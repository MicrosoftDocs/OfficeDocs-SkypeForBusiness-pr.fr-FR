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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer le cycle de vie des canaux privés au sein de votre organisation.
ms.openlocfilehash: 527e6421160eefa72b2a9c21e8e8f25303534320
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837324"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="dfba7-103">Gérer le cycle de vie des canaux privés dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="dfba7-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="dfba7-104">Vous trouverez ci-dessous les conseils nécessaires pour gérer le cycle de vie des [canaux privés](private-channels.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dfba7-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfba7-105">Si vous utilisez les étapes PowerShell de cet article pour gérer des canaux privés, vous devez installer et utiliser la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfba7-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="dfba7-106">Pour plus d’informations sur la procédure à suivre, voir [installer le dernier module PowerShell teams dans la Galerie de tests PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="dfba7-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="dfba7-107">La dernière version publique disponible du module teams PowerShell (actuellement [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) ne prend pas en charge la gestion des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="dfba7-108">Définir si les membres d’une équipe peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="dfba7-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="dfba7-109">Les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans les paramètres d’équipe.</span><span class="sxs-lookup"><span data-stu-id="dfba7-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="dfba7-110">Pour ce faire, sous l’onglet **paramètres** de l’équipe, désactivez ou activez l’option **autoriser les membres à créer des canaux privés**.</span><span class="sxs-lookup"><span data-stu-id="dfba7-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="dfba7-111">En tant qu’administrateur, vous pouvez utiliser l’API graphique pour contrôler si les membres peuvent créer des canaux privés dans des équipes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="dfba7-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="dfba7-112">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="dfba7-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="dfba7-113">Définir si les utilisateurs de votre organisation peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="dfba7-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="dfba7-114">En tant qu’administrateur, vous pouvez définir des stratégies en utilisant le centre d’administration Microsoft teams ou PowerShell pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="dfba7-115">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="dfba7-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="dfba7-116">Les stratégies d’équipe permettent de définir quels utilisateurs de votre organisation peuvent créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="dfba7-117">Pour en savoir plus, voir [gérer les stratégies d’équipes dans teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dfba7-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dfba7-118">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-118">Using PowerShell</span></span>

<span data-ttu-id="dfba7-119">Utilisez **CsTeamsChannelsPolicy** pour définir quels utilisateurs de votre organisation peuvent créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="dfba7-120">Définissez le paramètre **AllowPrivateChannelCreation** sur **true** pour autoriser les utilisateurs auxquels la stratégie est affectée pour créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="dfba7-121">Le fait de définir le paramètre sur **false** désactive la possibilité de créer des canaux privés pour les utilisateurs auxquels la stratégie est affectée.</span><span class="sxs-lookup"><span data-stu-id="dfba7-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="dfba7-122">Pour en savoir plus, voir [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dfba7-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="dfba7-123">Créer un canal privé pour le compte d’un propriétaire d’équipe</span><span class="sxs-lookup"><span data-stu-id="dfba7-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="dfba7-124">En tant qu’administrateur, vous pouvez utiliser l’API PowerShell ou Graph pour créer un canal privé pour le compte d’un propriétaire d’équipe.</span><span class="sxs-lookup"><span data-stu-id="dfba7-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="dfba7-125">Par exemple, vous pouvez procéder de la sorte si votre organisation veut centraliser la création de canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dfba7-126">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="dfba7-127">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="dfba7-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="dfba7-128">Obtenir la liste de tous les messages de canal privé</span><span class="sxs-lookup"><span data-stu-id="dfba7-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="dfba7-129">Vous pouvez obtenir la liste de tous les messages et réponses publiés dans un canal privé à des fins d’archivage et d’audit.</span><span class="sxs-lookup"><span data-stu-id="dfba7-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="dfba7-130">Pour ce faire, vous devez utiliser l’API graphique.</span><span class="sxs-lookup"><span data-stu-id="dfba7-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="dfba7-131">Rechercher des URL SharePoint pour tous les canaux privés d’une équipe</span><span class="sxs-lookup"><span data-stu-id="dfba7-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="dfba7-132">Que vous souhaitiez exécuter une découverte électronique ou un blocage légal sur des fichiers dans un canal privé ou avoir besoin d’une application métier qui place des fichiers dans des canaux privés spécifiques, vous avez besoin d’un moyen d’interroger les collections de sites SharePoint uniques créées pour chaque canal privé.</span><span class="sxs-lookup"><span data-stu-id="dfba7-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="dfba7-133">En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="dfba7-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dfba7-134">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-134">Using PowerShell</span></span>

1. <span data-ttu-id="dfba7-135">Installez [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) et connectez-vous avec votre compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="dfba7-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="dfba7-136">Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="dfba7-136">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="dfba7-137">(Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe.)</span><span class="sxs-lookup"><span data-stu-id="dfba7-137">(You can easily find the group Id in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="dfba7-138">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="dfba7-138">Using Graph API</span></span>

<span data-ttu-id="dfba7-139">Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="dfba7-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="dfba7-140">Pour obtenir la liste des ID de canal privé d’une équipe, procédez comme suit : <group_id> est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="dfba7-140">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="dfba7-141">Vous en aurez besoin dans les prochains appels.</span><span class="sxs-lookup"><span data-stu-id="dfba7-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="dfba7-142">(L’ID du groupe est facilement repérable dans le lien vers l’équipe).</span><span class="sxs-lookup"><span data-stu-id="dfba7-142">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="dfba7-143">**Demande**</span><span class="sxs-lookup"><span data-stu-id="dfba7-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="dfba7-144">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="dfba7-144">**Response**</span></span>

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

2. <span data-ttu-id="dfba7-145">Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la requête suivante, où &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="dfba7-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="dfba7-146">**Demande**</span><span class="sxs-lookup"><span data-stu-id="dfba7-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="dfba7-147">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="dfba7-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="dfba7-148">Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé</span><span class="sxs-lookup"><span data-stu-id="dfba7-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="dfba7-149">Il est possible que vous souhaitiez répertorier les propriétaires et les membres d’un canal privé pour décider si vous avez besoin de promouvoir certains membres du canal privé auprès d’un propriétaire.</span><span class="sxs-lookup"><span data-stu-id="dfba7-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="dfba7-150">Cela peut se produire lorsque vous avez des propriétaires de canaux privés qui ont quitté l’organisation et que le canal privé nécessite une aide d’un administrateur pour réclamer la propriété du canal.</span><span class="sxs-lookup"><span data-stu-id="dfba7-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="dfba7-151">En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="dfba7-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dfba7-152">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-152">Using PowerShell</span></span>

1. <span data-ttu-id="dfba7-153">Installez le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) et connectez-vous avec votre compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="dfba7-153">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="dfba7-154">Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et channel_id est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="dfba7-154">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="dfba7-155">**Demande**</span><span class="sxs-lookup"><span data-stu-id="dfba7-155">**Request**</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="dfba7-156">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="dfba7-156">**Response**</span></span>

    ```PowerShell
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

3. <span data-ttu-id="dfba7-157">Promouvoir un membre en tant que propriétaire ;</span><span class="sxs-lookup"><span data-stu-id="dfba7-157">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="dfba7-158">Utilisation de l’API Graph</span><span class="sxs-lookup"><span data-stu-id="dfba7-158">Using Graph API</span></span>

<span data-ttu-id="dfba7-159">Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="dfba7-159">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="dfba7-160">Utilisez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et que channel_id est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="dfba7-160">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="dfba7-161">**Demande**</span><span class="sxs-lookup"><span data-stu-id="dfba7-161">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="dfba7-162">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="dfba7-162">**Response**</span></span>

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
2.  <span data-ttu-id="dfba7-163">Procédez comme suit pour promouvoir le membre auprès d’un propriétaire &lt;,&gt;où &lt;group_id&gt;, channel_id &lt;et&gt; ID sont renvoyés à partir de l’appel précédent.</span><span class="sxs-lookup"><span data-stu-id="dfba7-163">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="dfba7-164">Notez que &lt;l'&gt; ID &lt;et&gt; l’identifiant de l’utilisateur renvoyés par l’appel précédent ne sont pas identiques et ne sont pas interchangeables.</span><span class="sxs-lookup"><span data-stu-id="dfba7-164">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="dfba7-165">Assurez-vous &lt;d'&gt;utiliser ID.</span><span class="sxs-lookup"><span data-stu-id="dfba7-165">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="dfba7-166">**Demande**</span><span class="sxs-lookup"><span data-stu-id="dfba7-166">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="dfba7-167">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="dfba7-167">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="dfba7-168">Module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="dfba7-168">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="dfba7-169">Installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-169">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="dfba7-170">La dernière version publique disponible du module teams PowerShell (actuellement [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) ne prend pas en charge la gestion des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="dfba7-170">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="dfba7-171">Procédez comme suit pour installer la dernière version du module PowerShell teams avec prise en charge de canal privé (actuellement 1.0.18) à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfba7-171">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="dfba7-172">N’installez pas le module PowerShell teams à partir de la Galerie de tests PowerShell côte à côte avec une version du module dans la Galerie PowerShell publique.</span><span class="sxs-lookup"><span data-stu-id="dfba7-172">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="dfba7-173">Procédez comme suit pour désinstaller d’abord le module PowerShell teams dans la Galerie PowerShell public, puis installez la dernière version du module à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfba7-173">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="dfba7-174">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="dfba7-174">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="dfba7-175">Démarrez une nouvelle instance du module Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfba7-175">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="dfba7-176">Pour désinstaller le module teams PowerShell de la Galerie public PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="dfba7-176">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="dfba7-177">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="dfba7-177">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="dfba7-178">Démarrez de nouveau le module Windows PowerShell, puis exécutez la commande suivante pour inscrire la Galerie de tests PowerShell en tant que source de confiance :</span><span class="sxs-lookup"><span data-stu-id="dfba7-178">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="dfba7-179">Pour installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="dfba7-179">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="dfba7-180">Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :</span><span class="sxs-lookup"><span data-stu-id="dfba7-180">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="dfba7-181">Effectuer une mise à jour vers la dernière version du module PowerShell teams à partir de la Galerie de tests PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-181">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="dfba7-182">Si vous avez déjà installé le module teams PowerShell à partir de la Galerie de tests PowerShell, procédez comme suit pour effectuer une mise à jour vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="dfba7-182">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="dfba7-183">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="dfba7-183">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="dfba7-184">Démarrez une nouvelle instance du module Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfba7-184">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="dfba7-185">Exécutez la commande suivante pour mettre à jour la version actuellement installée du module PowerShell teams à partir de la Galerie de tests PowerShell :</span><span class="sxs-lookup"><span data-stu-id="dfba7-185">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="dfba7-186">Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :</span><span class="sxs-lookup"><span data-stu-id="dfba7-186">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="dfba7-187">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="dfba7-187">Related topics</span></span>

- [<span data-ttu-id="dfba7-188">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfba7-188">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="dfba7-189">Utiliser l’API Microsoft Graph pour travailler avec des équipes</span><span class="sxs-lookup"><span data-stu-id="dfba7-189">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="dfba7-190">Canaux de liste</span><span class="sxs-lookup"><span data-stu-id="dfba7-190">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="dfba7-191">Créer un canal</span><span class="sxs-lookup"><span data-stu-id="dfba7-191">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="dfba7-192">Ajouter un membre au canal</span><span class="sxs-lookup"><span data-stu-id="dfba7-192">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="dfba7-193">Mettre à jour les membres du canal</span><span class="sxs-lookup"><span data-stu-id="dfba7-193">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="dfba7-194">Supprimer un membre du canal</span><span class="sxs-lookup"><span data-stu-id="dfba7-194">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
