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
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712766"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="54198-103">Azure Sentinel et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54198-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54198-104">Azure Sentinel dispose désormais d'un connecteur intégré.</span><span class="sxs-lookup"><span data-stu-id="54198-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="54198-105">Pour plus d'informations, voir [Connecter les journaux d'Office 365 à Azure Sentinel](/azure/sentinel/connect-office-365) .</span><span class="sxs-lookup"><span data-stu-id="54198-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="54198-106">Il s'agit de la méthode recommandée pour collecter ces journaux et elle remplace les méthodes de collecte décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="54198-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="54198-107">Teams joue un rôle central dans la communication et le partage des données dans le cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54198-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="54198-108">Étant donné que le service Teams s’accompagne de nombreuses technologies sous-jacentes dans le cloud, celui-ci peut tirer parti d’une analyse humaine et automatisée.</span><span class="sxs-lookup"><span data-stu-id="54198-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="54198-109">Cela s'applique à la fois au *repérage dans les journaux* et à la *surveillance en temps réel des réunions*.</span><span class="sxs-lookup"><span data-stu-id="54198-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="54198-110">Azure Sentinel offre aux administrateurs ces solutions.</span><span class="sxs-lookup"><span data-stu-id="54198-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="54198-111">Vous avez besoin d’un rappel sur Azure Sentinel ?</span><span class="sxs-lookup"><span data-stu-id="54198-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="54198-112">[Cet article](/azure/sentinel/overview) est exactement ce qu'il faut.</span><span class="sxs-lookup"><span data-stu-id="54198-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="54198-113">Journaux d’activité Sentinel et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54198-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="54198-114">Cet article traite de la collecte des journaux d’activité Teams dans Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="54198-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="54198-115">Il permet aux administrateurs d’assurer la gestion de la sécurité dans un emplacement unique.</span><span class="sxs-lookup"><span data-stu-id="54198-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="54198-116">Cela inclut la gestion :</span><span class="sxs-lookup"><span data-stu-id="54198-116">This includes managing:</span></span>

- <span data-ttu-id="54198-117">Appareils tiers</span><span class="sxs-lookup"><span data-stu-id="54198-117">Third-party devices</span></span>
- <span data-ttu-id="54198-118">Protection Microsoft contre les menaces</span><span class="sxs-lookup"><span data-stu-id="54198-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="54198-119">Charges de travail Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="54198-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="54198-120">Les livres de travail et les livres d'exécution Sentinel peuvent rendre la surveillance de la sécurité *systématique*.</span><span class="sxs-lookup"><span data-stu-id="54198-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="54198-121">La première étape de ce processus consiste à collecter les journaux nécessaires à l’analyse.</span><span class="sxs-lookup"><span data-stu-id="54198-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="54198-122">Plusieurs abonnements Microsoft 365 peuvent être exposés dans la même instance d’Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="54198-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="54198-123">Cela permet de [surveillance en temps réel](/azure/sentinel/livestream) et de le repérage de menaces dans les fichiers journaux historiques.</span><span class="sxs-lookup"><span data-stu-id="54198-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="54198-124">Les administrateurs pourront repérer à l’aide des [requêtes de ressources croisées](/azure/azure-monitor/log-query/cross-workspace-query), au sein d’un même groupe de ressources, au sein de groupes de ressources ou dans un autre abonnement.</span><span class="sxs-lookup"><span data-stu-id="54198-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="54198-125">Étape 1 : collecter les journaux Teams : activer les journaux d’audit dans Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="54198-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="54198-126">Étant donné que Teams enregistre l'activité par le biais de Microsoft 365, les journaux d'audit ne sont pas collectés par défaut.</span><span class="sxs-lookup"><span data-stu-id="54198-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="54198-127">Activez cette fonctionnalité en [procédant comme suit](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="54198-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="54198-128">Les données relatives de Teams sont collectées dans l'audit Microsoft 365 sous *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="54198-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="54198-129">Étape 2 : connecter les journaux Office 365 à Microsoft Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="54198-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="54198-130">Microsoft Azure Sentinel offre un connecteur intégré pour les journaux Office 365, qui vous permet d’ingérer les données Teams dans Azure Sentinel avec d’autres données Office 365.</span><span class="sxs-lookup"><span data-stu-id="54198-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="54198-131">Dans Azure Sentinel, activez le connecteur de données Office 365.</span><span class="sxs-lookup"><span data-stu-id="54198-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="54198-132">Pour plus d’informations, voir la [documentation Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="54198-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="54198-133">Requêtes KQL utiles pour le repérage</span><span class="sxs-lookup"><span data-stu-id="54198-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="54198-134">Utilisez ces requêtes pour vous familiariser avec vos données et l’environnement Teams.</span><span class="sxs-lookup"><span data-stu-id="54198-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="54198-135">Il est recommandé de connaître l’apparence et le comportement de l’environnement afin de reconnaître les activités suspectes.</span><span class="sxs-lookup"><span data-stu-id="54198-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="54198-136">À partir de là, vous pouvez vous brancher au repérage de menaces.</span><span class="sxs-lookup"><span data-stu-id="54198-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="54198-137">Requête utilisateur externe fédérée</span><span class="sxs-lookup"><span data-stu-id="54198-137">Federated external users query</span></span>

<span data-ttu-id="54198-138">Obtenez la liste des sites Teams qui ont des utilisateurs externes fédérés.</span><span class="sxs-lookup"><span data-stu-id="54198-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="54198-139">Ces utilisateurs disposent d'un nom de domaine / suffixe UPN qui n'appartient pas à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="54198-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="54198-140">Dans cet exemple de requête, l’organisation possède contoso.com.</span><span class="sxs-lookup"><span data-stu-id="54198-140">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="54198-141">Pour en savoir plus sur les types d’accès externe et invité dans Teams, consultez [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md)ou la section [Types de participants](teams-security-guide.md#participant-types) du Guide sur la sécurité Teams.</span><span class="sxs-lookup"><span data-stu-id="54198-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="54198-142">Les personnes qui ont récemment rejoint/dont le rôle a changé</span><span class="sxs-lookup"><span data-stu-id="54198-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="54198-143">Interrogez un utilisateur spécifique pour vérifier s’il a été ajouté à un canal Teams au cours des sept derniers jours ou dans une semaine :</span><span class="sxs-lookup"><span data-stu-id="54198-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="54198-144">Déterminer si le rôle d’un utilisateur a changé pour une équipe au cours des sept derniers jours :</span><span class="sxs-lookup"><span data-stu-id="54198-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="54198-145">Utilisateurs externes provenant d’organisations inconnues ou nouvelles</span><span class="sxs-lookup"><span data-stu-id="54198-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="54198-146">Dans Teams, vous pouvez ajouter des utilisateurs externes à votre environnement ou canaux.</span><span class="sxs-lookup"><span data-stu-id="54198-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="54198-147">Les organisations ont souvent un nombre limité de partenariats clés et ajoutent des utilisateurs parmi ces partenaires.</span><span class="sxs-lookup"><span data-stu-id="54198-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="54198-148">Cet KQL examine les utilisateurs externes ajoutés à des équipes qui proviennent d’organisations qui n’ont pas encore été consultées ou ajoutées.</span><span class="sxs-lookup"><span data-stu-id="54198-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="54198-149">Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="54198-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="54198-150">Utilisateurs externes ajoutés et supprimés</span><span class="sxs-lookup"><span data-stu-id="54198-150">External users who were added and then removed</span></span>

<span data-ttu-id="54198-151">Les intrus disposant d’un niveau d’accès existant peuvent ajouter un nouveau compte externe à Teams pour accéder aux données et les exfiltrer.</span><span class="sxs-lookup"><span data-stu-id="54198-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="54198-152">Ils peuvent également supprimer rapidement cet utilisateur afin de masquer le fait qu’il ait rendu l’accès.</span><span class="sxs-lookup"><span data-stu-id="54198-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="54198-153">Cette requête recherche les comptes externes ajoutés à Teams et supprimés rapidement pour vous permettre d’identifier le comportement suspect.</span><span class="sxs-lookup"><span data-stu-id="54198-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="54198-154">Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="54198-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="54198-155">Nouveau bot ou application ajouté</span><span class="sxs-lookup"><span data-stu-id="54198-155">New bot or application added</span></span>

<span data-ttu-id="54198-156">Teams peut inclure des applications ou des bots dans une équipe pour étendre l’ensemble de fonctionnalités (y compris les applications et bots personnalisés).</span><span class="sxs-lookup"><span data-stu-id="54198-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="54198-157">Dans certains cas, une application ou un bot peut être utilisé pour établir une *persistance* dans Teams sans avoir besoin d’un compte d’utilisateur et d’accéder à des fichiers et d’autres données.</span><span class="sxs-lookup"><span data-stu-id="54198-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="54198-158">Cette requête permet de repérer les applications ou les bots qui sont nouveaux pour Teams.</span><span class="sxs-lookup"><span data-stu-id="54198-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="54198-159">Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="54198-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="54198-160">Comptes d’utilisateur propriétaires d’un grand nombre d’équipes</span><span class="sxs-lookup"><span data-stu-id="54198-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="54198-161">Les attaquants qui cherchent à élever leurs privilèges peuvent s'attribuer les privilèges de propriétaire d'un grand nombre d'équipes diverses.</span><span class="sxs-lookup"><span data-stu-id="54198-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="54198-162">*Généralement,*, les utilisateurs créent et possèdent quelques équipes autour de sujets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="54198-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="54198-163">Cette requête KQL recherche un comportement suspect.</span><span class="sxs-lookup"><span data-stu-id="54198-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="54198-164">Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span><span class="sxs-lookup"><span data-stu-id="54198-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="54198-165">Nombreuses suppressions d’équipe effectuées par un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="54198-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="54198-166">Les agresseurs peuvent provoquer des interruptions et compromettre les projets et les données en supprimant plusieurs équipes.</span><span class="sxs-lookup"><span data-stu-id="54198-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="54198-167">Étant donné que les équipes sont généralement supprimées par les propriétaires individuels, une suppression centrale de nombreuses équipes peut être un signe de problème.</span><span class="sxs-lookup"><span data-stu-id="54198-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="54198-168">Ce KQL recherche les utilisateurs individuels qui suppriment plusieurs équipes.</span><span class="sxs-lookup"><span data-stu-id="54198-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="54198-169">Pour plus d’informations, voir la requête dans le [hub git de la communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span><span class="sxs-lookup"><span data-stu-id="54198-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="54198-170">Développez vos opportunités de repérage de menaces</span><span class="sxs-lookup"><span data-stu-id="54198-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="54198-171">Vous pouvez utiliser la combinaison de requêtes à partir de ressources telles qu’Azure Active Directory (Azure AD) ou d’autres charges de travail Office 365 avec des requêtes Teams.</span><span class="sxs-lookup"><span data-stu-id="54198-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="54198-172">Par exemple, combinez la détection de modèles suspects dans Azure AD SigninLogs et utilisez ce résultat lors du repérage pour les propriétaires d’équipe.</span><span class="sxs-lookup"><span data-stu-id="54198-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

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

<span data-ttu-id="54198-173">De plus, vous pouvez rendre les détections SigninLogs spécifiques à Teams en ajoutant un filtre pour les connexions basées sur Teams uniquement à l’aide des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="54198-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="54198-174">Pour aider à expliquer l'utilisation de l'*endroit où AppDisplayName possède Teams* plus loin, le KQL que vous voyez ci-dessous démontre une connexion réussie à partir d'une adresse IP avec l'échec à partir d'une adresse IP différente, mais limité *uniquement* aux connexions à Teams :</span><span class="sxs-lookup"><span data-stu-id="54198-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="54198-175">Informations et mises à jour importantes</span><span class="sxs-lookup"><span data-stu-id="54198-175">Important information and updates</span></span>

<span data-ttu-id="54198-176">**Nous vous remercions pour la collaboration au contenu, Pete Bryan, Nicholas DiCola et Matthew Martin.**</span><span class="sxs-lookup"><span data-stu-id="54198-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="54198-177">Pete Bryan, et les personnes avec lesquelles il collabore, continuent de développer des requêtes de détection et de repérage pour Teams.</span><span class="sxs-lookup"><span data-stu-id="54198-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="54198-178">Restez en contact avec ce référentiel [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="54198-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="54198-179">Surveillez les mises à jour de l’[analyseur](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) et [ application logique](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) utilisés dans cet article.</span><span class="sxs-lookup"><span data-stu-id="54198-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="54198-180">Vous pouvez également participer (et contribuer) à la [communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki).</span><span class="sxs-lookup"><span data-stu-id="54198-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="54198-181">Nous recherchons activement des commentaires sur cet article, alors veuillez utiliser l'option de commentaires ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="54198-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="54198-182">Merci et bon repérage.</span><span class="sxs-lookup"><span data-stu-id="54198-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="54198-183">Inscrire votre application dans Azure AD</span><span class="sxs-lookup"><span data-stu-id="54198-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="54198-184">Activer ou désactiver la recherche dans le journal d’audit</span><span class="sxs-lookup"><span data-stu-id="54198-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="54198-185">Qu’est-ce que Azure Sentinel ?</span><span class="sxs-lookup"><span data-stu-id="54198-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
