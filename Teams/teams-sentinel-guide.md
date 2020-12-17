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
localization_priority: Priority
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
ms.openlocfilehash: 4f13cdd1d62a31178f7aed922b3bc55b87cd59db
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701232"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel et Microsoft Teams

Teams joue un rôle central dans la communication et le partage des données dans le cloud Microsoft 365. Étant donné que le service Teams s’accompagne de nombreuses technologies sous-jacentes dans le cloud, celui-ci peut tirer parti d’une analyse humaine et automatisée, non seulement lorsqu’il s’agit de *le repérage dans les journaux*, mais également dans *la surveillance en temps réel des réunions*. Azure Sentinel offre aux administrateurs ces solutions.

> [!NOTE]
> Vous avez besoin d’un rappel sur Azure Sentinel ? [Cet article](https://docs.microsoft.com/azure/sentinel/overview) est exactement ce qu'il faut.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Journaux d’activité Sentinel et Microsoft Teams

Cet article traite de la collecte des journaux d’activité Teams dans Azure Sentinel. En plus d'autoriser les administrateurs à placer la gestion de la sécurité dans un volet de verre (y compris les appareils tiers sélectionnés, protection Microsoft contre les menaces et d’autres charges de travail Microsoft 365), les classeurs sentinelles et runbooks peuvent rendre la surveillance de la sécurité systématique. La première étape de ce processus consiste à collecter les journaux nécessaires à l’analyse.

> [!NOTE]
> Plusieurs abonnements Microsoft 365 peuvent être exposés dans la même instance d’Azure Sentinel. Cela permet de [surveillance en temps réel](https://docs.microsoft.com/azure/sentinel/livestream) et de le repérage de menaces dans les fichiers journaux historiques. Les administrateurs pourront repérer à l’aide des [requêtes de ressources croisées](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), au sein d’un même groupe de ressources, au sein de groupes de ressources ou dans un autre abonnement.

## <a name="step-1-collect-teams-logs"></a>Étape 1 : collecter les journaux Teams

Cette section se compose de trois parties :

1. Activation des journaux d’audit dans **Microsoft 365** (M365).
2. Inscription d’une application dans **Microsoft Azure** pour autoriser l’authentification et l’autorisation pour la collecte des journaux.
3. Inscription de l’abonnement API qui permettra la collecte de journaux via l’API M365 via **PowerShell**.

### <a name="enable-audit-logs-in-m365"></a>Activer les journaux d’audit dans M365

Étant donné que Teams enregistre l’activité via M365, les journaux d’audit ne sont pas collectés par défaut. Pour activer cette fonctionnalité, [procédez comme suit](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). Les données Teams sont collectées dans l’audit M365 sous *Audit.General*.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Inscrire une application dans Microsoft Azure pour la collecte des journaux

> [!TIP]
> Avant de commencer, vous devez vous enregistrer votre **ID d’application/ID client**, et votre **ID du locataire** pour une utilisation ultérieure. Veillez à les capturer au fur et à mesure que vous parcourez les étapes d’inscription ci-dessous. Les deux ID s’affichent.
>- Une fois que vous avez créé votre application, cliquez sur inscription de l’application dans la barre latérale de lancement rapide > Recherchez le nom complet de votre nouvelle application > Copiez l’ID de l’application (client).
>- Cliquez sur vue d’ensemble sur la barre de lancement rapide > copier l’ID d’annuaire (locataire).

Authentifiez et autorisez une application Azure Active Directory (Azure AD) pour collecter des données de journal à partir de l’API.

1. Accédez à votre panneau *Azure AD* dans le portail Azure.
2. Cliquez sur *Inscriptions des applications* dans la barre latérale lancement rapide.
3. Sélectionnez *Nouvelle inscription*.
4. Nommez l’application de collecte de journal Teams, puis cliquez sur *Inscrire*.
5. Cliquez sur le long de ce chemin d’accès : *Autorisations d’API* > *Ajouter une autorisation* > *API de gestion Office 365* > *Autorisations d’application*.
6. Développez flux d’activités et cochez *ActivityFeed.Read*.
7. Sélectionnez *Consentement de l’administrateur général* ici. Cliquez sur Oui lorsque vous êtes invité à confirmer votre signification.
8. Cliquez sur *Certificats et secrets* dans la barre latérale > bouton *Nouvelle clé secrète client*.
9. Dans la fenêtre Nouvelle clé secrète client, entrez une description pour la nouvelle clé secrète client, assurez-vous de choisir « Jamais » pour l’expiration, puis cliquez sur *Ajouter*.

> [!IMPORTANT]
> Il est **critique** de copier la nouvelle clé secrète client dans une entrée du gestionnaire de mots de passe qui s’affiche sous le nom de l’application nouvellement créée. Vous ne serez pas en mesure de revenir sur ce secret une fois la fermeture du panneau Azure (*Panneau* étant le terme azur pour fenêtre).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Inscrire l’API avec PowerShell pour collecter les journaux Teams

La dernière étape de l’installation consiste à collecter et enregistrer l’abonnement API de sorte que vous puissiez recueillir vos données de journal. Pour ce faire, vous pouvez effectuer des appels PowerShell REST à l'API d'activité de gestion M365.

Vous êtes prêt à fournir **ID d’application (client)**, la nouvelle **clé secrète client** votre **domaine d’URL pour M365** et **ID d’annuaire (locataire)** les valeurs dans l’applet de commande PowerShell ci-dessous.

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Étape 2 : déployer un guide opérationnel Sentinel pour réceptionner les journaux Teams

Les guides opérationnels Azure Sentinel (également appelées applications logiques) permettront à Azure d’absorber vos données Teams collectées. L’application logique interroge Office 365 pour rechercher les données d’audit qu’elle écrit dans l’espace de travail Azure Sentinel.

Utilisez [ce](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modèle ARM pour déployer votre guide opérationnel Sentinel.

Éléments à retenir :

1. Vous devez parcourir le modèle ARM et remplacer certaines valeurs par des valeurs adaptées à votre environnement.
2. Vous devez autoriser l’interconnexion des journaux et examiner les résultats dans Azure Sentinel.

   Patientez 5 à 10 minutes, en sachant qu’en l’absence de données au cours des 5 dernières minutes, un message d’erreur s’affiche. Consultez les journaux d’audit et gardez à l’esprit que, comme les informations relatives à Teams se trouvent dans l’audit. Les événements généraux, qui collectent plus que les journaux Teams, apparaissent dans les 5 à 10 minutes sur les systèmes en cours d’utilisation. Si vous utilisez un environnement de texte, veillez à utiliser Teams pour générer la journalisation.

![Graphique montrant les classes d’application logiques.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Explication des actions dans le graphique : 
  </summary>

  • La périodicité est le déclencheur d’application logique qui indique au flux de travail de s’exécuter toutes les heures.
  <p>
• L’action actuelle est très simple et permet d’obtenir l’heure actuelle.
  <p>
• Initialiser la variable crée une variable appelée NextPage et la définit sur 1. Celle-ci sera utilisée plus tard pour gérer la pagination à partir de l’API Office 365.
  <p>
• Initialiser la variable 2 crée une variable vide appelée heure de début.
  <p>
• L’exécution de la requête et des résultats de liste est une action Azure Monitor qui interroge l’espace de travail pour rechercher le dernier journal Office 365 entré à partir de l’application logique.
  <p>
• La condition 4 permet de vérifier si la requête Exécuter la requête et les résultats de liste a renvoyé des données. Pour vérifier si c’est la première fois que l’application logique a été utilisée. Si aucune donnée n’est renvoyée, la variable StartTime est paramétrée sur Maintenant - 24 heures. Si des données sont renvoyées, StartTime est paramétrée sur le dernier enregistrement TimeGenerated. Cette opération permet à la requête de récupérer les données de la dernière entrée jusqu’à présent dans le sondage de l’API Office 365, ou au cours des dernières 24 heures, s’il s’agit de la première exécution.
  <p>
• Initialiser la variable 3 crée une variable appelée AvailableUri. Il s’agit d’une chaîne avec l’URL créée à l’aide de StartTime et CurrentTime comme heures de début et de fin, respectivement.
  <p>
• La condition « Until » est une boucle qui permet à l'application logique de continuer à interroger l'API pour voir s'il y a davantage de données (pagination). Tant que la variable NextPage a la valeur 1, la boucle continue. Plus tard, cette variable sera mise à jour s’il n’y a plus de pages à récupérer.
  <p>
• À l’intérieur de la boucle Until, la première étape HTTP se connecte au AvailableURI. Cet URI renvoie la liste du contenu disponible et de chaque URI de contenu. Pour plus d’informations sur l’utilisation de cette URL, consultez : https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Une fois le contrôle exécuté, assurez-vous que les données sont renvoyées. La condition vérifie si la longueur du corps est 0. Si c’est le cas, il n’y a pas de données à écrire dans l’analytique des journaux d'activité. Si la valeur est supérieure à 0, il y a des données à traiter.
  <p>
• Si des données sont détectées, elles doivent être traitées ensuite. L’analyse JSON définit un schéma des données renvoyées. Cela permet aux applications logiques d’utiliser les données analysées en tant que contenu dynamique dans les étapes ultérieures.
  <p>
• Étant donné que la liste renvoyée des données disponibles est une matrice, une pour chaque action est utilisée pour parcourir la liste de contenu disponible.
  <p>
• L’étape suivante consiste à saisir le contenu.  Le protocole HTTP est de nouveau utilisé pour obtenir le contentUri (une propriété dynamique créée à partir de l'analyse JSON), qui est l'URL des données à récupérer.
  <p>
• L’analyse JSON permet également d’analyser les données renvoyées. Vous pouvez trouver un exemple de contenu sur cette URL : https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Les données renvoyées sont également une matrice. Une boucle « For Each » peut également être utilisée ici. Dans cette boucle, le flux de travail prend l’élément actuel de données et utilise l’action d’envoi de données pour écrire les données dans les données de l’analytique des journaux d'activité.
  <p>
• Dans la mesure où il peut y avoir plusieurs pages de contenu disponible, une condition est vérifiée si NextPageUri n’est pas NULL. Si la valeur est NULL ou vide, NextPage est définit à 0, ce qui met fin à la boucle Until. S’il contient une URL, la variable AvaibleUri est mise à jour vers cette URL. Ainsi, l’exécution suivante de la boucle Until utilise une URL suivante disponible, et non l’URL de départ.

  </details>

> [!TIP]
> Vous pouvez choisir d’utiliser une fonction *Azure* pour réceptionner ces journaux. si c’est le cas, les informations relatives au déploiement sont [ici](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)ou [ici](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), selon vos préférences.

Lorsque le connecteur (selon les options ci-dessus choisi) est en cours d’exécution, un tableau personnalisée appelée O365API_CL s’affiche dans l’espace de travail Azure Sentinel. Cette opération permet de loger vos journaux Teams.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Étape 3 : utiliser Sentinel pour surveiller Microsoft Teams

L’identité est un vecteur d’attaque important pour surveiller le moment auquel Microsoft Teams est destiné. Dans la mesure où Azure Active Directory (Azure AD) sous-tend le répertoire de Microsoft 365 (qui inclut Teams), il est utile de collecter et de repérer les menaces figurant dans les journaux Azure AD concernant l’authentification, afin de détecter les comportements suspects relatifs à l’identité. Vous pouvez utiliser le connecteur intégré pour extraire les données Azure AD dans Azure Sentinel, et utiliser ces requêtes [détection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) et [repérage](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) pour rechercher les problèmes.

En ce qui concerne les attaques propres à Microsoft Teams, les menaces pesant sur les données (par exemple, Azure Sentinel) permettent également de contrôler celles-ci et de les repérer.

### <a name="create-a-parser-for-your-data"></a>Créer un analyseur pour vos données

La première chose à faire pour déterminer la logique d’un ensemble important de données collectées est de donner du sens à l’analyse. Cette opération s’effectue à l’aide d’une fonction Kusto Query Language (KQL) qui simplifie l’utilisation des données.

> [!NOTE]
> Les fonctions KQL sont des requêtes KQL enregistrées sous la forme d’un type de données appelé « fonction ». Les fonctions KQL possèdent un alias qui peut être entré dans la zone de requête de Sentinel pour réexécuter rapidement la requête. Pour plus d’informations sur les fonctions KQL et la création d’une fonction d’analyse, consultez [cet article de la communauté technique](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 L’analyseur ci-dessous est un exemple personnalisable destiné à sélectionner un sous-ensemble des champs de l’API de gestion d’Office 365 pertinents pour *Teams*. Il existe également un analyseur suggéré [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), mais vous pouvez modifier l’analyseur ci-dessous pour l’adapter à vos besoins et préférences.

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 Enregistrez l’analyseur sous la forme d’une fonction KQL, avec un alias de TeamsData. Elle sera utilisée pour les requêtes à suivre. Pour plus d’informations sur la configuration et l’utilisation d’une fonction KQL comme analyseur, consultez cet [Article de la communauté technique](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helpful-hunting-kql-queries"></a>Requêtes KQL utiles pour le repérage

Utilisez ces requêtes pour vous familiariser avec vos données et l’environnement Teams. Il est recommandé de connaître l’apparence et le comportement de l’environnement afin de reconnaître les activités suspectes. À partir de là, vous pouvez vous brancher au repérage de menaces.

#### <a name="federated-external-users-query"></a>Requête utilisateur externe fédérée

Obtenez la liste des sites Teams qui ont des utilisateurs externes fédérés. Ces utilisateurs disposent d'un nom de domaine / suffixe UPN qui n'appartient *pas* à votre organisation. Dans cet exemple de requête, l’organisation possède contoso.com.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> Pour en savoir plus sur les types d’accès externe et invité dans Teams, consultez [cet article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)ou la section *Types de participants* dans le [Guide de la sécurité Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Les personnes qui ont récemment rejoint/dont le rôle a changé

Interrogez un utilisateur spécifique pour vérifier s’il a été ajouté à un canal Teams au cours des 7 derniers jours ou dans une semaine :

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

Le rôle d’un utilisateur a changé pour une équipe au cours des 7 derniers jours :

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Utilisateurs externes provenant d’organisations inconnues ou nouvelles

Dans Teams, vous pouvez ajouter des utilisateurs externes à votre environnement ou canaux. Les organisations ont souvent un nombre limité de partenariats clés et ajoutent des utilisateurs parmi ces partenaires. Cet KQL examine les utilisateurs externes ajoutés à des équipes qui proviennent d’organisations qui n’ont pas encore été consultées ou ajoutées.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>Utilisateurs externes ajoutés et supprimés

Les intrus disposant d’un niveau d’accès existant peuvent ajouter un nouveau compte externe à Teams pour accéder aux données et les exfiltrer. Ils peuvent également supprimer rapidement cet utilisateur afin de masquer le fait qu’il ait rendu l’accès. Cette requête recherche les comptes externes ajoutés à Teams et supprimés rapidement pour vous permettre d’identifier le comportement suspect.

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>Nouveau bot ou application ajouté

Teams a la possibilité d'inclure des applications ou des bots au sein d'une équipe pour étendre l'ensemble des fonctionnalités. Cela inclut les applications et bots personnalisés. Dans certains cas, une application ou un bot peut être utilisé pour établir une persistance dans Teams sans avoir besoin d’un compte d’utilisateur, mais également d’accéder à des fichiers et d’autres données. Cette requête permet de repérer les applications ou les bots qui sont nouveaux pour Teams.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Comptes d’utilisateur propriétaires d’un grand nombre d’équipes

Les attaquants cherchant à élever leur privilège s’attribuent généralement les privilèges de propriétaire de nombreuses équipes, tandis que, généralement, les utilisateurs normaux créent et possèdent un petit nombre d’équipes centrées sur certains sujets. Cette requête KQL recherche un comportement suspect.

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>Nombreuses suppressions d’équipe effectuées par un seul utilisateur

Les agresseurs peuvent provoquer des interruptions et compromettre les projets et les données en supprimant plusieurs équipes. Les équipes étant généralement supprimées par des propriétaires individuels, une suppression centrale de nombreuses équipes peut poser problème. Ce KQL recherche les utilisateurs individuels qui suppriment plusieurs équipes.

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>Développez vos opportunités de repérage de menaces

Vous pouvez développer votre repérage en combinant des requêtes provenant de ressources telles qu’Azure Active Directory (Azure AD), ou d’autres charges de travail Office 365 avec vos requêtes Teams. Par exemple, vous combinez la détection de modèles suspects dans Azure AD SigninLogs et vous utilisez ces informations pendant la recherche de propriétaires Teams.

```kusto
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
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

De plus, vous pouvez rendre les détections SigninLogs spécifiques à Teams en ajoutant un filtre pour les connexions basées sur Teams uniquement à l’aide des éléments suivants :

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Pour vous aider à expliquer `where AppDisplayName starts with "Microsoft Teams"` plus loin, la KQL ci-dessous montre une connexion réussie à partir d’une adresse IP avec un échec provenant d’une adresse IP différente, mais réservé uniquement aux connexions Teams :

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
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

**Nous vous remercions pour la collaboration au contenu, Pete Bryan, Nicholas DiCola et Matthew Martin.** Pete Bryan et les personnes avec lesquelles il collabore continueront à développer des requêtes de détection et de repérage pour Teams. Veillez donc à rester en contact avec ce référentiel [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) pour les mises à jour.  Surveiller les mises à jour de l’[analyseur](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) et [ application logique](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) utilisés dans cet article. Vous pouvez également participer et contribuer à la [communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki). Merci ! Bon repérage.

[Inscrire votre application dans Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Activer ou désactiver la recherche dans le journal d’audit](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Qu’est-ce que Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)
