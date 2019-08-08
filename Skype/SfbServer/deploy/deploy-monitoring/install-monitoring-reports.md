---
title: Installer des rapports de surveillance dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Résumé: Découvrez comment installer un service qui générera des rapports d’analyse dans Skype entreprise Server.'
ms.openlocfilehash: 765c7a13b965b8701de6bc70782a9d7a8963a429
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239980"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installer des rapports de surveillance dans Skype entreprise Server
 
**Résumé:** Découvrez comment installer un service qui générera des rapports d’analyse dans Skype entreprise Server.
  
Les rapports de surveillance de Skype entreprise Server vous fournissent des informations sur la qualité et la quantité des sessions de communication qui interviennent au sein de votre organisation. 
  
## <a name="install-monitoring-reports"></a>Installer des rapports de surveillance

Les rapports d’analyse ne sont pas automatiquement installés lors de l’installation de Skype entreprise Server. au lieu de cela, vous devez installer des rapports de surveillance séparément et seulement après l’installation de Skype entreprise Server sur l’ordinateur.
  
> [!NOTE]
> Il est recommandé d’installer les rapports de surveillance sur le même ordinateur que celui sur lequel la base de données de surveillance est installée. Cela simplifie le processus d’attribution des autorisations d’accès aux rapports : l’installation des rapports de surveillance sur l’ordinateur qui héberge le magasin d’analyse signifie qu’il n’est pas nécessaire de configurer les autorisations qui permettent à une base de données sur un premier ordinateur d’interagir avec le service Reporting Services exécuté sur un autre ordinateur. 
  
Les rapports de surveillance de Skype entreprise Server incluent plus de 30 rapports conçus pour fournir des informations détaillées sur les conférences, les sessions de messagerie instantanée d’égal à égal, les inscriptions des utilisateurs, l’application de groupe de réponse, etc. Pour la version 2013, les rapports de surveillance de Skype entreprise Server incluent un certain nombre d’améliorations:
  
- **Nouveaux rapports de qualité de la voix**. Ces nouveaux rapports incluent le [rapport Comparaison de qualité multimédia dans Skype entreprise Server](../../manage/health-and-monitoring/comparison.md), qui compare la qualité entre les différents types d’appels (par exemple, entre les appels câblés et les appels sans fil). le [rapport de temps de participation à la Conférence dans Skype entreprise Server](../../manage/health-and-monitoring/join-time-report.md)vous donne des informations sur la durée nécessaire pour permettre aux utilisateurs de participer à une conférence. 
    
- **Rapports améliorés pour l’analyse et la résolution des problèmes des sessions de partage vidéo et d’application.** le [rapport synthèse sur la qualité multimédia de Skype entreprise Server](../../manage/health-and-monitoring/summary.md) vous permet d’analyser les appels vidéo et de partage d’application, tandis que le [rapport sur les performances du serveur dans Skype entreprise Server](../../manage/health-and-monitoring/server-performance.md) indique les performances des serveurs qui les génèrent. invoqu. Les métriques de partage d’application et de vidéo sont également signalées par le [rapport détaillé de la session d’égal à égal dans Skype entreprise Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) et le [rapport Détails de la Conférence dans Skype entreprise Server](../../manage/health-and-monitoring/detail-report.md).
    
- **Performances améliorées des rapports**. Ces améliorations incluent un temps de réponse et d’extraction des données plus court, ainsi qu’une navigation plus rapide et plus facile dans les rapports.
    
D’autres informations sur chaque rapport sont disponibles dans la documentation des rapports de surveillance.
  
> [!NOTE]
> Il existe un autre rapport-sous-état d’appels QoE-fourni dans Skype entreprise Server. Toutefois, ce rapport est principalement destiné à un usage interne et non à un accès direct. 
  
Il existe deux façons d’installer des rapports d’analyse de Skype entreprise Server: vous pouvez utiliser l’Assistant Déploiement de Skype entreprise Server ou utiliser un script Windows PowerShell inclus dans les fichiers d’installation de Skype entreprise Server. Quelle que doit la méthode utilisée pour installer les rapports, vous devez d’abord vous assurer que vous :
  
- avez le droit d’ajouter un rôle de base de données à un compte d’utilisateur dans la base de données de surveillance ;
    
- détenez le rôle Gestionnaire de contenu dans SQL Server Reporting Services. Ce rôle vous donne le droit de déployer des rapports sur SQL Server Reporting Services.
    
Pour installer les rapports de surveillance à l’aide de l’Assistant Déploiement, procédez comme suit :
  
1. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Assistant Déploiement de Skype entreprise Server**.
    
2. Dans l’Assistant Déploiement, cliquez sur **Déployer les rapports de surveillance** afin de démarrer l’Assistant Déploiement des rapports de surveillance.
    
3. Dans l’Assistant Déploiement des rapports de surveillance, dans la page **Spécifier une base de données de surveillance**, vérifiez que le nom de domaine complet de l’ordinateur qui héberge votre magasin d’analyse apparaît dans la liste déroulante **Base de données de surveillance**. (Si vous avez plusieurs magasins d’analyse, vous devez sélectionner le serveur approprié dans la liste déroulante.) Vérifiez que l’instance SQL Server correcte apparaît dans la zone **Instance SQL Server Reporting Services (SSRS)** (par exemple, **atl-sql-001.litwareinc.com/archinst**), puis cliquez sur **Suivant**.
    
4. Dans la page **Spécifier des informations d’identification**, dans la zone **Nom d’utilisateur**, tapez le nom de domaine et le nom d’utilisateur du compte à utiliser pour accéder aux rapports de surveillance (par exemple, **litwareinc\kenmyer**). Si vous n’utilisez pas le format domaine\nom d’utilisateur, une erreur se produit.
    
    Tapez le mot de passe du compte d’utilisateur dans la zone **Mot de passe**, puis cliquez sur **Suivant**. Notez qu’aucun droit spécial n’est requis pour ce compte. Le nom de connexion et les autorisations de base de données requis sont octroyés automatiquement au compte une fois l’installation terminée.
    
5. Dans la page **Spécifier un groupe en lecture seule**, entrez le nom d’un groupe de sécurité qui disposera d’un accès en lecture seule à SQL Server Reporting Services dans la zone de groupe Utilisateur. Par exemple, pour octroyer aux administrateurs un accès en lecture seule aux rapports, entrez **RTCUniversalReadOnlyAdmins**. Cliquez sur **Suivant**.
    
6. Dans la page **Exécution de commandes**, cliquez sur **Terminer**.
    
La surveillance des rapports peut également être installée à partir de Skype entreprise Server Management Shell en exécutant le script DeployReports. ps1; Ce script Windows PowerShell est disponible dans le \<dossier installation Location\>\Skype pour Business Server 2015 \ Deployment\Setup. Pour installer des rapports d’analyse à l’aide de DeployReports. ps1, tapez une commande semblable à la suivante à l’invite Management Shell:
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Les paramètres utilisés dans la commande précédente sont décrits dans le tableau suivant :
  
|**Nom du paramètre**|**Obligatoire**|**Description**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Oui  <br/> |Compte d’utilisateur (au format domaine\nomUtilisateur) utilisé pour accéder au magasin d’analyse ; par exemple :  <br/> ```-storedUserName "litwareinc\kenmyer"```Ce compte doit avoir les autorisations SQL Server et SQL Server Reporting Services préalablement spécifiées, ou le script échoue.  <br/> |
|storedPassword  <br/> |Oui  <br/> |Mot de passe du compte d’utilisateur utilisé pour accéder au magasin d’analyse.  <br/> |
|readOnlyGroupName  <br/> |Non  <br/> |Domaine ou groupe de sécurité local dont les membres disposent d’un accès en lecture seule aux rapports de surveillance. Notez que le script échoue si le groupe spécifié n’existe pas. Si vous décidez ultérieurement de révoquer ces autorisations ou si vous décidez d’octroyer à d’autres utilisateurs ou groupes des autorisations d’accès, vous pouvez le faire à l’aide du Gestionnaire de rapports SQL Service Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |Non  <br/> |Instance SQL Server qui héberge le service de rapport. L’instance de création de rapports doit être spécifiée à l’aide du nom de domaine complet du serveur de rapports ; par exemple :<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Si ce paramètre n’est pas inclus, le script suppose que les services de création de rapports sont hébergés par la même instance SQL Server qui héberge la base de données de surveillance.  <br/> |
|monitoringDatabaseId  <br/> |Non  <br/> |Identité de service de la base de données de surveillance. Vous pouvez retourner les identités pour vos bases de données de surveillance en exécutant cette commande :<br/> ```Get-CsService -MonitoringDatabase```|
   
Une fois les rapports de surveillance installés, vous devez utiliser l’applet de commande Set-CsReportingConfiguration pour configurer l’URL utilisée pour accéder à ces rapports. Cette tâche peut être exécutée à partir de Skype entreprise Server Management Shell en exécutant la commande Windows PowerShell suivante. Notez qu’il est recommandé, mais pas obligatoire, d’utiliser le protocole HTTPS pour configurer l’URL des rapports :
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Dans la commande précédente, la propriété ReportingUrl doit avoir la valeur de l’URL du Gestionnaire de rapports utilisé par SQL Server 2008 R2 Reporting Services. Vous pouvez la déterminer en suivant les étapes ci-après sur l’ordinateur sur lequel SQL Server Reporting Services a été installé :
  
1. Cliquez sur Démarrer, sur Tous les programmes, sur Microsoft SQL Server 2008 R2, sur Outils de configuration, puis sur Gestionnaire de configuration de Reporting Services.
    
2. Dans la boîte de dialogue Connexion relative à la configuration de Reporting Services, vérifiez que le nom de l’ordinateur Reporting Services apparaît dans la zone Nom du serveur. Sélectionnez l’instance SQL Server dans la liste déroulante Instance du serveur de rapports, puis cliquez sur Connecter.
    
3. Dans le Gestionnaire de configuration de Reporting Services, cliquez sur URL du Gestionnaire de rapports. Une ou plusieurs URL doivent apparaître dans le volet URL du Gestionnaire de rapports. Chacune de ces URL peut être utilisée en tant qu’URL de rapports, même si, là encore, il est recommandé d’utiliser le protocole HTTPS pour le paramètre ReportingUrl.
    
Si vous avez configuré une base de données miroir pour votre base de données de surveillance, vous devez également associer les rapports de surveillance à la base de données miroir. Pour plus d’informations, reportez-vous à l’article [associer des rapports d’analyse à une base de données miroir dans Skype entreprise Server](monitoring-reports-with-a-mirror-database.md) .
  

