---
title: Azure Sentinel et Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conseils de sécurité et apprentissage pour les administrateurs informatiques sur l'utilisation de Sentinel pour surveiller et repérer les menaces qui peuvent survenir dans Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cf7d4e9670d8ea282105eaa057347fa7e9f6dac
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822993"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel et Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel dispose désormais d'un connecteur intégré. Pour plus d'informations, voir [Connecter les journaux d'Office 365 à Azure Sentinel](/azure/sentinel/connect-office-365) . Il s'agit de la méthode recommandée pour collecter ces journaux et elle remplace les méthodes de collecte décrites ci-dessous.

Teams joue un rôle central dans la communication et le partage des données dans le cloud Microsoft 365. Étant donné que le service Teams s’accompagne de nombreuses technologies sous-jacentes dans le cloud, celui-ci peut tirer parti d’une analyse humaine et automatisée. Cela s'applique à la fois au *repérage dans les journaux* et à la *surveillance en temps réel des réunions*. Azure Sentinel offre aux administrateurs ces solutions.

> [!NOTE]
> Vous avez besoin d’un rappel sur Azure Sentinel ? [Cet article](/azure/sentinel/overview) est exactement ce qu'il faut.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Journaux d’activité Sentinel et Microsoft Teams

Cet article traite de la collecte des journaux d’activité Teams dans Azure Sentinel.

Sentinel permet aux administrateurs de gérer la sécurité en un seul endroit. Cela inclut la gestion :

- Appareils tiers
- Protection Microsoft contre les menaces
- Charges de travail Microsoft 365

Les livres de travail et les livres d'exécution Sentinel peuvent rendre la surveillance de la sécurité *systématique*. La première étape de ce processus consiste à collecter les journaux nécessaires à l’analyse.

> [!NOTE]
> Plusieurs abonnements Microsoft 365 peuvent être exposés dans la même instance d’Azure Sentinel. Cela permet de [surveillance en temps réel](/azure/sentinel/livestream) et de le repérage de menaces dans les fichiers journaux historiques. Les administrateurs pourront repérer à l’aide des [requêtes de ressources croisées](/azure/azure-monitor/log-query/cross-workspace-query), au sein d’un même groupe de ressources, au sein de groupes de ressources ou dans un autre abonnement.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Étape 1 : collecter les journaux Teams : activer les journaux d’audit dans Microsoft 365

Étant donné que Teams enregistre l'activité par le biais de Microsoft 365, les journaux d'audit ne sont pas collectés par défaut. Activez cette fonctionnalité en [procédant comme suit](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Les données relatives de Teams sont collectées dans l'audit Microsoft 365 sous *Audit.General*.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Étape 2 : connecter les journaux Office 365 à Microsoft Azure Sentinel

Microsoft Azure Sentinel offre un connecteur intégré pour les journaux Office 365, qui vous permet d’ingérer les données Teams dans Azure Sentinel avec d’autres données Office 365.
 
Dans Azure Sentinel, activez le connecteur de données Office 365. Pour plus d’informations, voir la [documentation Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Requêtes KQL utiles pour le repérage

Utilisez ces requêtes pour vous familiariser avec vos données et l’environnement Teams. Il est recommandé de connaître l’apparence et le comportement de l’environnement afin de reconnaître les activités suspectes. À partir de là, vous pouvez vous brancher au repérage de menaces.

### <a name="federated-external-users-query"></a>Requête utilisateur externe fédérée

Obtenez la liste des sites Teams qui ont des utilisateurs externes fédérés. Ces utilisateurs disposent d'un nom de domaine / suffixe UPN qui n'appartient pas à votre organisation.

Dans cet exemple de requête, l’organisation possède contoso.com.

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> Pour en savoir plus sur les types d’accès externe et invité dans Teams, consultez [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md)ou la section [Types de participants](teams-security-guide.md#participant-types) du Guide sur la sécurité Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Les personnes qui ont récemment rejoint/dont le rôle a changé

Interrogez un utilisateur spécifique pour vérifier s’il a été ajouté à un canal Teams au cours des sept derniers jours ou dans une semaine :

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Déterminer si le rôle d’un utilisateur a changé pour une équipe au cours des sept derniers jours :

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Utilisateurs externes provenant d’organisations inconnues ou nouvelles

Dans Teams, vous pouvez ajouter des utilisateurs externes à votre environnement ou canaux. Les organisations ont souvent un nombre limité de partenariats clés et ajoutent des utilisateurs parmi ces partenaires. Cet KQL examine les utilisateurs externes ajoutés à des équipes qui proviennent d’organisations qui n’ont pas encore été consultées ou ajoutées.

Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).

### <a name="external-users-who-were-added-and-then-removed"></a>Utilisateurs externes ajoutés et supprimés

Les intrus disposant d’un niveau d’accès existant peuvent ajouter un nouveau compte externe à Teams pour accéder aux données et les exfiltrer. Ils peuvent également supprimer rapidement cet utilisateur afin de masquer le fait qu’il ait rendu l’accès. Cette requête recherche les comptes externes ajoutés à Teams et supprimés rapidement pour vous permettre d’identifier le comportement suspect.

Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).

### <a name="new-bot-or-application-added"></a>Nouveau bot ou application ajouté

Teams peut inclure des applications ou des bots dans une équipe pour étendre l’ensemble de fonctionnalités (y compris les applications et bots personnalisés). Dans certains cas, une application ou un bot peut être utilisé pour établir une *persistance* dans Teams sans avoir besoin d’un compte d’utilisateur et d’accéder à des fichiers et d’autres données. Cette requête permet de repérer les applications ou les bots qui sont nouveaux pour Teams.

Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Comptes d’utilisateur propriétaires d’un grand nombre d’équipes

Les attaquants qui cherchent à élever leurs privilèges peuvent s'attribuer les privilèges de propriétaire d'un grand nombre d'équipes diverses. *Généralement,*, les utilisateurs créent et possèdent quelques équipes autour de sujets spécifiques. Cette requête KQL recherche un comportement suspect.

Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).

### <a name="many-team-deletions-by-a-single-user"></a>Nombreuses suppressions d’équipe effectuées par un seul utilisateur

Les agresseurs peuvent provoquer des interruptions et compromettre les projets et les données en supprimant plusieurs équipes. Étant donné que les équipes sont généralement supprimées par les propriétaires individuels, une suppression centrale de nombreuses équipes peut être un signe de problème. Ce KQL recherche les utilisateurs individuels qui suppriment plusieurs équipes.

Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).

### <a name="expanding-your-threat-hunting-opportunities"></a>Développez vos opportunités de repérage de menaces

Vous pouvez utiliser la combinaison de requêtes à partir de ressources telles qu’Azure Active Directory (Azure AD) ou d’autres charges de travail Office 365 avec des requêtes Teams. Par exemple, combinez la détection de modèles suspects dans Azure AD SigninLogs et utilisez ce résultat lors du repérage pour les propriétaires d’équipe.

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

De plus, vous pouvez rendre les détections SigninLogs spécifiques à Teams en ajoutant un filtre pour les connexions basées sur Teams uniquement à l’aide des éléments suivants :

```Kusto
| where AppDisplayName has 'Teams'
```

Pour aider à expliquer l'utilisation de l'*endroit où AppDisplayName possède Teams* plus loin, le KQL que vous voyez ci-dessous démontre une connexion réussie à partir d'une adresse IP avec l'échec à partir d'une adresse IP différente, mais limité *uniquement* aux connexions à Teams :

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a>Informations et mises à jour importantes

**Nous vous remercions pour la collaboration au contenu, Pete Bryan, Nicholas DiCola et Matthew Martin.** Pete Bryan, et les personnes avec lesquelles il collabore, continuent de développer des requêtes de détection et de repérage pour Teams.

Restez en contact avec ce référentiel [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/) pour les mises à jour.

Surveillez les mises à jour de l’[analyseur](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) et [ application logique](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) utilisés dans cet article.

Vous pouvez également participer (et contribuer) à la [communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki). Nous recherchons activement des commentaires sur cet article, alors veuillez utiliser l'option de commentaires ci-dessous. Merci et bon repérage.

[Inscrire votre application dans Azure AD](/skype-sdk/trusted-application-api/docs/registrationinazureactivedirectory)

[Activer ou désactiver la recherche dans le journal d’audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Qu’est-ce que Azure Sentinel ?](/azure/sentinel/overview)
