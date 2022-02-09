---
title: Déployer le Gestionnaire de Statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Résumé : Lisez cette rubrique pour découvrir comment déployer le Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: 98a1a405ccccf9ee88941588e6e43f152d2f6bb3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410717"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Déployer le Gestionnaire de Statistiques pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment déployer le Gestionnaire de statistiques pour Skype Entreprise Server.
  
 Le Gestionnaire de statistiques Skype Entreprise Server est un outil puissant qui vous permet d’afficher Skype Entreprise Server données d’état et de performances en temps réel. Vous pouvez sonder les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques.
  
Avant d’essayer d’installer le Gestionnaire de statistiques, assurez-vous que vous êtes familiarisé avec la configuration logicielle, réseau et matérielle requise. Pour plus d’informations, [voir Plan for Statistics Manager for Skype Entreprise Server](plan.md).
  
> [!NOTE]
> Si vous êtes en cours de mise à niveau à partir d’une version antérieure du Gestionnaire de statistiques, consultez [Upgrade Statistics Manager pour Skype Entreprise Server](upgrade.md). 
  
> [!NOTE]
> Le site web du gestionnaire de statistiques a été testé et fonctionne correctement sur Internet Explorer 11+, Edge 20.10240+ et Chrome 46+ (version persistante actuelle). 
  
Vous pouvez trouver le Gestionnaire de statistiques téléchargeable sur [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Cette rubrique comprend les sections suivantes :
  
- [Déployer le Gestionnaire de statistiques](deploy.md#BKMK_Deploy)
    
- [Résoudre les problèmes de votre déploiement](deploy.md#BKMK_Troubleshoot)
    
- [Créer un certificat auto-signé](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Déployer le Gestionnaire de statistiques
<a name="BKMK_Deploy"> </a>

Pour déployer le Gestionnaire de statistiques, suivez les étapes suivantes :
  
1. Préparez l’ordinateur hôte d’écoute en installant le système de mise en cache redis en mémoire et en vous assurant que vous avez installé les certificats appropriés.
    
2. Installez le service d’écoute sur l’ordinateur hôte. 
    
3. Installez le site web sur l’ordinateur hôte.
    
4. Installez un agent sur chaque ordinateur Skype Entreprise Server que vous souhaitez surveiller.
    
5. Importez la topologie pour les serveurs que vous surveillez.
    
> [!NOTE]
> Redis, le service d’écoute et le site web doivent tous être installés sur le même ordinateur hôte. Assurez-vous que l’ordinateur hôte n’a pas Skype Entreprise Server installé. 
  
### <a name="prepare-the-listener-host-machine"></a>Préparer l’ordinateur hôte d’écoute

Pour préparer l’ordinateur hôte, vous devez installer le système de mise en cache redis en mémoire et vous assurer qu’un certificat valide se trouve sur l’ordinateur. Microsoft recommande d’installer la dernière version stable de Redis 3.0. La version 2.0 du Gestionnaire de statistiques a été testée avec Redis 3.2.100. 
  
1. Téléchargez Redis à partir du site suivant : [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Les programme d’installation non signés peuvent être téléchargés à partir de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Si nécessaire, les binaires signés sont disponibles par le biais de gestionnaires de packages populaires [: Nuget](https://www.nuget.org/packages/Redis-64/) et [Atomlatey](https://chocolatey.org/packages/redis-64).
    
   - Exécutez le msi fourni et suivez les invites.
    
   - Ne cochez pas la case pour ajouter une règle de pare-feu.
    
2. Le service d’écoute requiert un certificat. Microsoft recommande vivement la signature d’un certificat par une autorité de certification de confiance. 
    
    Si vous souhaitez utiliser un certificat auto-signé (à des fins de test dans un atelier, par exemple), voir Créer un certificat [auto-signé](deploy.md#BKMK_SelfCert).
    
    Notez que l’agent utilise la vérification de l’empreinte numérique du certificat (au lieu de la vérification de chaîne). Il n’aura pas la validation complète du certificat, car il est possible d’utiliser des certificats auto-signés.
    
### <a name="install-the-listener-service"></a>Installer le service d’écoute

Installez le service d’écoute sur l’ordinateur hôte en exécutant le StatsManPerfAgentListener.msi et en spécifiant ce qui suit :
  
1. Examinez le contrat de licence et, si vous acceptez, sélectionnez **J’accepte** les termes du contrat de licence, puis cliquez sur **Suivant**. 
    
2. Sur la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** Il s’agit du mot de passe que les agents distants utiliseront pour s’authentifier au service d’écoute.
    
   - **Port de service :** Il s’agit du numéro de port HTTPS que l’port d’écoute utilisera pour communiquer avec les agents. Au cours de l’installation, ce port est autorisé par le pare-feu local, une liste decl d’URL est créée et un cert SSL est lié à ce port. La valeur par défaut est 8443.
    
   - **Empreinte numérique de certificat :** Il s’agit de l’empreinte numérique du certificat que l’écoute utilisera pour chiffrer le protocole HTTPS. Le service réseau doit avoir un accès en lecture à la clé privée.
    
     Cliquez sur **le bouton Sélectionner...** pour choisir l’empreinte numérique.
    
     Vous pouvez trouver l’empreinte du certificat à l’aide du Gestionnaire de certificats ou à l’aide de la commande PowerShell suivante :
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **Installer Dir :** Il s’agit du répertoire dans lequel les binaires seront installés. Vous pouvez modifier la valeur par défaut à l’aide du **bouton Parcourir...**
    
   - **AppData Dir :** Il s’agit du répertoire dans lequel le dossier Logs et d’autres données sont stockés. Vous pouvez la modifier par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour valider l’installation, effectuez les étapes suivantes :
  
1. Ouvrez un navigateur et accédez à https://localhost:\<service-port\>/healthcheck/
    
    Par défaut, le port de service est 8443 (sauf si vous avez spécifié un autre port).
    
2. Pour vous assurer que l’écoute a été correctement installée, recherchez ce qui suit :
    
   - Si la page de contrôle d’état s’affiche, l’installation de l’écoute a réussi.
    
   - Si knownServerCount est supérieur ou supérieur à 1, la connexion à Redis est établie.
    
   - Après quelques minutes d’attente et après avoir installé au moins un agent, vérifiez que le compteur ValuesWritten est incrémenté.
    
### <a name="install-the-website"></a>Installer le site web

Installez le site web sur l’ordinateur hôte en exécutant le StatsManWebSite.msi (inclus dans [Skype Entreprise Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518) et en spécifiant les informations suivantes :
  
1. Examinez le contrat de licence et, si vous acceptez, sélectionnez **J’accepte** les termes du contrat de licence, puis cliquez sur **Suivant**. 
    
2. Sur la page suivante, spécifiez les informations suivantes :
    
   - **Port de service :** Il s’agit du numéro de port que le site web écoutera. Vous pouvez le modifier ultérieurement à l’aide de la liaison de gestionnaire IIS. Pendant l’installation, ce port est autorisé par le pare-feu local.
    
   - **Installer Dir :** Il s’agit du répertoire dans lequel les binaires seront installés. Vous pouvez modifier la valeur par défaut à l’aide du **bouton Parcourir...**
    
   - **AppData Dir :** Il s’agit du répertoire dans lequel le dossier Logs et d’autres données sont stockés. Vous pouvez la modifier par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour afficher le site Web, ouvrez un navigateur et accédez à : http://localhost,webport\>/.
  
Pour afficher uniquement les informations d’état, ouvrez un navigateur et accédez à : http://localhost:\<webport\>/healthcheck/.
  
Par défaut, le numéro de port web est 8080. Vous pouvez modifier la liaison de port du site web à l’aide du Gestionnaire des iis.
  
Le programme d’installation web ajoute un groupe de sécurité local, appelé StatsManWebSiteUsers. Vous pouvez ajouter des comptes à ce groupe de sécurité pour accorder l’accès au site web. 
  
### <a name="install-the-agents"></a>Installer les agents

Installez un agent sur chaque Skype Entreprise Server que vous souhaitez surveiller en exécutant le StatsManPerfAgent.msi et en spécifiant les étapes suivantes :
  
1. Examinez le contrat de licence et, si vous acceptez, sélectionnez **J’accepte** les termes du contrat de licence, puis cliquez sur **Suivant**. 
    
2. Sur la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** Il s’agit du mot de passe que l’agent distant utilisera pour s’authentifier au service d’écoute.
    
   - **URI de service :** Il s’agit de l’URI où réside l’écoute. Il doit utiliser le https://name:port format.
    
     Vous pouvez utiliser un nom NETBIOS ou un nom de domaine complet. Vous pouvez utiliser le nom qui est également spécifié en tant qu’objet ou **autre** nom du sujet du certificat sur le service d’écoute, mais ce n’est pas obligatoire.
    
   - **Empreinte de service :** Il s’agit de l’empreinte numérique du certificat SSL utilisé par l’écoute. L’agent utilisera cette empreinte numérique pour s’authentifier sur l’écoute. (Il n’aura pas la validation complète du certificat, car il est possible d’utiliser des certificats auto-signés.)
    
   - **Installer Dir :** Il s’agit du répertoire dans lequel les binaires seront installés. Vous pouvez modifier la valeur par défaut à l’aide du **bouton Parcourir...**
    
   - **AppData Dir :** Il s’agit du répertoire dans lequel le dossier Logs et le fichier password.txt chiffré seront stockés. Vous pouvez le modifier par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Si vous installez un agent sur de nombreux ordinateurs, vous voudrez probablement le faire en mode sans surveillance. Par exemple : 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importer la topologie
<a name="BKMK_ImportTopology"> </a>

Une fois le Gestionnaire de statistiques installé et en cours d’exécution, vous devez importer la topologie Skype Entreprise Server afin que le gestionnaire de statistiques connaisse le site, le pool et le rôle de chaque serveur. Pour importer votre topologie Skype Entreprise Server, vous allez utiliser l’cmdlet [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) pour récupérer des informations sur chaque pool utilisé dans votre organisation, puis importer ces informations dans le Gestionnaire de statistiques.
  
Pour importer la topologie Skype Entreprise Server, suivez les étapes suivantes :
  
1. Sur un hôte qui possède les Skype Entreprise Server cmdlets PowerShell :
    
    a. Exécutez la commande suivante : 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiez le fichier « mypoolinfo.xml » sur le serveur qui exécute l’écoute.
    
2. Sur l’hôte qui exécute l’écoute :
    
   a. Exécutez PowerShell.
    
   b. Accédez au répertoire sur lequel l’écoute est installé. La valeur par défaut est : 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Pour vérifier quels serveurs sont ajoutés et mis à jour, exécutez la commande suivante :
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

La commande suivante vous permet d’afficher toutes les options :
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Pour consulter les informations de votre serveur actuellement importé, exécutez le script suivant : 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

Si vous souhaitez surveiller des serveurs qui ne sont pas dans votre topologie Skype Entreprise Server (une Exchange Server, par exemple), vous pouvez importer un serveur unique sur l’hôte qui exécute l’écoute. Pour importer un serveur unique, suivez les étapes suivantes :
  
1. Accédez au répertoire sur lequel l’écoute est installé. La valeur par défaut est : 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Exécutez la commande suivante :
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Résoudre les problèmes de votre déploiement
<a name="BKMK_Troubleshoot"> </a>

Si un agent ne parvient pas à démarrer, recherchez ce qui suit : 
  
- L’agent est-il inscrit dans le Gestionnaire de statistiques ?
    
    1. Assurez-vous que vous avez suivi les instructions d’importation de la topologie. Voir [Importer la topologie](deploy.md#BKMK_ImportTopology).
        
    2. Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, les nodes dans un cluster SQL AlwaysOn), vous devez ajouter l’agent manuellement en suivant les instructions de l’importation de la topologie[.](deploy.md#BKMK_ImportTopology)
    
- L’agent peut-il contacter l’écoute ?
    
    1. Assurez-vous que le service d’écoute est en cours d’exécution. 
        
        S’il n’est pas en cours d’exécution, assurez-vous que Redis est en cours d’exécution, puis essayez de redémarrer l’écoute.
        
    2. Assurez-vous que le port est ouvert au service d’écoute et que l’ordinateur de l’agent peut communiquer avec le port.
    
- Pour vous assurer que le Gestionnaire de statistiques collecte des données, vous pouvez vérifier le fichier CSV comme suit. 
    
    La commande suivante récupère les noms de stockage des compteurs : 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    La commande suivante récupère les valeurs des compteurs spécifiés : 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Pour plus d’informations sur tous les événements que vous pouvez voir dans le journal des événements d’application, voir [Troubleshoot Statistics Manager for Skype Entreprise Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Créer un certificat auto-signé
<a name="BKMK_SelfCert"> </a>

Microsoft recommande vivement d’utiliser un certificat signé par une autorité de certification de confiance. Toutefois, si vous souhaitez utiliser un certificat auto-signé à des fins de test, faites les choses suivantes : 
  
1. À partir d’une console PowerShell lorsque vous êtes connecté en tant qu’administrateur, tapez ce qui suit :
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Type  `certlm.msc`. Cela ouvre le Gestionnaire de certificats pour l’ordinateur local.
    
3. Accédez **à Personnel**, puis ouvrez **Certificats**.
    
4. Cliquez avec le bouton droit **sur StatsManListener-All\> Tasks-Manage\> Private Keys...**
    
5. Cliquez sur **Ajouter**.
    
6. Dans la **zone Entrer les noms des objets à sélectionner** , tapez ce qui suit : Service réseau
    
7. Cliquez sur **OK**.
    
8. Sous **Contrôle total**, désochez **la case** Autoriser. (Seul l’accès en lecture est nécessaire.)
    
9. Cliquez sur **OK**.
    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_SelfCert"> </a>

Pour plus d'informations, consultez les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)
    
- [Résoudre les problèmes du Gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md) ß