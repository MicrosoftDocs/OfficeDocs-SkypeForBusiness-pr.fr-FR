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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gérer le cycle de vie des canaux privés dans Microsoft Teams

Vous trouverez ici les conseils dont vous avez besoin pour gérer le cycle de vie des [canaux privés](private-channels.md) dans votre organisation.

> [!IMPORTANT]
> Si vous utilisez les étapes PowerShell de cet article pour gérer les canaux privés, vous devez installer et utiliser la préversion publique du module Teams PowerShell à partir de la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Si vous souhaitez savoir comment installer le module, consultez l’article [Installer Microsoft Teams PowerShell](teams-powershell-install.md). Le dernier module Teams PowerShell disponible au grand public ne prend pas en charge la gestion des canaux privés.

## <a name="set-whether-team-members-can-create-private-channels"></a>Définir si les membres de l’équipe peuvent créer des canaux privés

Les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans les paramètres de l’équipe. Pour ce faire, dans l’onglet **Paramètres** de l’équipe, désactivez ou activez **Autoriser les membres à créer des canaux privés**.

En tant qu’administrateur, vous pouvez utiliser l’API Graph pour déterminer si les membres peuvent créer des canaux privés dans des équipes spécifiques. Voici un exemple.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Définir si les utilisateurs de votre organisation peuvent créer des canaux privés

En tant qu’administrateur, vous pouvez définir des stratégies à l’aide du centre d’administration Microsoft Teams ou de PowerShell pour déterminer les utilisateurs de votre organisation autorisés à créer des canaux privés.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Utilisez des stratégies d’équipe pour définir les utilisateurs de votre organisation autorisés à créer des canaux privés. Si vous souhaitez en savoir plus, consultez l’article [Gérer les stratégies d’équipe dans Teams](teams-policies.md).

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez **CsTeamsChannelsPolicy** pour définir les utilisateurs de votre organisation autorisés à créer des canaux privés. Définissez le paramètre **AllowPrivateChannelCreation** sur **true** pour permettre aux utilisateurs, auxquels la stratégie est attribuée, de créer des canaux privés. Définir le paramètre sur **false** désactive la possibilité de créer des canaux privés pour les utilisateurs auxquels la stratégie est attribuée.

Si vous souhaitre en savoir plus, consultez l’article [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Créer une canal privé au nom du propriétaire d’une équipe

En tant qu’administrateur, vous pouvez utiliser PowerShell ou l’API Graph pour créer un canal privé au nom du propriétaire d’une équipe. Par exemple, vous souhaiterez peut-être le faire si votre organisation souhaite centraliser la création de canaux privés.

### <a name="using-powershell"></a>Utiliser PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Utiliser l’API Graph

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtenez une liste de tous les messages du canal privé

Vous souhaiterez peut-être obtenir une liste de tous les messages et réponses publiés sur un canal privé à des fins d’archivage et d’audit.  Voici comment utiliser l’API Graph pour ce faire.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Rechercher des URL SharePoint pour tous les canaux privés d’une équipe

Que vous cherchiez à effectuer une découverte électronique ou une conservation légale sur des fichiers dans un canal privé ou que vous cherchiez à créer une application personnalisée qui place des fichiers dans des canaux privés spécifiques, vous souhaiterez un moyen d’interroger les collections de sites SharePoint uniques qui sont créées pour chaque canal privé.

En tant qu’administrateur, vous pouvez utiliser les commandes PowerShell ou de l’API Graph pour interroger ces URL.

### <a name="using-powershell"></a>Utiliser PowerShell

1. Installez et connectez-vous à [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) avec votre compte administrateur.
2. Exécutez les lignes de commande suivantes, dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe. (Vous pouvez facilement trouver l’ID de groupe dans le lien vers l’équipe.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Utiliser l’API Graph

Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Utilisez les lignes de commande suivantes pour obtenir la liste des ID de canal privé pour une équipe donnée, dans lesquelles <group_id> est l’ID de groupe de l’équipe. Vous en aurez besoin lors des prochains appels. (Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe).

    **Demande**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
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
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
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

En tant qu’administrateur, vous pouvez utiliser le centre d’administration Microsoft Teams, PowerShell ou l’API Graph pour effectuer ces actions.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Si vous souhaitez savoir comment gérer les membres de l’équipe à l’aide du centre d’administration Microsoft Teams, consultez l’article [Gérer les équipes dans le centre d’administration Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Utiliser PowerShell

1. Exécutez les lignes de commande suivantes, dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_name&gt; est le nom du canal.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Promouvoir un membre au rôle de propriétaire.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Utiliser l’API Graph

Vous pouvez essayer ces commandes via l’[Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Utilisez les lignes de commande suivantes dans lesquelles &lt;group_id&gt; est l’ID de groupe de l’équipe et &lt;channel_id&gt; est l’ID du canal.

    **Demande**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Response**

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
2. Utilisez les lignes de commande suivantes pour promouvoir le membre au rôle de propriétaire, dans lesquelles &lt;group_id&gt;, &lt;channel_id&gt; et &lt;id&gt; sont renvoyés par l’appel précédent. Notez que &lt;id&gt; et &lt;userId&gt; renvoyés par l’appel précédent ne sont pas les mêmes et ne sont pas interchangeables. Assurez-vous d’utiliser &lt;id&gt;.

    **Demande**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
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
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser l’API Microsoft Graph pour travailler avec Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Répertorier les canaux](https://docs.microsoft.com/graph/api/channel-list)
    - [Créer un canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Ajouter un membre au canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Mettre à jour un membre du canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Supprimer un membre du canal](https://docs.microsoft.com/graph/api/conversationmember-delete)
