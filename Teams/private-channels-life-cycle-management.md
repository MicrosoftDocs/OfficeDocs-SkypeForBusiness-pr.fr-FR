---
title: Gérer les canaux privés dans Microsoft Teams avec l’API Graph
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
description: Découvrez comment gérer les canaux privés dans votre organisation à l’aide de l’API Graph.
ms.openlocfilehash: 854e8721dac7d49e258db42845b84480955bfec7
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772037"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="068df-103">Gérer le cycle de vie des canaux privés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="068df-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="068df-104">Vous y trouverez les conseils dont vous avez besoin pour gérer l’utilisation de l’API Graph pour gérer les canaux [privés Teams](https://docs.microsoft.com/microsoftteams/private-channels) dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="068df-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](https://docs.microsoft.com/microsoftteams/private-channels) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="068df-105">Définir si les membres de l’équipe peuvent créer des canaux privés</span><span class="sxs-lookup"><span data-stu-id="068df-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="068df-106">En tant qu’administrateur, vous pouvez utiliser l’API Graph pour déterminer si les membres peuvent créer des canaux privés dans des équipes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="068df-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="068df-107">Voici un exemple.</span><span class="sxs-lookup"><span data-stu-id="068df-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="068df-108">Créer une canal privé au nom du propriétaire d’une équipe</span><span class="sxs-lookup"><span data-stu-id="068df-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="068df-109">En tant qu’administrateur, vous pouvez utiliser l’API Graph pour créer un canal privé de la part d’un propriétaire d’équipe.</span><span class="sxs-lookup"><span data-stu-id="068df-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="068df-110">Par exemple, vous souhaiterez peut-être le faire si votre organisation souhaite centraliser la création de canaux privés.</span><span class="sxs-lookup"><span data-stu-id="068df-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="068df-111">Obtenez une liste de tous les messages du canal privé</span><span class="sxs-lookup"><span data-stu-id="068df-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="068df-112">Vous souhaiterez peut-être obtenir une liste de tous les messages et réponses publiés sur un canal privé à des fins d’archivage et d’audit.</span><span class="sxs-lookup"><span data-stu-id="068df-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="068df-113">Voici comment utiliser l’API Graph pour ce faire.</span><span class="sxs-lookup"><span data-stu-id="068df-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="068df-114">Rechercher des URL SharePoint pour tous les canaux privés d’une équipe</span><span class="sxs-lookup"><span data-stu-id="068df-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="068df-115">Que vous cherchiez à effectuer une découverte électronique ou une conservation légale sur des fichiers dans un canal privé ou que vous cherchiez à créer une application personnalisée qui place des fichiers dans des canaux privés spécifiques, vous souhaiterez un moyen d’interroger les collections de sites SharePoint uniques qui sont créées pour chaque canal privé.</span><span class="sxs-lookup"><span data-stu-id="068df-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="068df-116">En tant qu’administrateur, vous pouvez utiliser les commandes API graph pour interroger ces URL.</span><span class="sxs-lookup"><span data-stu-id="068df-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="068df-117">Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="068df-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="068df-118">Utilisez les lignes de commande suivantes pour obtenir la liste des ID de canal privé pour une équipe donnée, dans lesquelles <group_id> est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="068df-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="068df-119">Vous en aurez besoin lors des prochains appels.</span><span class="sxs-lookup"><span data-stu-id="068df-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="068df-120">(Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe).</span><span class="sxs-lookup"><span data-stu-id="068df-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="068df-121">**Demande**</span><span class="sxs-lookup"><span data-stu-id="068df-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="068df-122">**Response**</span><span class="sxs-lookup"><span data-stu-id="068df-122">**Response**</span></span>

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

2. <span data-ttu-id="068df-123">Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la demande suivante, dans laquelle &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="068df-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="068df-124">**Demande**</span><span class="sxs-lookup"><span data-stu-id="068df-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="068df-125">**Response**</span><span class="sxs-lookup"><span data-stu-id="068df-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="068df-126">Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé</span><span class="sxs-lookup"><span data-stu-id="068df-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="068df-127">Vous souhaiterez peut-être répertorier les propriétaires et les membres d’un canal privé pour décider si vous devez promouvoir certains membres de ce canal privé au rôle de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="068df-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="068df-128">Cela peut se produire lorsque des propriétaires de canaux privés ont quitté l’organisation et que le canal privé a besoin de l’aide de l’administrateur pour trouver un propriétaire.</span><span class="sxs-lookup"><span data-stu-id="068df-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="068df-129">En tant qu’administrateur, vous pouvez utiliser l’API Graph pour effectuer ces actions.</span><span class="sxs-lookup"><span data-stu-id="068df-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="068df-130">Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="068df-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="068df-131">Utilisez les lignes de commande suivantes dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_id&gt; est l’ID du canal.</span><span class="sxs-lookup"><span data-stu-id="068df-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="068df-132">**Demande**</span><span class="sxs-lookup"><span data-stu-id="068df-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="068df-133">**Response**</span><span class="sxs-lookup"><span data-stu-id="068df-133">**Response**</span></span>

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
2. <span data-ttu-id="068df-134">Utilisez les lignes de commande suivantes pour promouvoir le membre au rôle de propriétaire, dans lesquelles &lt;group_id&gt;, &lt;channel_id&gt; et &lt;id&gt; sont renvoyés par l’appel précédent.</span><span class="sxs-lookup"><span data-stu-id="068df-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="068df-135">Notez que &lt;id&gt; et &lt;userId&gt; renvoyés par l’appel précédent ne sont pas les mêmes et ne sont pas interchangeables.</span><span class="sxs-lookup"><span data-stu-id="068df-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="068df-136">Assurez-vous d’utiliser &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="068df-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="068df-137">**Demande**</span><span class="sxs-lookup"><span data-stu-id="068df-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="068df-138">**Response**</span><span class="sxs-lookup"><span data-stu-id="068df-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="068df-139">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="068df-139">Related topics</span></span>

[<span data-ttu-id="068df-140">Utiliser l’API Microsoft Graph pour travailler avec Teams</span><span class="sxs-lookup"><span data-stu-id="068df-140">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="068df-141">Répertorier les canaux</span><span class="sxs-lookup"><span data-stu-id="068df-141">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)

[<span data-ttu-id="068df-142">Créer un canal</span><span class="sxs-lookup"><span data-stu-id="068df-142">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)

[<span data-ttu-id="068df-143">Ajouter un membre au canal</span><span class="sxs-lookup"><span data-stu-id="068df-143">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)

[<span data-ttu-id="068df-144">Mettre à jour un membre du canal</span><span class="sxs-lookup"><span data-stu-id="068df-144">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)

[<span data-ttu-id="068df-145">Supprimer un membre du canal</span><span class="sxs-lookup"><span data-stu-id="068df-145">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
