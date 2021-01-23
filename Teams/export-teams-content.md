---
title: Exporter du contenu avec les API Microsoft Teams Export
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Dans cet article, vous allez découvrir comment exporter du contenu de Teams à l’aide des API d’exportation de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944599"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exporter du contenu avec les API Microsoft Teams Export

Les API Teams Export vous permettent d’exporter des messages 1:1, de conversation de groupe et de canal à partir de Microsoft Teams. Si votre organisation doit exporter des messages Microsoft Teams, vous pouvez les extraire à l’aide d’API d’exportation de Teams. *Le message de conversation* représente un message de conversation individuel au sein [d’un canal ou](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) d’une [conversation.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Le message de conversation peut être un message de conversation racine ou un élément d’un thread de réponse défini par la propriété **replyToId** dans le message de conversation.

Voici quelques exemples sur l’utilisation de ces API d’exportation :

- **Exemple 1**: si vous avez activé Microsoft Teams dans votre organisation et que vous souhaitez exporter tous les messages Microsoft Teams à ce jour par programme en transmettre la plage de dates pour un utilisateur ou une équipe donné.
- **Exemple 2**: si vous voulez exporter quotidiennement tous les messages des utilisateurs ou de l’équipe par programme en fournissant une plage de dates. Les API d’exportation peuvent extraire tous les messages créés ou mis à jour pendant la plage de dates donnée.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Quels sont les API Teams Export pris en charge ?

- **Exportation en bloc de messages Teams :** Les API Teams Export peuvent prendre en charge jusqu’à 200 SD par application par client et 600 SD pour une application, avec ces limites, vous devez être en mesure d’exporter en bloc des messages Teams.
- **Contexte de l’application**: pour appeler Microsoft Graph, votre application doit acquérir un jeton d’accès auprès de la plateforme d’identité Microsoft. Le jeton d’accès contient des informations sur votre application et les autorisations qu’elle possède pour les ressources et API disponibles via Microsoft Graph. Pour obtenir un jeton d’accès, votre application doit être enregistrée auprès de la plateforme d’identité Microsoft et être autorisée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.

    Si vous êtes déjà familiarisé avec l’intégration d’une application à la plateforme d’identité Microsoft pour obtenir des jetons, consultez la [section](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Étapes suivantes pour plus d’informations et d’exemples spécifiques de Microsoft Graph.
- **Environnement hybride :** Exporter des api de prise en charge envoyées par des utilisateurs qui ont une mise en service dans un environnement hybride (exchange et Teams locaux). Tous les messages envoyés par les utilisateurs configurés pour un environnement hybride seront accessibles à l’aide d’API d’exportation.
- **Messages supprimés par l’utilisateur :** Les messages supprimés par les utilisateurs du client Teams sont accessibles à l’aide d’API d’exportation jusqu’à 30 jours à partir de la suppression.
- **Pièces jointes :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre des messages. Les API d’exportation vous permet de récupérer les fichiers joints aux messages.
- **Propriétés des messages de conversation :** Consultez la liste complète des propriétés que les API Teams Export peuvent prendre [en charge ici.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Comment accéder aux API d’exportation de Teams

- **L’exemple 1** est une requête simple qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe sans filtre :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **L’exemple 2** est un exemple de requête qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe en spécifiant les filtres d’heure et les 50 premiers messages :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Pour plus d’informations sur la ressource chatMessage, consultez l’article du type de ressource [chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)
