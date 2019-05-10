---
title: Déployer du gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Résumé : consultez cette rubrique pour connaître la procédure de déploiement du gestionnaire de statistiques de Skype Entreprise Serveur.'
ms.openlocfilehash: c70bb596914142fb03e87ccd7e2f1df606aac31f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864903"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Déployer le Gestionnaire de Statistiques pour Skype Entreprise Server
 
**Résumé:** consultez cette rubrique pour connaître la procédure de déploiement du gestionnaire de statistiques de Skype Entreprise Server .
  
 Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui permet de consulter Skype pour l’état et les performances des données entreprise Server en temps réel. Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques.
  
Avant de procéder à l’installation du Gestionnaire de Statistiques, veillez à vous familiariser avec la configuration logicielle, matérielle et les spécifications réseau requises. Pour plus d’informations,[Planifier le Gestionnaire de Statistiques pour Skype Entreprise Server](plan.md).
  
> [!NOTE]
> Si vous procédez à la mise à niveau à partir d’une version précédente de Gestionnaire des Statistiques, reportez-vous à la rubrique[ Mettre à niveau le Gestionnaire de Statistiques dans Skype Entreprise Server Business Server](upgrade.md). 
  
> [!NOTE]
> Le site Web du gestionnaire de statistiques a été testé et fonctionne correctement sur Internet Explorer 11+, Microsoft Edge 20.10240+ et Chrome 46+ (version Evergreen actuelle). 
  
Vous trouverez le Gestionnaire de statistiques téléchargeable en [ https://aka.ms/StatsManDownload ](https://aka.ms/StatsManDownload). 
  
Cette rubrique contient les sections suivantes :
  
- [Déploiement du gestionnaire de statistiques](deploy.md#BKMK_Deploy)
    
- [Dépannage de votre déploiement](deploy.md#BKMK_Troubleshoot)
    
- [Création d’un certificat auto-signé](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Déploiement du gestionnaire de statistiques
<a name="BKMK_Deploy"> </a>

Pour déployer le Gestionnaire de Statistiques, procédez comme suit :
  
1. Préparez l’ordinateur hôte de l’écouteur en installant le système de mise en cache en mémoire Redis et vérifiez que les certificats appropriés sont installés.
    
2. Installez le service d’écoute sur l’ordinateur hôte. 
    
3. Installez le site Web sur l’ordinateur hôte.
    
4. Installez un agent sur chaque ordinateur Skype Entreprise Server que vous souhaitez surveiller.
    
5. Importez la topologie des serveurs que vous surveillez.
    
> [!NOTE]
> Le système Redis, le service d’écoute et le site Web doivent être installés sur le même ordinateur hôte. N’oubliez pas de que l’ordinateur hôte n’a pas Skype Entreprise Server installé. 
  
### <a name="prepare-the-listener-host-machine"></a>Préparation de l’ordinateur hôte

Pour préparer l’ordinateur hôte, vous devrez installer le système de mise en cache en mémoire Redis et vous assurer qu’un certificat valide est installé sur l’ordinateur. Microsoft recommande d’installer la dernière version stable de Redis 3.0. Le Gestionnaire de Statistiques version 2.0 a été testé avec Redis 3.2.100. 
  
1. Télécharger Redis à partir du site suivant : [ https://github.com/MSOpenTech/redis ](https://github.com/MSOpenTech/redis). 
    
    Les programmes d’installation non signés peuvent être téléchargés à partir de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Si nécessaire, les fichiers binaires signés sont accessibles via les responsables de package populaires : [Nuget](https://www.nuget.org/packages/Redis-64/) et [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Exécutez le fichier .msi fourni et suivez les invites.
    
   - Ne sélectionnez pas la case à cocher pour ajouter une règle de pare-feu.
    
2. Le service d’écoute requiert un certificat. Microsoft recommande vivement que votre certificat signé provienne d’une autorité de certification approuvée. 
    
    Si vous souhaitez utiliser un certificat auto-signé, par exemple à des fins de test au sein d’un laboratoire, reportez-vous à l’article [Création d’un certificat auto-signé](deploy.md#BKMK_SelfCert).
    
    Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.
    
### <a name="install-the-listener-service"></a>Installation du service de l’écouteur

Pour installer le service d’écoute sur l’ordinateur hôte, exécutez le fichier StatsManPerfAgentListener.msi et spécifiez les informations suivantes :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** il s’agit du mot de passe que les agents distants utiliseront pour s’authentifier auprès du service d’écoute.
    
   - **Port du service :** il s’agit du numéro de port HTTPS que l’écouteur utilisera pour communiquer avec les agents. Lors de l’installation, ce port pourra traverser le pare-feu local, une ACL d’URL sera créée et un certificat SSL sera lié à ce port. La valeur par défaut est 8443.
    
   - **Empreinte de certificat :** il s’agit de l’empreinte de certificat que l’écouteur utilisera pour chiffrer le protocole HTTPS. Le service réseau doit disposer d’un accès en lecture à la clé privée.
    
     Cliquez sur le bouton **Sélectionner...** pour choisir l’empreinte.
    
     Vous pouvez trouver l’empreinte de certificat à l’aide du gestionnaire de certificats ou de la commande PowerShell :
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Répertoire d’installation: ** il s’agit du répertoire dans lequel les fichiers binaires seront installés. Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.
    
   - **Répertoire AppData :** il s’agit du répertoire dans lequel le dossier Journaux et d’autres données seront stockés. Vous pouvez modifier le répertoire par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour valider l’installation, procédez comme suit :
  
1. Ouvrez un navigateur et accédez à https://localhost:\<service-port\>/healthcheck/.
    
    Par défaut, le port du service est 8443 (sauf si vous spécifiez un autre port).
    
2. Pour vérifier l’installation correcte de l’écouteur, procédez comme suit :
    
   - Si la page de vérification d’intégrité s’affiche, l’écouteur a été correctement installé.
    
   - Si la KnownServerCount est supérieur ou égal à 1, Redis la connexion est établie.
    
   - Après l’installation d’au moins un agent, patientez quelques minutes et vérifiez que le compteur ValuesWritten augmente.
    
### <a name="install-the-website"></a>Installation du site Web

Installer le site Web de l’ordinateur hôte en exécutant le StatsManWebSite.msi (inclus avec [Skype Entreprise Server, en temps réel statistiques Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) et en spécifiant des opérations suivantes :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Port du service :** il s’agit du numéro de port que le site Web écoutera. Vous pouvez le modifier ultérieurement à l’aide de la liaison du gestionnaire IIS. Lors de l’installation, ce port pourra traverser le pare-feu local.
    
   - **Répertoire d’installation :** Il s’agit du répertoire dans lequel les fichiers binaires seront installés. Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.
    
   - **Répertoire AppData :** il s’agit du répertoire dans lequel le dossier Journaux et d’autres données seront stockés. Vous pouvez modifier le répertoire par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Pour afficher le site Web, ouvrez un navigateur et accédez à:http://localhost,webport\>/.
  
Pour afficher uniquement les informations d’intégrité, ouvrez un navigateur et accédez à :http://localhost:\<webport\>/healthcheck/.
  
Par défaut, le numéro de port Web est 8080. Vous pouvez modifier la liaison de port du site Web à l’aide du gestionnaire IIS.
  
Le programme d’installation Web ajoute un groupe de sécurité local appelé StatsManWebSiteUsers. Vous pouvez ajouter des comptes à ce groupe de sécurité pour accorder l’accès au site Web. 
  
### <a name="install-the-agents"></a>Installation des agents

Pour installer un agent sur chaque Skype Entreprise Server que vous souhaitez surveiller, exécutez le fichier StatsManPerfAgent.msi et spécifiez les informations suivantes :
  
1. Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.  
    
2. Dans la page suivante, spécifiez les informations suivantes :
    
   - **Mot de passe du service :** il s’agit du mot de passe que l’agent distant utilisera pour s’authentifier auprès du service d’écoute.
    
   - **URI du service :** il s’agit de l’URI où réside l’écouteur. Elle doit utiliser le formathttps://name:port.
    
     Vous pouvez utiliser un nom NETBIOS ou un nom de domaine complet. Vous pouvez utiliser le nom qui est également spécifié comme **Objet** ou **Autres noms de l’objet** du certificat sur le service d’écoute, mais cela n’est pas obligatoire.
    
   - **Empreinte du service :** il s’agit de l’empreinte du certificat SSL utilisé par l’écouteur. L’agent utilisera cette empreinte pour s’authentifier auprès de l’écouteur. (Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.)
    
   - **Répertoire d’installation: ** il s’agit du répertoire dans lequel les fichiers binaires seront installés. Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.
    
   - **Répertoire AppData :** Il s’agit du répertoire dans lequel le dossier Journaux et le fichier password.txt chiffré seront stockés. Vous pouvez le modifier à partir du répertoire par défaut. Il ne sera pas supprimé lors de la désinstallation.
    
3. Cliquez sur **Installer**.
    
Si vous installez un agent sur différents ordinateurs, vous souhaitez peut-être le faire en mode sans assistance. Par exemple : 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importation de la topologie
<a name="BKMK_ImportTopology"> </a>

Lorsque le Gestionnaire de Statistiques est installé et en cours d’exécution, vous devez importer la topologie Skype Entreprise Server de manière à ce que le Gestionnaire de Statistiques puisse connaître le site, le pool et le rôle de chaque serveur. Pour importer votre topologie Skype Entreprise Server, utilisez l’applet de commande[Obtenir-CSPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) pour récupérer les informations relatives à chaque pool utilisé dans votre organisation, puis importez-les dans le Gestionnaire de Statistiques.
  
Pour importer a topologie de Skype Entreprise Server, procédez comme suit :
  
1. Sur un hôte qui a Skype Entreprise Server pour les applets de commande PowerShell:
    
    a. Exécutez la commande suivante : 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copiez le fichier «mypoolinfo.xml» sur le serveur exécutant l’Écouteur.
    
2. Sur l’hôte exécutant l’Écouteur :
    
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

Pour consulter les informations du serveur importé, exécutez le script suivant : 
  
```
.\Get-StatsManServerInfo.ps1
```

Si vous souhaitez surveiller des serveurs qui ne font pas partie de votre topologie Skype Entreprise Server, par exemple un serveur Exchange, vous pouvez effectuer une importation de serveur unique vers l’hôte qui exécute l’écouteur. Pour effectuer une importation de serveur , procédez comme suit :
  
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
  
- L’agent est-il enregistré auprès du Gestionnaire de Statistiques?
    
1. 	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).  
    
2. Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
- L’agent peut-il contacter l’écouteur ?
    
1. Vérifiez que le service d’écoute est exécuté. 
    
    Si ce n’est pas le cas, vérifiez que le système Redis est en cours d’exécution, puis essayez de redémarrer l’écouteur.
    
2. Assurez-vous que le port est ouvert sur le service d’écoute et que l’ordinateur de l’agent peut communiquer avec le port.
    
- Pour vérifier que le Gestionnaire de Statistiques collecte des données, vous pouvez consulter le fichier CSV comme suit.  
    
    La commande suivante récupère les noms de stockage de compteur : 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    La commande suivante récupère les valeurs des compteurs spécifiés : 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Pour plus d’informations sur l’ensemble des événements qui peuvent figurer dans le journal d’événements de l’application, reportez-vous à la rubrique [Résolution de Gestionnaire de Statistiques dans Skype Entreprise Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Création d’un certificat auto-signé
<a name="BKMK_SelfCert"> </a>

Microsoft recommande vivement d’utiliser un certificat signé par une autorité de certification approuvée. Toutefois, si vous souhaitez utiliser un certificat auto-signé à des fins de test, procédez comme suit : 
  
1. Connectez-vous à une console PowerShell en tant qu’administrateur, et tapez les informations suivantes :
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Type `certlm.msc`. Le Gestionnaire de Certificat s’ouvrira pour l’ordinateur local.
    
3. Accédez à **Personnel** et ouvrez**Certificats**.
    
4. Cliquez à l’aide du bouton droit de la souris sur **StatsManListener-\>Toutes les Tâches-\>Gérer les clés privées Keys…**
    
5. Cliquez sur **Ajouter**.
    
6. Dans la zone **Entrer les noms d’objets à sélectionner**, tapez Service réseau.
    
7. Cliquez sur **OK**.
    
8. Sous **Contrôle total**, désactivez la case à cocher **Autoriser**. Seul un accès en lecture est nécessaire.
    
9. Cliquez sur **OK**.
    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_SelfCert"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)
    
- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)ß
