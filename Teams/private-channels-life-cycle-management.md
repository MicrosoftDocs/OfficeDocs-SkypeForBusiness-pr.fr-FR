---
title: Gérer les canaux privés dans Microsoft Teams’Graph API
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer les canaux privés dans votre organisation à l’aide de Graph API.
ms.openlocfilehash: b0b915529d9d4bc780215afceead61ebf31e5259
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2022
ms.locfileid: "62064870"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gérer le cycle de vie des canaux privés dans Microsoft Teams

Vous y trouverez les conseils dont vous avez besoin pour utiliser l’API Graph pour gérer Teams [canaux](./private-channels.md) privés dans votre organisation.

## <a name="set-whether-team-members-can-create-private-channels"></a>Définir si les membres de l’équipe peuvent créer des canaux privés

En tant qu’administrateur, vous pouvez utiliser l’API Graph pour déterminer si les membres peuvent créer des canaux privés dans des équipes spécifiques. Voici un exemple.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Créer une canal privé au nom du propriétaire d’une équipe

En tant qu’administrateur, vous pouvez utiliser l’API Graph pour créer un canal privé de la part d’un propriétaire d’équipe. Par exemple, vous souhaiterez peut-être le faire si votre organisation souhaite centraliser la création de canaux privés.

```Graph API
POST /teams/{id}/channels
{
    "membershipType": "Private",
    "displayName": "<Channel_Name>",
    "members": [
        {
            "@odata.type": "#microsoft.graph.aadUserConversationMember",
            "user@odata.bind": "https://graph.microsoft.com/v1.0/users('<user_id>')",
            "roles": [
                "owner"
            ]
        }
    ]
}
            
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtenez une liste de tous les messages du canal privé

Vous souhaiterez peut-être obtenir une liste de tous les messages et réponses publiés sur un canal privé à des fins d’archivage et d’audit.  Voici comment utiliser l’API Graph pour ce faire.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Rechercher des URL SharePoint pour tous les canaux privés d’une équipe

Que vous cherchiez à effectuer une découverte électronique ou une conservation légale sur des fichiers dans un canal privé ou que vous cherchiez à créer une application personnalisée qui place des fichiers dans des canaux privés spécifiques, vous souhaiterez un moyen d’interroger les collections de sites SharePoint uniques qui sont créées pour chaque canal privé.

En tant qu’administrateur, vous pouvez utiliser Graph API pour interroger ces URL.

Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Utilisez les lignes de commande suivantes pour obtenir la liste des ID de canal privé pour une équipe donnée, dans lesquelles <group_id> est l’ID de groupe de l’équipe. Vous en aurez besoin lors des prochains appels. (Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe).

    **Demande**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Response**

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

2. Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la demande suivante, dans laquelle &lt;channel_id&gt; est l’ID du canal.

    **Demande**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Response**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé

Vous souhaiterez peut-être répertorier les propriétaires et les membres d’un canal privé pour décider si vous devez promouvoir certains membres de ce canal privé au rôle de propriétaire. Cela peut se produire lorsque des propriétaires de canaux privés ont quitté l’organisation et que le canal privé a besoin de l’aide de l’administrateur pour trouver un propriétaire.

En tant qu’administrateur, vous pouvez utiliser l’API Graph pour effectuer ces actions.

Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Utilisez les lignes de commande suivantes dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_id&gt; est l’ID du canal.

    **Demande**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members
    ```

    **Response**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/$metadata#teams({group_id}')/channels('{channel_id}')/members",
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

2. Utilisez les lignes de commande suivantes pour promouvoir le membre au rôle de propriétaire, dans lesquelles &lt;group_id&gt;, &lt;channel_id&gt; et &lt;id&gt; sont renvoyés par l’appel précédent. Notez que &lt;id&gt; et &lt;userId&gt; renvoyés par l’appel précédent ne sont pas les mêmes et ne sont pas interchangeables. Assurez-vous d’utiliser &lt;id&gt;.

    **Demande**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Response**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Sujets associés

[Utiliser l’API Microsoft Graph pour travailler avec Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Répertorier les canaux](/graph/api/channel-list)

[Créer un canal](/graph/api/channel-post)

[Ajouter un membre au canal](/graph/api/conversationmember-add)

[Mettre à jour un membre du canal](/graph/api/conversationmember-update)

[Supprimer un membre du canal](/graph/api/conversationmember-delete)
