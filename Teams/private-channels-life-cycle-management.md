---
title: Gérer le cycle de vie des canaux privés dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer le cycle de vie des canaux privés au sein de votre organisation.
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969412"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="40353-103">Gérer le cycle de vie des canaux privés dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="40353-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="40353-104">Vous trouverez ci-dessous les conseils nécessaires pour gérer le cycle de vie des [canaux privés](private-channels.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="40353-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="40353-105">Définir si les membres d’une équipe peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="40353-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="40353-106">Les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans les paramètres d’équipe.</span><span class="sxs-lookup"><span data-stu-id="40353-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="40353-107">Pour ce faire, sous l’onglet **paramètres** de l’équipe, désactivez ou activez l’option **autoriser les membres à créer des canaux privés**.</span><span class="sxs-lookup"><span data-stu-id="40353-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="40353-108">En tant qu’administrateur, vous pouvez utiliser l’API graphique pour contrôler si les membres peuvent créer des canaux privés dans des équipes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="40353-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="40353-109">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="40353-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="40353-110">Définir si les utilisateurs de votre organisation peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="40353-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="40353-111">En tant qu’administrateur, vous pouvez définir des stratégies en utilisant le centre d’administration Microsoft teams ou PowerShell pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="40353-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="40353-112">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="40353-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="40353-113">Les stratégies d’équipe permettent de définir quels utilisateurs de votre organisation peuvent créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="40353-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="40353-114">Pour en savoir plus, voir [gérer les stratégies d’équipes dans teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="40353-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="40353-115">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="40353-115">Using PowerShell</span></span>

<span data-ttu-id="40353-116">Utilisez **CsTeamsChannelsPolicy** pour définir quels utilisateurs de votre organisation peuvent créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="40353-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="40353-117">Définissez le paramètre **AllowPrivateChannelCreation** sur **true** pour autoriser les utilisateurs auxquels la stratégie est affectée pour créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="40353-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="40353-118">Le fait de définir le paramètre sur **false** désactive la possibilité de créer des canaux privés pour les utilisateurs auxquels la stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="40353-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="40353-119">Pour en savoir plus, voir [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="40353-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="40353-120">Créer un canal privé pour le compte d’un propriétaire d’équipe</span><span class="sxs-lookup"><span data-stu-id="40353-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="40353-121">En tant qu’administrateur, vous pouvez utiliser l’API PowerShell ou Graph pour créer un canal privé pour le compte d’un propriétaire d’équipe.</span><span class="sxs-lookup"><span data-stu-id="40353-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="40353-122">Par exemple, vous pouvez procéder de la sorte si votre organisation veut centraliser la création de canaux privés.</span><span class="sxs-lookup"><span data-stu-id="40353-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="40353-123">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="40353-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="40353-124">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="40353-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="40353-125">Obtenir la liste de tous les messages de canal privé</span><span class="sxs-lookup"><span data-stu-id="40353-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="40353-126">Vous pouvez obtenir la liste de tous les messages et réponses publiés dans un canal privé à des fins d’archivage et d’audit.</span><span class="sxs-lookup"><span data-stu-id="40353-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="40353-127">Pour ce faire, vous devez utiliser l’API graphique.</span><span class="sxs-lookup"><span data-stu-id="40353-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="40353-128">Rechercher des URL SharePoint pour tous les canaux privés d’une équipe</span><span class="sxs-lookup"><span data-stu-id="40353-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="40353-129">Que vous souhaitiez exécuter une découverte électronique ou un blocage légal sur des fichiers dans un canal privé ou avoir besoin d’une application métier qui place des fichiers dans des canaux privés spécifiques, vous avez besoin d’un moyen d’interroger les collections de sites SharePoint uniques créées pour chaque canal privé.</span><span class="sxs-lookup"><span data-stu-id="40353-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="40353-130">En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="40353-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="40353-131">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="40353-131">Using PowerShell</span></span>

1. <span data-ttu-id="40353-132">Installez [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) et connectez-vous avec votre compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="40353-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="40353-133">Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="40353-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="40353-134">(Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe.)</span><span class="sxs-lookup"><span data-stu-id="40353-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="40353-135">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="40353-135">Using Graph API</span></span>

<span data-ttu-id="40353-136">Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="40353-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="40353-137">Pour obtenir la liste des ID de canal privé d’une équipe donnée, utilisez la commande suivante, où <group_id> correspond à l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="40353-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="40353-138">Vous en aurez besoin dans les prochains appels.</span><span class="sxs-lookup"><span data-stu-id="40353-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="40353-139">(L’ID du groupe est facilement repérable dans le lien vers l’équipe).</span><span class="sxs-lookup"><span data-stu-id="40353-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="40353-140">**Demande**</span><span class="sxs-lookup"><span data-stu-id="40353-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="40353-141">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="40353-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="40353-142">Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la requête suivante, où &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="40353-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="40353-143">**Demande**</span><span class="sxs-lookup"><span data-stu-id="40353-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="40353-144">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="40353-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="40353-145">Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé</span><span class="sxs-lookup"><span data-stu-id="40353-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="40353-146">Il est possible que vous souhaitiez répertorier les propriétaires et les membres d’un canal privé pour décider si vous avez besoin de promouvoir certains membres du canal privé auprès d’un propriétaire.</span><span class="sxs-lookup"><span data-stu-id="40353-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="40353-147">Cela peut se produire lorsque vous avez des propriétaires de canaux privés qui ont quitté l’organisation et que le canal privé nécessite une aide d’un administrateur pour réclamer la propriété du canal.</span><span class="sxs-lookup"><span data-stu-id="40353-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="40353-148">En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="40353-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="40353-149">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="40353-149">Using PowerShell</span></span>

1. <span data-ttu-id="40353-150">Installez le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) et connectez-vous avec votre compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="40353-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="40353-151">Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et channel_id est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="40353-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="40353-152">**Demande**</span><span class="sxs-lookup"><span data-stu-id="40353-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="40353-153">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="40353-153">**Response**</span></span>

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. <span data-ttu-id="40353-154">Promouvoir un membre en tant que propriétaire ;</span><span class="sxs-lookup"><span data-stu-id="40353-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="40353-155">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="40353-155">Using Graph API</span></span>

<span data-ttu-id="40353-156">Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="40353-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="40353-157">Utilisez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et channel_id est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="40353-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="40353-158">**Demande**</span><span class="sxs-lookup"><span data-stu-id="40353-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="40353-159">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="40353-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="40353-160">Procédez comme suit pour promouvoir le membre auprès d’un propriétaire &lt;,&gt;où &lt;group_id&gt;, channel_id &lt;et&gt; ID sont renvoyés à partir de l’appel précédent.</span><span class="sxs-lookup"><span data-stu-id="40353-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="40353-161">Notez que &lt;l'&gt; ID &lt;et&gt; l’identifiant de l’utilisateur renvoyés par l’appel précédent ne sont pas identiques et ne sont pas interchangeables.</span><span class="sxs-lookup"><span data-stu-id="40353-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="40353-162">Assurez-vous &lt;d'&gt;utiliser ID.</span><span class="sxs-lookup"><span data-stu-id="40353-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="40353-163">**Demande**</span><span class="sxs-lookup"><span data-stu-id="40353-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="40353-164">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="40353-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="40353-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40353-165">Related topics</span></span>

- [<span data-ttu-id="40353-166">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="40353-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="40353-167">Utiliser l’API Microsoft Graph pour travailler avec des équipes</span><span class="sxs-lookup"><span data-stu-id="40353-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="40353-168">Canaux de liste</span><span class="sxs-lookup"><span data-stu-id="40353-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="40353-169">Créer un canal</span><span class="sxs-lookup"><span data-stu-id="40353-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="40353-170">Ajouter un membre au canal</span><span class="sxs-lookup"><span data-stu-id="40353-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="40353-171">Mettre à jour les membres du canal</span><span class="sxs-lookup"><span data-stu-id="40353-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="40353-172">Supprimer un membre du canal</span><span class="sxs-lookup"><span data-stu-id="40353-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)