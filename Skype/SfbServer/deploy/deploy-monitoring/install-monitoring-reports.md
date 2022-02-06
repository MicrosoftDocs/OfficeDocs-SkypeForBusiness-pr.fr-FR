---
title: Installer des rapports de surveillance dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Résumé : Découvrez comment installer un service qui générera des rapports de surveillance dans Skype Entreprise Server.'
---

# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installer des rapports de surveillance dans Skype Entreprise Server
 
**Résumé :** Découvrez comment installer un service qui générera des rapports de surveillance dans Skype Entreprise Server.
  
Skype Entreprise Server rapports de surveillance vous fournissent une multitude d’informations sur la qualité et la quantité des sessions de communication qui ont lieu dans votre organisation. 
  
## <a name="install-monitoring-reports"></a>Installer des rapports de surveillance

Les rapports de surveillance ne sont pas installés automatiquement lorsque vous installez Skype Entreprise Server ; à la place, vous devez installer les rapports de surveillance séparément et uniquement après l’installation de Skype Entreprise Server sur l’ordinateur.
  
> [!NOTE]
> Il est recommandé d’installer les rapports de surveillance sur le même ordinateur que celui sur lequel la base de données de surveillance est installée. Cela simplifie le processus d’attribution des autorisations d’accès aux rapports : l’installation des rapports de surveillance sur l’ordinateur qui héberge le magasin d’analyse signifie qu’il n’est pas nécessaire de configurer les autorisations qui permettent à une base de données sur un premier ordinateur d’interagir avec le service Reporting Services exécuté sur un autre ordinateur. 
  
Skype Entreprise Server monitoring reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more. Pour la version 2013, les rapports Skype Entreprise Server de surveillance incluent un certain nombre d’améliorations :
  
- **Nouveaux rapports de qualité de la voix**. Ces nouveaux rapports incluent le rapport comparatif de la qualité des médias en [Skype Entreprise Server](../../manage/health-and-monitoring/comparison.md), qui compare la qualité entre les différents types d’appels (par exemple, entre les appels câblés et les appels sans fil) et le rapport de temps d’accès aux conférences [dans Skype Entreprise Server](../../manage/health-and-monitoring/join-time-report.md) , qui fournit des informations sur la durée nécessaire pour que les utilisateurs rejoignent une conférence. 
    
- **Rapports améliorés pour l’analyse et la résolution des problèmes des sessions de partage vidéo et d’application.** Le rapport de synthèse de la qualité des médias dans [Skype Entreprise Server](../../manage/health-and-monitoring/summary.md) permet d’analyser les appels de partage de vidéos et d’applications, tandis que le rapport sur les performances du serveur en [Skype Entreprise Server](../../manage/health-and-monitoring/server-performance.md) détaille les performances des serveurs générant ces appels. Les mesures de partage vidéo et d’application sont désormais également signalées par le rapport détaillé de session P2T dans [Skype Entreprise Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) et le rapport détaillé de conférence [dans Skype Entreprise Server](../../manage/health-and-monitoring/detail-report.md).
    
- **Performances améliorées des rapports**. Ces améliorations incluent un temps de réponse et d’extraction des données plus court, ainsi qu’une navigation plus rapide et plus facile dans les rapports.
    
D’autres informations sur chaque rapport sont disponibles dans la documentation des rapports de surveillance.
  
> [!NOTE]
> Il existe un autre rapport , le sous-rapport des détails des appels QoE, inclus dans Skype Entreprise Server. Toutefois, ce rapport est principalement destiné à un usage interne et non à un accès direct. 
  
Il existe deux façons d’installer Skype Entreprise Server rapports de surveillance : vous pouvez utiliser l’Assistant Déploiement Skype Entreprise Server ou utiliser un script Windows PowerShell inclus dans l’installation Skype Entreprise Server fichiers. Quelle que doit la méthode utilisée pour installer les rapports, vous devez d’abord vous assurer que vous :
  
- avez le droit d’ajouter un rôle de base de données à un compte d’utilisateur dans la base de données de surveillance ;
    
- détenez le rôle Gestionnaire de contenu dans SQL Server Reporting Services. Ce rôle vous donne le droit de déployer des rapports sur SQL Server Reporting Services.
    
Pour installer les rapports de surveillance à l’aide de l’Assistant Déploiement, procédez comme suit :
  
1. Cliquez **sur** Démarrer, **sur** Tous **les programmes, sur Skype Entreprise Server**, puis sur Skype Entreprise Server **Déploiement**.
    
2. Dans l’Assistant Déploiement, cliquez sur **Déployer les rapports de surveillance** afin de démarrer l’Assistant Déploiement des rapports de surveillance.
    
3. Dans l’Assistant Déploiement des rapports de surveillance, dans la page **Spécifier une base de données de surveillance**, vérifiez que le nom de domaine complet de l’ordinateur qui héberge votre magasin d’analyse apparaît dans la liste déroulante **Base de données de surveillance**. (Si vous avez plusieurs magasins d’analyse, vous devez sélectionner le serveur approprié dans la liste déroulante.) Vérifiez que l’instance SQL Server correcte apparaît dans la zone **Instance SQL Server Reporting Services (SSRS)** (par exemple, **atl-sql-001.litwareinc.com/archinst**), puis cliquez sur **Suivant**.
    
4. Dans la page **Spécifier des informations d’identification**, dans la zone **Nom d’utilisateur**, tapez le nom de domaine et le nom d’utilisateur du compte à utiliser pour accéder aux rapports de surveillance (par exemple, **litwareinc\kenmyer**). Si vous n’utilisez pas ce format (domaine \nom d’utilisateur), une erreur se produit.
    
    Tapez le mot de passe du compte d’utilisateur dans la zone **Mot de passe**, puis cliquez sur **Suivant**. Notez qu’aucun droit spécial n’est requis pour ce compte. Le compte se fera automatiquement accorder les autorisations d’accès et de base de données requises une fois l’installation terminée.
    
5. Dans la page **Spécifier un groupe en lecture seule**, entrez le nom d’un groupe de sécurité qui disposera d’un accès en lecture seule à SQL Server Reporting Services dans la zone de groupe Utilisateur. Par exemple, pour octroyer aux administrateurs un accès en lecture seule aux rapports, entrez **RTCUniversalReadOnlyAdmins**. Cliquez sur **Suivant**.
    
6. Dans la page de **Exécution de commandes**, cliquez sur **Terminer**.
    
Les rapports de surveillance peuvent également être installés à partir de Skype Entreprise Server Management Shell en exécutant le DeployReports.ps1 de script ; ce script \<install location\>Windows PowerShell se trouve dans le dossier \Skype Entreprise Server 2015\Deployment\Setup. Pour installer les rapports de surveillance à l’aide de DeployReports.ps1, tapez une commande similaire à la suivante à l’invite Management Shell :
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Les paramètres utilisés dans la commande précédente sont décrits dans le tableau suivant :
  
|**Nom du paramètre**|**Obligatoire**|**Description**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Oui  <br/> |Compte d’utilisateur (au format domaine\nomUtilisateur) utilisé pour accéder au magasin d’analyse ; par exemple :  <br/> ```-storedUserName "litwareinc\kenmyer"```Ce compte doit avoir les autorisations spécifiées précédemment SQL Server et SQL Server Reporting Services autorisations, sinon le script échouera.  <br/> |
|storedPassword  <br/> |Oui  <br/> |Mot de passe du compte d’utilisateur utilisé pour accéder au magasin d’analyse.  <br/> |
|readOnlyGroupName  <br/> |Non  <br/> |Domaine ou groupe de sécurité local dont les membres disposent d’un accès en lecture seule aux rapports de surveillance. Notez que le script échoue si le groupe spécifié n’existe pas. Si vous décidez ultérieurement de révoquer ces autorisations, ou si vous décidez d’octroyer à d’autres utilisateurs ou groupes des autorisations d’accès, vous pouvez le faire à l’aide du Gestionnaire de rapports SQL Service Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |Non  <br/> |Instance SQL Server qui héberge le service de rapport. L’instance de création de rapports doit être spécifiée à l’aide du nom de domaine complet du serveur de rapports ; par exemple :<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Si ce paramètre n’est pas inclus, le script suppose que les services de rapports sont hébergés par la même instance SQL Server qui héberge la base de données de surveillance.  <br/> |
|monitoringDatabaseId  <br/> |Non  <br/> |Identité de service de la base de données de surveillance. Vous pouvez retourner les identités pour vos bases de données de surveillance en exécutant cette commande :<br/> ```Get-CsService -MonitoringDatabase```|
   
Une fois les rapports de surveillance installés, vous devez utiliser la cmdlet New-CsReportingConfiguration pour configurer l’URL utilisée pour accéder à ces rapports. Cette tâche peut être effectuée à partir de l’Skype Entreprise Server Management Shell en exécutant la commande Windows PowerShell suivante. Notez qu’il est recommandé, mais pas obligatoire, d’utiliser le protocole HTTPS pour configurer l’URL des rapports :
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Dans la commande précédente, la propriété ReportingUrl doit avoir la valeur de l’URL du Gestionnaire de rapports utilisé par SQL Server 2008 R2 Reporting Services. Vous pouvez la déterminer en suivant les étapes ci-après sur l’ordinateur sur lequel SQL Server Reporting Services a été installé :
  
1. Cliquez sur Démarrer, sur Tous les programmes, sur Microsoft SQL Server 2008 R2, sur Outils de configuration, puis sur Gestionnaire de configuration de Reporting Services.
    
2. Dans la boîte de dialogue Connexion relative à la configuration de Reporting Services, vérifiez que le nom de l’ordinateur Reporting Services apparaît dans la zone Nom du serveur. Sélectionnez l’instance SQL Server dans la liste déroulante Instance du serveur de rapports, puis cliquez sur Connecter.
    
3. Dans le Gestionnaire de configuration de Reporting Services, cliquez sur URL du Gestionnaire de rapports. Une ou plusieurs URL doivent apparaître dans le volet URL du Gestionnaire de rapports. Chacune de ces URL peut être utilisée en tant qu’URL de rapports, même si, là encore, il est recommandé d’utiliser le protocole HTTPS pour le paramètre ReportingUrl.
    
Si vous avez installé une base de données miroir pour votre base de données de surveillance, vous devez également associer les rapports de surveillance à la base de données miroir. Pour plus [d’informations, voir l’article Associer des rapports de surveillance à Skype Entreprise Server](monitoring-reports-with-a-mirror-database.md) base de données miroir.
  

