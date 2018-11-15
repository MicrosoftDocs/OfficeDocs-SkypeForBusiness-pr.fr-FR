---
title: Déployer des statistiques responsable Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer des statistiques Manager pour Skype pour Business Server.'
ms.openlocfilehash: f408f494fc95fecdf0a0e80114d4d68d99181885
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532146"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Déployer des statistiques responsable Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment déployer des statistiques Manager pour Skype pour Business Server.
  
 Gestionnaire de statistiques pour Skype pour Business Server est un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel. Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques.
  
Avant d’essayer d’installer le Gestionnaire de statistiques, assurez-vous que vous êtes familiarisé avec la configuration requise matérielle, logicielle et réseau. Pour plus d’informations, voir [planification pour le Gestionnaire de statistiques de Skype pour Business Server](plan.md).
  
> [!NOTE]
> Si vous mettez à niveau depuis une version précédente du Gestionnaire de statistiques, voir [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md). 
  
> [!NOTE]
> Le site Web du gestionnaire de statistiques a été testé et fonctionne correctement sur Internet Explorer 11+, Edge 20.10240+ et Chrome 46+ (version Evergreen actuelle). 
  
Vous pouvez trouver le Gestionnaire de statistiques téléchargeable à [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Cette rubrique contient les sections suivantes :
  
- [Déploiement du gestionnaire de statistiques](deploy.md#BKMK_Deploy)
    
- [Dépannage de votre déploiement](deploy.md#BKMK_Troubleshoot)
    
- [Création d’un certificat auto-signé](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Déploiement du gestionnaire de statistiques
<a name="BKMK_Deploy"> </a>

Pour déployer les statistiques Manager, procédez comme suit :
  
1. Préparez l’ordinateur hôte de l’écouteur en installant le système de mise en cache en mémoire Redis et vérifiez que les certificats appropriés sont installés.
    
2. Installez le service d’écoute sur l’ordinateur hôte.  
    
3. Installez le site Web sur l’ordinateur hôte.
    
4. Installer un Agent sur chaque Skype pour ordinateur Business Server à surveiller.
    
5. Importez la topologie des serveurs que vous surveillez.
    
> [!NOTE]
> Le système Redis, le service d’écoute et le site Web doivent être installés sur le même ordinateur hôte. N’oubliez pas de que l’ordinateur hôte n’a pas de Skype pour Business Server est installé. 
  
### <a name="prepare-the-listener-host-machine"></a>Préparation de l’ordinateur hôte

Pour préparer la machine hôte, vous devez installer le système de mise en cache en mémoire Redis et vous assurer qu’un certificat valide sur l’ordinateur. Microsoft recommande d’installer la dernière version stable de 3.0 Redis. Gestionnaire de statistiques version 2.0 a été testée avec Redis 3.2.100. 
  
1. Téléchargez Redis à partir du site suivant : [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Programmes d’installation non signés peuvent être téléchargés à partir de[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Si nécessaire, des fichiers binaires signés sont disponibles via les gestionnaires de package populaires suivants : [Nuget](https://www.nuget.org/packages/Redis-64/) et [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Exécutez le fichier .msi fourni et suivez les invites.
    
   - Ne sélectionnez pas la case à cocher pour ajouter une règle de pare-feu.
    
2. Le service d’écoute requiert un certificat. Microsoft recommande vivement que vous disposez d’un certificat signé par une autorité de certification approuvée. 
    
    Si vous souhaitez utiliser un certificat auto-signé, par exemple à des fins de test au sein d’un laboratoire, reportez-vous à l’article [Création d’un certificat auto-signé](deploy.md#BKMK_SelfCert).
    
    Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.
    
### <a name="install-the-listener-service"></a>Installation du service de l’écouteur

Installer le service d’écoute sur l’ordinateur hôte en exécutant le StatsManPerfAgentListener.msi et en spécifiant les paramètres suivants :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** il s’agit du mot de passe que les agents distants utiliseront pour s’authentifier auprès du service d’écoute.
    
   - **Port du Service :** Il s’agit du numéro de port HTTPS qui utilise le port d’écoute pour communiquer avec les Agents. Pendant l’installation, ce port seront autorisés à travers le pare-feu local, un ACL URL sera créé, et un certificat SSL sera lié à ce port. La valeur par défaut est 8443.
    
   - **Empreinte numérique du certificat :** Il s’agit de l’empreinte de certificat qu'utilise le port d’écoute pour chiffrer le protocole HTTPS. Service réseau doit avoir un accès en lecture à la clé privée.
    
     Cliquez sur le bouton **Sélectionner...** pour choisir l’empreinte.
    
     Vous pouvez trouver l’empreinte de certificat à l’aide du gestionnaire de certificats ou de la commande PowerShell :
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Répertoire d’installation :** Il s’agit de l’annuaire sur lequel les fichiers binaires seront installés. Vous pouvez la modifier à partir de la valeur par défaut de commandes en utilisant le bouton **Parcourir** .
    
   - **AppData Dir :** Il s’agit du répertoire où seront stockées le dossier Logs et autres données. Vous pouvez le changer à partir de la valeur par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour valider l’installation, procédez comme suit :
  
1. Ouvrez un navigateur et accédez àhttps://localhost:\<service-port\>/healthcheck/
    
    Par défaut, le port du service est 8443 (sauf si vous spécifiez un autre port).
    
2. Pour vérifier l’installation correcte de l’écouteur, procédez comme suit :
    
   - Si la page de vérification d’intégrité s’affiche, l’écouteur a été correctement installé.
    
   - Si la valeur KnownServersCount est définie sur 1 ou un nombre supérieur, la connexion à Redis est établie.
    
   - Après l’installation d’au moins un agent, patientez quelques minutes et vérifiez que le compteur ValuesWritten augmente.
    
### <a name="install-the-website"></a>Installation du site Web

Installer le site Web sur l’ordinateur hôte en exécutant le StatsManWebSite.msi et en spécifiant les paramètres suivants :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Port du Service :** Il s’agit du numéro de port que du site web écoutera. Vous pouvez le modifier ultérieurement à l’aide du Gestionnaire des services Internet de liaison. Pendant l’installation, ce port est autorisé à travers le pare-feu local.
    
   - **Répertoire d’installation :** Il s’agit du répertoire où seront installés les fichiers binaires. Vous pouvez la modifier à partir de la valeur par défaut de commandes en utilisant le bouton **Parcourir** .
    
   - **AppData Dir :** Il s’agit du répertoire où seront stockées le dossier Logs et autres données. Vous pouvez le changer à partir de la valeur par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour afficher le site Web, ouvrez un navigateur et accédez à : http://localhost, webport\>/.
  
Pour afficher uniquement les informations d’intégrité, ouvrez un navigateur et accédez à : http://localhost:\<webport\>/healthcheck/.
  
Par défaut, le numéro de port Web est 8080. Vous pouvez modifier la liaison de port du site Web à l’aide du gestionnaire IIS.
  
Le programme d’installation Web ajoute un groupe de sécurité local appelé StatsManWebSiteUsers. Vous pouvez ajouter des comptes à ce groupe de sécurité pour accorder l’accès au site Web. 
  
### <a name="install-the-agents"></a>Installation des agents

Installer un Agent sur chaque Skype pour Business Server que vous souhaitez surveiller en exécutant la StatsManPerfAgent.msi et en spécifiant les paramètres suivants :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** il s’agit du mot de passe que l’agent distant utilisera pour s’authentifier auprès du service d’écoute.
    
   - **URI de service :** Il s’agit de l’URI où réside le port d’écoute. Elle doit utiliser le https://name:port format.
    
     Vous pouvez utiliser un nom NETBIOS ou un nom de domaine complet. Vous pouvez utiliser le nom qui est également spécifié en tant que **l’objet** ou les **Noms de sujet** du certificat sur le service d’écoute, mais ce n’est pas une condition requise.
    
   - **Empreinte numérique de service :** Il s’agit de l’empreinte du certificat SSL à l’aide de l’écouteur. L’Agent utilisera cette empreinte pour s’authentifier sur le port d’écoute. (Il n’aura pas complète de validation de certificat, car il est possible d’utiliser des certificats auto-signés.)
    
   - **Répertoire d’installation :** Il s’agit de l’annuaire sur lequel les fichiers binaires seront installés. Vous pouvez la modifier à partir de la valeur par défaut de commandes en utilisant le bouton **Parcourir** .
    
   - **AppData Dir :** Il s’agit le répertoire où seront stockés le dossier Logs et le fichier password.txt chiffré. Vous peut Merci modifier celui par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Si vous installez un agent sur différents ordinateurs, vous souhaitez peut-être le faire en mode sans assistance. Par exemple :   
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importation de la topologie
<a name="BKMK_ImportTopology"> </a>

Après les statistiques Manager est installé et en cours d’exécution, vous devez importer le Skype pour la topologie du serveur d’entreprise afin que le Gestionnaire de statistiques sait le Site, le Pool et le rôle de chaque serveur. Pour importer votre Skype pour la topologie du serveur d’entreprise, vous allez l’applet de commande [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) permet de récupérer des informations sur chaque pool utilisé dans votre organisation, puis importer ces informations dans le Gestionnaire de statistiques.
  
Pour importer le Skype pour la topologie du serveur d’entreprise, procédez comme suit :
  
1. Sur un hôte ayant le Skype pour les applets de commande PowerShell de serveur d’entreprise :
    
    a. Exécutez la commande suivante : 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiez le fichier « mypoolinfo.xml » sur le serveur qui exécute le port d’écoute.
    
2. Sur l’hôte exécutant l’écouteur :
    
   a. Exécutez PowerShell.
    
   b. Accédez au répertoire dans lequel l’écouteur est installé. Valeur par défaut : 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Pour confirmer les serveurs qui sont ajoutés et mis à jour, exécutez la commande suivante :
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

La commande suivante permet d’afficher toutes les options :
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Pour voir vos informations de serveur actuellement importé, exécutez le script suivant : 
  
```
.\Get-StatsManServerInfo.ps1
```

Si vous souhaitez surveiller les serveurs qui ne sont pas dans votre Skype pour topologie Business Server, un serveur Exchange, par exemple--vous pouvez effectuer une importation de serveur unique sur l’hôte qui exécute le port d’écoute. Pour effectuer une importation de serveur , procédez comme suit :
  
1. Accédez au répertoire dans lequel l’écouteur est installé. Valeur par défaut : 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Exécutez la commande suivante :
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Dépannage de votre déploiement
<a name="BKMK_Troubleshoot"> </a>

Si un agent ne démarre pas, vérifiez les points suivants :  
  
- Est-ce que l’agent inscrit dans le Gestionnaire des statistiques ?
    
1. 	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).  
    
2. Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
- L’agent peut-il contacter l’écouteur ?
    
1. Vérifiez que le service d’écoute est exécuté.   
    
    Si ce n’est pas le cas, vérifiez que le système Redis est en cours d’exécution, puis essayez de redémarrer l’écouteur.
    
2. Assurez-vous que le port est ouvert pour le service d’écoute, et que l’ordinateur de l’Agent peut communiquer avec le port.
    
- Pour vous assurer que gestionnaire de statistiques de collecte des données, vous pouvez vérifier le fichier CSV comme suit. 
    
    La commande suivante récupère les noms de stockage de compteur :   
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    La commande suivante récupère les valeurs des compteurs spécifiés :  
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Pour plus d’informations sur tous les événements que vous pouvez voir dans le journal des événements, voir [Résoudre les statistiques responsable Skype pour Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Création d’un certificat auto-signé
<a name="BKMK_SelfCert"> </a>

Microsoft recommande vivement d’utiliser un certificat signé par une autorité de certification approuvée. Toutefois, si vous souhaitez utiliser un certificat auto-signé à des fins de test, procédez comme suit : 
  
1. Connectez-vous à une console PowerShell en tant qu’administrateur, et tapez les informations suivantes :
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Type de `certlm.msc`. Le gestionnaire de certificat s’ouvrira pour l’ordinateur local.
    
3. Accédez à **personnel**, puis ouvrez **les certificats**.
    
4. Cliquez avec le bouton droit sur **StatsManListener -\>toutes les tâches -\>gérer les clés privées...**
    
5. Cliquez sur **Ajouter **.
    
6. Dans la zone **Entrer les noms d’objets à sélectionner**, tapez Service réseau.
    
7. Cliquez sur **OK**.
    
8. Sous **Contrôle total**, désactivez la case à cocher **Autoriser**. Seul un accès en lecture est nécessaire.
    
9. Cliquez sur **OK**.
    
## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_SelfCert"> </a>

Pour plus d’informations, voir les articles suivants :
  
- [Planifier Business Server pour le Gestionnaire de statistiques de Skype](plan.md)
    
- [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md)
    
- [Résoudre les statistiques du gestionnaire pour Skype pour Business Server](troubleshoot.md)
    
- [Blog du gestionnaire de statistiques de Skype Entreprise Server ](https://blogs.technet.microsoft.com/skypestatsman/)
    

