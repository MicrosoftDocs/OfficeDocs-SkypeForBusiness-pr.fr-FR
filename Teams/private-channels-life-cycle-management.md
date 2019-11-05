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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gérer le cycle de vie des canaux privés dans Microsoft teams

Vous trouverez ci-dessous les conseils nécessaires pour gérer le cycle de vie des [canaux privés](private-channels.md) au sein de votre organisation.

## <a name="set-whether-team-members-can-create-private-channels"></a>Définir si les membres d’une équipe peuvent créer des canaux privés

Les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans les paramètres d’équipe. Pour ce faire, sous l’onglet **paramètres** de l’équipe, désactivez ou activez l’option **autoriser les membres à créer des canaux privés**.

En tant qu’administrateur, vous pouvez utiliser l’API graphique pour contrôler si les membres peuvent créer des canaux privés dans des équipes spécifiques. Voici un exemple :

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Définir si les utilisateurs de votre organisation peuvent créer des canaux privés

En tant qu’administrateur, vous pouvez définir des stratégies en utilisant le centre d’administration Microsoft teams ou PowerShell pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft teams

Les stratégies d’équipe permettent de définir quels utilisateurs de votre organisation peuvent créer des canaux privés. Pour en savoir plus, voir [gérer les stratégies d’équipes dans teams](teams-policies.md).

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez **CsTeamsChannelsPolicy** pour définir quels utilisateurs de votre organisation peuvent créer des canaux privés. Définissez le paramètre **AllowPrivateChannelCreation** sur **true** pour autoriser les utilisateurs auxquels la stratégie est affectée pour créer des canaux privés. Le fait de définir le paramètre sur **false** désactive la possibilité de créer des canaux privés pour les utilisateurs auxquels la stratégie est affectée.

Pour en savoir plus, voir [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Créer un canal privé pour le compte d’un propriétaire d’équipe

En tant qu’administrateur, vous pouvez utiliser l’API PowerShell ou Graph pour créer un canal privé pour le compte d’un propriétaire d’équipe. Par exemple, vous pouvez procéder de la sorte si votre organisation veut centraliser la création de canaux privés.

### <a name="using-powershell"></a>Utiliser PowerShell

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Utilisation de l’API Graph

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtenir la liste de tous les messages de canal privé

Vous pouvez obtenir la liste de tous les messages et réponses publiés dans un canal privé à des fins d’archivage et d’audit.  Pour ce faire, vous devez utiliser l’API graphique.

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Rechercher des URL SharePoint pour tous les canaux privés d’une équipe

Que vous souhaitiez exécuter une découverte électronique ou un blocage légal sur des fichiers dans un canal privé ou avoir besoin d’une application métier qui place des fichiers dans des canaux privés spécifiques, vous avez besoin d’un moyen d’interroger les collections de sites SharePoint uniques créées pour chaque canal privé.

En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.

### <a name="using-powershell"></a>Utiliser PowerShell

1. Installez [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) et connectez-vous avec votre compte d’administrateur.
2. Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l’équipe. (Vous pouvez facilement trouver l’ID du groupe dans le lien vers l’équipe.)

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Utilisation de l’API Graph

Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).

1. Pour obtenir la liste des ID de canal privé d’une équipe donnée, utilisez la commande suivante, où <group_id> correspond à l’ID de groupe de l’équipe. Vous en aurez besoin dans les prochains appels. (L’ID du groupe est facilement repérable dans le lien vers l’équipe).

    **Demande**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Réponse**

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

2. Pour chaque canal privé pour lequel vous souhaitez obtenir l’URL SharePoint, effectuez la requête suivante, où &lt;channel_id&gt; est l’ID du canal.

    **Demande**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Réponse**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Répertorier et mettre à jour les rôles des propriétaires et des membres dans un canal privé

Il est possible que vous souhaitiez répertorier les propriétaires et les membres d’un canal privé pour décider si vous avez besoin de promouvoir certains membres du canal privé auprès d’un propriétaire. Cela peut se produire lorsque vous avez des propriétaires de canaux privés qui ont quitté l’organisation et que le canal privé nécessite une aide d’un administrateur pour réclamer la propriété du canal.

En tant qu’administrateur, vous pouvez utiliser les commandes de l’API PowerShell ou de Graph pour interroger ces URL.

### <a name="using-powershell"></a>Utiliser PowerShell

1. Installez le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) et connectez-vous avec votre compte d’administrateur.
2. Exécutez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et channel_id est l’ID du canal.

    **Demande**

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **Réponse**

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

3. Promouvoir un membre en tant que propriétaire ;

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Utilisation de l’API Graph

Vous pouvez essayer ces commandes via l' [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer).

1. Utilisez la commande suivante, &lt;où&gt; group_id est l’ID de groupe de l' &lt;équipe&gt; et channel_id est l’ID du canal.

    **Demande**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Réponse**

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
2.  Procédez comme suit pour promouvoir le membre auprès d’un propriétaire &lt;,&gt;où &lt;group_id&gt;, channel_id &lt;et&gt; ID sont renvoyés à partir de l’appel précédent. Notez que &lt;l'&gt; ID &lt;et&gt; l’identifiant de l’utilisateur renvoyés par l’appel précédent ne sont pas identiques et ne sont pas interchangeables. Assurez-vous &lt;d'&gt;utiliser ID.

    **Demande**

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Réponse**

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

## <a name="related-topics"></a>Voir aussi

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser l’API Microsoft Graph pour travailler avec des équipes](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Canaux de liste](https://docs.microsoft.com/graph/api/channel-list)
    - [Créer un canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Ajouter un membre au canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Mettre à jour les membres du canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Supprimer un membre du canal](https://docs.microsoft.com/graph/api/conversationmember-delete)