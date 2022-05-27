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
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer le Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675986"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Déployer le Gestionnaire de Statistiques pour Skype Entreprise Server

**Résumé:** Lisez cette rubrique pour savoir comment déployer le Gestionnaire de statistiques pour Skype Entreprise Server.

 Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui vous permet d’afficher Skype Entreprise Server données d’intégrité et de performances en temps réel. Vous pouvez interroger les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques.

Avant d’essayer d’installer le Gestionnaire des statistiques, assurez-vous que vous connaissez bien les exigences en matière de logiciels, de mise en réseau et de matériel. Pour plus d’informations, consultez [Plan for Statistics Manager for Skype Entreprise Server](plan.md).

> [!NOTE]
> Si vous effectuez une mise à niveau à partir d’une version précédente de Statistics Manager, consultez [Upgrade Statistics Manager pour Skype Entreprise Server](upgrade.md).

> [!NOTE]
> Le site web du Gestionnaire de statistiques a été testé et fonctionne correctement sur Internet Explorer 11+, Edge 20.10240+ et Chrome 46+ (version persistante actuelle).

Vous pouvez trouver le Gestionnaire des statistiques téléchargeable à l’adresse [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

Cette rubrique comprend les sections suivantes :

- [Déployer le Gestionnaire des statistiques](deploy.md#BKMK_Deploy)

- [Résoudre les problèmes de déploiement](deploy.md#BKMK_Troubleshoot)

- [Créer un certificat auto-signé](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>Déployer le Gestionnaire des statistiques
<a name="BKMK_Deploy"> </a>

Pour déployer Statistics Manager, procédez comme suit :

1. Préparez l’ordinateur hôte de l’écouteur en installant le système de mise en cache Redis en mémoire et en vous assurant que vous avez installé les certificats appropriés.

2. Installez le service Écouteur sur l’ordinateur hôte.

3. Installez le site web sur l’ordinateur hôte.

4. Installez un agent sur chaque Skype Entreprise Server ordinateur que vous souhaitez surveiller.

5. Importez la topologie des serveurs que vous surveillez.

> [!NOTE]
> Redis, le service Écouteur et le site web doivent tous être installés sur le même ordinateur hôte. Assurez-vous que l’ordinateur hôte n’a pas Skype Entreprise Server installé.

### <a name="prepare-the-listener-host-machine"></a>Préparer l’ordinateur hôte de l’écouteur

Pour préparer l’ordinateur hôte, vous devez installer le système de mise en cache Redis en mémoire et vous assurer qu’un certificat valide se trouve sur l’ordinateur. Microsoft vous recommande d’installer la dernière version stable de Redis 3.0. Statistics Manager version 2.0 a été testé avec Redis 3.2.100.

1. Téléchargez Redis à partir du site suivant : [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    Les programmes d’installation non signés peuvent être téléchargés à partir de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    Les fichiers binaires signés sont disponibles par le biais de gestionnaires de packages populaires : [Nuget](https://www.nuget.org/packages/Redis-64/) et [Choclatey](https://chocolatey.org/packages/redis-64).

   - Exécutez le msi fourni et suivez les invites.

   - Ne cochez pas la case pour ajouter une règle de pare-feu.

2. Le service d’écouteur requiert un certificat. Microsoft recommande vivement de disposer d’un certificat signé par une autorité de certification approuvée.

    Si vous souhaitez utiliser un certificat auto-signé à des fins de test dans un labo, par exemple, consultez [Créer un certificat auto-signé](deploy.md#BKMK_SelfCert).

    L’Agent utilise la vérification de l’empreinte numérique du certificat (au lieu de la vérification en chaîne). Il n’effectue pas la validation complète des certificats, car il est possible d’utiliser des certificats auto-signés.

### <a name="install-the-listener-service"></a>Installer le service Écouteur

Installez le service Écouteur sur l’ordinateur hôte en exécutant le StatsManPerfAgentListener.msi et en spécifiant les éléments suivants :

1. Passez en revue le contrat de licence et, si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

2. Dans la page suivante, spécifiez les informations suivantes :

   - **Mot de passe du service :** Ce mot de passe est utilisé par les agents distants pour s’authentifier auprès du service Écouteur.

   - **Port de service :** Ce numéro de port HTTPS est utilisé par l’écouteur pour communiquer avec les agents. Pendant l’installation, ce port est autorisé via le pare-feu local, une liste de contrôle d’accès d’URL est créée et un certificat SSL est lié à ce port. La valeur par défaut est 8443.

   - **Empreinte numérique du certificat :** Ce certificat est utilisé par l’écouteur pour chiffrer le protocole HTTPS. Le service réseau doit disposer d’un accès en lecture à la clé privée.

     Cliquez sur le bouton **Sélectionner...** pour choisir l’empreinte numérique.

     Vous pouvez trouver l’empreinte numérique du certificat à l’aide du Gestionnaire de certificats ou à l’aide de la commande PowerShell suivante :

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Installez Dir :** C’est dans ce répertoire que les fichiers binaires seront installés. Vous pouvez le modifier par défaut à l’aide du bouton **Parcourir...** .

   - **AppData Dir :** Ce répertoire est l’emplacement où le dossier Journaux et d’autres données seront stockés. Vous pouvez le modifier à partir de la valeur par défaut. Il ne sera pas supprimé lors de la désinstallation.

3. Cliquez sur **Installer**.

Pour valider l’installation, procédez comme suit :

1. Ouvrez un navigateur et accédez à `https://localhost:<service-port>/healthcheck/`.

    Par défaut, le port de service est 8443 (sauf si vous avez spécifié un autre port).

2. Pour vous assurer que l’écouteur est correctement installé, recherchez les éléments suivants :

   - Si la page de contrôle d’intégrité s’affiche, l’installation de l’écouteur a réussi.

   - Si knownServerCount est égal à 1 ou supérieur, la connexion à Redis est établie.

   - Après avoir attendu quelques minutes et après l’installation d’au moins un agent, vérifiez que le compteur ValuesWritten est incrémenté.

### <a name="install-the-website"></a>Installer le site web

Installez le site web sur l’ordinateur hôte en exécutant le StatsManWebSite.msi (inclus avec [Skype Entreprise Server, Real-Time Statistics Manager (64 bits))](https://www.microsoft.com/download/details.aspx?id=57518) :

1. Passez en revue le contrat de licence et, si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

2. Dans la page suivante, spécifiez les informations suivantes :

   - **Port de service :** Ce port TCP est l’endroit où le site web écoute. Vous pouvez la modifier ultérieurement à l’aide de la liaison du gestionnaire IIS. Pendant l’installation, ce port est autorisé via le pare-feu local.

   - **Installez Dir :** C’est dans ce répertoire que les fichiers binaires seront installés. Vous pouvez le modifier par défaut à l’aide du bouton **Parcourir...** .

   - **AppData Dir :** Ce répertoire est l’emplacement où le dossier Journaux et d’autres données seront stockés. Vous pouvez le modifier à partir de la valeur par défaut. Il ne sera pas supprimé lors de la désinstallation.

3. Cliquez sur **Installer**.

Pour afficher le site web, ouvrez un navigateur et accédez à : `http://<localhost:webport/>`.

Pour afficher uniquement les informations d’intégrité, ouvrez un navigateur et accédez à : `http://localhost:<webport>/healthcheck/`.

Par défaut, le numéro de port web est 8080. Vous pouvez modifier la liaison de port du site web à l’aide du gestionnaire IIS.

Le programme d’installation web ajoute un groupe de sécurité local, appelé StatsManWebSiteUsers. Vous pouvez ajouter des comptes à ce groupe de sécurité pour accorder l’accès au site web.

### <a name="install-the-agents"></a>Installer les agents

Installez un agent sur chaque Skype Entreprise Server que vous souhaitez surveiller en exécutant le StatsManPerfAgent.msi :

1. Passez en revue le contrat de licence et, si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

2. Dans la page suivante, spécifiez les informations suivantes :

   - **Mot de passe du service :** Ce mot de passe est utilisé par l’agent distant pour s’authentifier auprès du service d’écoute.

   - **URI de service :** Cette URL est l’emplacement où réside l’écouteur. Utilisez le `https://name:port` format.

     Vous pouvez utiliser un nom NETBIOS ou un nom de domaine complet. Vous pouvez utiliser le nom qui est également spécifié comme **nom** d’objet ou autre **nom** de sujet du certificat sur le service Écouteur, mais ce n’est pas obligatoire.

   - **Empreinte numérique du service :** Ce certificat SS : est utilisé par l’écouteur. L’Agent utilise cette empreinte numérique pour s’authentifier auprès de l’écouteur. Il n’effectue pas la validation complète des certificats, car il est possible d’utiliser des certificats auto-signés.

   - **Installez Dir :** C’est dans ce répertoire que les fichiers binaires seront installés. Vous pouvez le modifier par défaut à l’aide du bouton **Parcourir...** .

   - **AppData Dir :** Ce répertoire est l’emplacement où le dossier Journaux et le fichier password.txt chiffré sont stockés. Vous pouvez remercier de le modifier à partir de la valeur par défaut. Il ne sera pas supprimé lors de la désinstallation.

3. Cliquez sur **Installer**.

Si vous installez un agent sur de nombreuses machines, vous souhaiterez probablement le faire en mode sans assistance. Par exemple :

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importer la topologie
<a name="BKMK_ImportTopology"> </a>

Une fois le Gestionnaire de statistiques installé et en cours d’exécution, vous devez importer la topologie Skype Entreprise Server afin que le Gestionnaire de statistiques connaisse le site, le pool et le rôle de chaque serveur. Pour importer votre topologie Skype Entreprise Server, vous allez utiliser l’applet de commande [Get-CsPool](/powershell/module/skype/get-cspool) pour récupérer des informations sur chaque pool utilisé dans votre organisation, puis importer ces informations dans le Gestionnaire de statistiques.

Pour importer la topologie Skype Entreprise Server, procédez comme suit :

1. Sur un hôte qui a les applets de commande PowerShell Skype Entreprise Server :

    a. Exécutez la commande suivante :

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. Copiez le fichier « mypoolinfo.xml » sur le serveur qui exécute l’écouteur.

2. Sur l’hôte qui exécute l’écouteur :

   a. Exécutez PowerShell.

   b. Accédez au répertoire sur lequel l’écouteur est installé. La valeur par défaut est :

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

Pour afficher les informations de votre serveur actuellement importé, exécutez le script suivant :

```powershell
.\Get-StatsManServerInfo.ps1
```

Si vous souhaitez surveiller les serveurs qui ne se trouvent pas dans votre topologie Skype Entreprise Server (par exemple, une Exchange Server), vous pouvez effectuer une importation sur un serveur unique sur l’hôte qui exécute l’écouteur. Pour effectuer une importation sur un serveur unique, procédez comme suit :

1. Accédez au répertoire sur lequel l’écouteur est installé. La valeur par défaut est :

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Exécutez la commande suivante :

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Résoudre les problèmes de déploiement
<a name="BKMK_Troubleshoot"> </a>

Si un agent ne parvient pas à démarrer, recherchez les problèmes suivants :

- L’agent est-il inscrit dans le Gestionnaire des statistiques ?

   1. Veillez à suivre les instructions d’importation de la topologie. Voir [Importer la topologie](deploy.md#BKMK_ImportTopology).

   2. Si l’Agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, les nœuds d’un cluster SQL AlwaysOn), vous devez ajouter l’Agent manuellement en suivant les instructions fournies dans [Importer la topologie](deploy.md#BKMK_ImportTopology).

- L’agent peut-il contacter l’écouteur ?

   1. Vérifiez que le service Écouteur est en cours d’exécution.

      S’il n’est pas en cours d’exécution, vérifiez que Redis est en cours d’exécution, puis essayez de redémarrer l’écouteur.

   2. Assurez-vous que le port est ouvert au service Écouteur et que l’ordinateur agent peut communiquer avec le port.

- Pour vous assurer que le Gestionnaire des statistiques collecte des données, vous pouvez vérifier le fichier CSV comme suit.

    La commande suivante récupère les noms de stockage des compteurs :

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    La commande suivante récupère les valeurs des compteurs spécifiés :

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Pour plus d’informations sur tous les événements que vous pouvez voir dans le journal des événements de l’application, consultez [Troubleshoot Statistics Manager pour Skype Entreprise Server](troubleshoot.md).

## <a name="create-a-self-signed-certificate"></a>Créer un certificat auto-signé
<a name="BKMK_SelfCert"> </a>

Microsoft recommande vivement d’utiliser un certificat signé par une autorité de certification approuvée. Toutefois, si vous souhaitez utiliser un certificat auto-signé à des fins de test, procédez comme suit :

1. À partir d’une console PowerShell lorsque vous êtes connecté en tant qu’administrateur, exécutez la commande suivante :

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Tapez  `certlm.msc`. Cela ouvre le Gestionnaire de certificats pour l’ordinateur local.

3. Accédez à **Personnel**, puis ouvrez **Certificats**.

4. Cliquez avec le bouton droit sur **StatsManListener- \> Toutes les tâches - \>Gérer les clés privées...**

5. Cliquez sur **Ajouter**.

6. Dans la zone **Entrer les noms d’objets à sélectionner, tapez** le texte suivant : Service réseau

7. Cliquez sur **OK**.

8. Sous **contrôle total**, décocher la case **Autoriser** . (Seul l’accès en lecture est nécessaire.)

9. Cliquez sur **OK**.

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_SelfCert"> </a>

Pour plus d’informations, voir les rubriques suivantes :

- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)

- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)

- [Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)
