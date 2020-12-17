---
title: Gérer le cycle de vie des canaux privés dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer le cycle de vie des canaux privés dans votre organisation.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601659"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="87554-103">Gérer le cycle de vie des canaux privés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87554-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="87554-104">Vous trouverez ici les conseils dont vous avez besoin pour gérer le cycle de vie des [canaux privés](private-channels.md) dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="87554-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87554-105">Si vous utilisez les étapes PowerShell de cet article pour gérer les canaux privés, vous devez installer et utiliser la préversion publique du module Teams PowerShell à partir de la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="87554-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="87554-106">Si vous souhaitez savoir comment installer le module, consultez l’article [Installer Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="87554-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="87554-107">Le dernier module Teams PowerShell disponible au grand public ne prend pas en charge la gestion des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="87554-108">Définir si les membres de l’équipe peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="87554-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="87554-109">Les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="87554-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="87554-110">Pour ce faire, dans l’onglet **Paramètres** de l’équipe, désactivez ou activez **Autoriser les membres à créer des canaux privés**.</span><span class="sxs-lookup"><span data-stu-id="87554-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="87554-111">En tant qu’administrateur, vous pouvez utiliser l’API Graph pour déterminer si les membres peuvent créer des canaux privés dans des équipes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="87554-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="87554-112">Voici un exemple.</span><span class="sxs-lookup"><span data-stu-id="87554-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="87554-113">Définir si les utilisateurs de votre organisation peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="87554-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="87554-114">En tant qu’administrateur, vous pouvez définir des stratégies à l’aide du centre d’administration Microsoft Teams ou de PowerShell pour déterminer les utilisateurs de votre organisation autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87554-115">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87554-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="87554-116">Utilisez des stratégies d’équipe pour définir les utilisateurs de votre organisation autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="87554-117">Si vous souhaitez en savoir plus, consultez l’article [Gérer les stratégies d’équipe dans Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="87554-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87554-118">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="87554-118">Using PowerShell</span></span>

<span data-ttu-id="87554-119">Utilisez **CsTeamsChannelsPolicy** pour définir les utilisateurs de votre organisation autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="87554-120">Définissez le paramètre **AllowPrivateChannelCreation** sur **true** pour permettre aux utilisateurs, auxquels la stratégie est attribuée, de créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="87554-121">Définir le paramètre sur **false** désactive la possibilité de créer des canaux privés pour les utilisateurs auxquels la stratégie est attribuée.</span><span class="sxs-lookup"><span data-stu-id="87554-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="87554-122">Si vous souhaitre en savoir plus, consultez l’article [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="87554-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="87554-123">Créer une canal privé au nom du propriétaire d’une équipe</span><span class="sxs-lookup"><span data-stu-id="87554-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="87554-124">En tant qu’administrateur, vous pouvez utiliser PowerShell ou l’API Graph pour créer un canal privé au nom du propriétaire d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="87554-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="87554-125">Par exemple, vous souhaiterez peut-être le faire si votre organisation souhaite centraliser la création de canaux privés.</span><span class="sxs-lookup"><span data-stu-id="87554-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87554-126">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="87554-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="87554-127">Utiliser l’API Graph</span><span class="sxs-lookup"><span data-stu-id="87554-127">Using Graph API</span></span>

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="87554-128">Obtenez une liste de tous les messages du canal privé</span><span class="sxs-lookup"><span data-stu-id="87554-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="87554-129">Vous souhaiterez peut-être obtenir une liste de tous les messages et réponses publiés sur un canal privé à des fins d’archivage et d’audit.</span><span class="sxs-lookup"><span data-stu-id="87554-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="87554-130">Voici comment utiliser l’API Graph pour ce faire.</span><span class="sxs-lookup"><span data-stu-id="87554-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="87554-131">Rechercher des URL SharePoint pour tous les canaux privés d’une équipe</span><span class="sxs-lookup"><span data-stu-id="87554-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="87554-132">Que vous cherchiez à effectuer une découverte électronique ou une conservation légale sur des fichiers dans un canal privé ou que vous cherchiez à créer une application personnalisée qui place des fichiers dans des canaux privés spécifiques, vous souhaiterez un moyen d’interroger les collections de sites SharePoint uniques qui sont créées pour chaque canal privé.</span><span class="sxs-lookup"><span data-stu-id="87554-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="87554-133">En tant qu’administrateur, vous pouvez utiliser les commandes PowerShell ou de l’API Graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="87554-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87554-134">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="87554-134">Using PowerShell</span></span>

1. <span data-ttu-id="87554-135">Installez et connectez-vous à [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) avec votre compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="87554-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="87554-136">Exécutez les lignes de commande suivantes, dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="87554-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="87554-137">(Vous pouvez facilement trouver l’ID de groupe dans le lien vers l’équipe.)</span><span class="sxs-lookup"><span data-stu-id="87554-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="87554-138">Utiliser l’API Graph</span><span class="sxs-lookup"><span data-stu-id="87554-138">Using Graph API</span></span>

<span data-ttu-id="87554-139">Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="87554-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="87554-140">Utilisez les lignes de commande suivantes pour obtenir la liste des ID de canal privé pour une équipe donnée, dans lesquelles <group_id> est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="87554-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="87554-141">Vous en aurez besoin lors des prochains appels.</span><span class="sxs-lookup"><span data-stu-id="87554-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="87554-142">(Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe).</span><span class="sxs-lookup"><span data-stu-id="87554-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="87554-143">**Demande**</span><span class="sxs-lookup"><span data-stu-id="87554-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="87554-144">**Response**</span><span class="sxs-lookup"><span data-stu-id="87554-144">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. <span data-ttu-id="87554-145">Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la demande suivante, dans laquelle &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="87554-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="87554-146">**Demande**</span><span class="sxs-lookup"><span data-stu-id="87554-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="87554-147">**Response**</span><span class="sxs-lookup"><span data-stu-id="87554-147">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="87554-148">Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé</span><span class="sxs-lookup"><span data-stu-id="87554-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="87554-149">Vous souhaiterez peut-être répertorier les propriétaires et les membres d’un canal privé pour décider si vous devez promouvoir certains membres de ce canal privé au rôle de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="87554-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="87554-150">Cela peut se produire lorsque des propriétaires de canaux privés ont quitté l’organisation et que le canal privé a besoin de l’aide de l’administrateur pour trouver un propriétaire.</span><span class="sxs-lookup"><span data-stu-id="87554-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="87554-151">En tant qu’administrateur, vous pouvez utiliser le centre d’administration Microsoft Teams, PowerShell ou l’API Graph pour effectuer ces actions.</span><span class="sxs-lookup"><span data-stu-id="87554-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87554-152">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87554-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="87554-153">Si vous souhaitez savoir comment gérer les membres de l’équipe à l’aide du centre d’administration Microsoft Teams, consultez l’article [Gérer les équipes dans le centre d’administration Microsoft Teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="87554-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87554-154">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="87554-154">Using PowerShell</span></span>

1. <span data-ttu-id="87554-155">Exécutez les lignes de commande suivantes, dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_name&gt; est le nom du canal.</span><span class="sxs-lookup"><span data-stu-id="87554-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="87554-156">Promouvoir un membre au rôle de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="87554-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="87554-157">Utiliser l’API Graph</span><span class="sxs-lookup"><span data-stu-id="87554-157">Using Graph API</span></span>

<span data-ttu-id="87554-158">Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="87554-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="87554-159">Utilisez les lignes de commande suivantes dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="87554-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="87554-160">**Demande**</span><span class="sxs-lookup"><span data-stu-id="87554-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="87554-161">**Response**</span><span class="sxs-lookup"><span data-stu-id="87554-161">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. <span data-ttu-id="87554-162">Utilisez les lignes de commande suivantes pour promouvoir le membre au rôle de propriétaire, dans lesquelles &lt;group_id&gt;, &lt;channel_id&gt; et &lt;id&gt; sont renvoyés par l’appel précédent.</span><span class="sxs-lookup"><span data-stu-id="87554-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="87554-163">Notez que &lt;id&gt; et &lt;userId&gt; renvoyés par l’appel précédent ne sont pas les mêmes et ne sont pas interchangeables.</span><span class="sxs-lookup"><span data-stu-id="87554-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="87554-164">Assurez-vous d’utiliser &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="87554-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="87554-165">**Demande**</span><span class="sxs-lookup"><span data-stu-id="87554-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="87554-166">**Response**</span><span class="sxs-lookup"><span data-stu-id="87554-166">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a><span data-ttu-id="87554-167">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="87554-167">Related topics</span></span>

- [<span data-ttu-id="87554-168">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="87554-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="87554-169">Utiliser l’API Microsoft Graph pour travailler avec Teams</span><span class="sxs-lookup"><span data-stu-id="87554-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="87554-170">Répertorier les canaux</span><span class="sxs-lookup"><span data-stu-id="87554-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="87554-171">Créer un canal</span><span class="sxs-lookup"><span data-stu-id="87554-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="87554-172">Ajouter un membre au canal</span><span class="sxs-lookup"><span data-stu-id="87554-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="87554-173">Mettre à jour un membre du canal</span><span class="sxs-lookup"><span data-stu-id="87554-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="87554-174">Supprimer un membre du canal</span><span class="sxs-lookup"><span data-stu-id="87554-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
