---
title: Exporter du contenu à l’aide des API d’exportation de Microsoft teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Dans cet article, vous allez découvrir comment exporter du contenu d’équipes à l’aide des API d’exportation de Microsoft Teams.
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
ms.openlocfilehash: 896e60e8de6e01208a07c40e757a79a12192383a
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611818"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exporter du contenu à l’aide des API d’exportation de Microsoft teams

Les API d’exportation d’équipes vous permettent d’exporter des 1:1 et des discussions de groupe à partir de Microsoft Teams. Si votre organisation doit exporter des messages de Microsoft Teams, vous pouvez les extraire à l’aide des API d’exportation d’équipes. Le *message de discussion* représente un message individuel dans un [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou une [discussion](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). Le message de discussion peut être un message de discussion racine ou une partie d’un thread de réponse défini par la propriété **replyToId** dans le message de discussion.

Voici quelques exemples de la manière dont vous pouvez utiliser ces API d’exportation :

- **Exemple 1**: Si vous avez activé Microsoft teams au sein de votre organisation et que vous souhaitez exporter tous les messages de Microsoft teams vers une date par programme en passant la plage de dates pour un utilisateur donné.
- **Exemple 2**: Si vous souhaitez exporter par programme tous les messages utilisateurs quotidiennement en fournissant une plage de dates. Les API d’exportation peuvent récupérer tous les messages créés ou mis à jour pendant la plage de dates donnée.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Quels sont les fonctionnalités prises en charge par les API d’exportation d’équipes ?

- **Exportation en bloc du message d’équipes :** Les API d’exportation d’équipes prennent en charge jusqu’à 200 RPS par application par client et 600 RPS pour une application, avec ces limites, vous devriez être en mesure d’exporter en bloc des messages Teams.
- **Contexte** de l’application : pour appeler Microsoft Graph, votre application doit acquérir un jeton d’accès auprès de la plateforme d’identité Microsoft. Le jeton d’accès contient des informations sur votre application, ainsi que les autorisations qu’elle contient pour les ressources et API disponibles via Microsoft Graph. Pour obtenir un jeton d’accès, votre application doit être inscrite auprès de la plateforme d’identité Microsoft et être habilitée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.

    Pour obtenir des jetons, voir la section [étapes suivantes](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) pour en savoir plus sur l’intégration d’une application à la plateforme d’identité Microsoft.
- **Environnement hybride :** Les API d’exportation prennent en charge les messages envoyés par les utilisateurs approvisionnés dans un environnement hybride (Exchange et équipes locale). Les messages envoyés par des utilisateurs qui sont configurés pour un environnement hybride seront accessibles via les API d’exportation.
- **Message supprimé par l’utilisateur :** Il est possible d’accéder aux messages supprimés par un utilisateur à partir du client teams à l’aide d’API d’exportation de 30 jours après la suppression.
- **Pièces jointes de message :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre de messages. L’utilisation des API d’exportation vous permet de récupérer les fichiers joints aux messages.
- **Propriétés du message de conversation :** Reportez-vous à la liste complète des [Propriétés prises en](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)charge par teams pour l’API.

## <a name="how-to-access-teams-export-apis"></a>Accès aux API d’exportation d’équipes

- **Exemple 1** est une requête simple permettant de récupérer tous les messages d’un utilisateur sans filtres :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- Dans l' **exemple 2** , vous pouvez récupérer tous les messages d’un utilisateur en spécifiant des filtres de date 50 et des filtres de date :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>L’API renvoie la réponse avec le lien page suivante en cas de plusieurs résultats. Pour obtenir le jeu de résultats suivant, il vous suffit d’appeler GET sur l’URL à partir de @odata. nextlink. Si @odata. nextlink est absent ou nul, tous les messages sont récupérés.

## <a name="prerequisites-to-access-teams-export-apis"></a>Conditions préalables à l’accès aux API d’exportation d’équipes 

- Les API d’exportation d’équipes sont actuellement en version préliminaire. Elle n’est disponible que pour les utilisateurs et clients disposant des [licences requises](https://aka.ms/teams-changenotification-licenses) pour les API. À l’avenir, Microsoft pourra vous exiger que vous ou vos clients payez des frais supplémentaires en fonction de la quantité de données consultée par le biais de l’API.
- Les API Microsoft teams dans Microsoft Graph qui accèdent aux données sensibles sont considérées comme des API protégées. Les API d’exportation requièrent une validation supplémentaire au-delà des autorisations et de la consentement avant de pouvoir les utiliser. Pour demander l’accès à ces API protégées, remplissez le [formulaire de demande](https://aka.ms/teamsgraph/requestaccess).
- Les autorisations d’application sont utilisées par les applications qui s’exécutent sans qu’un utilisateur connecté se trouve ; les autorisations des applications ne peuvent être envoyées que par un administrateur. Les autorisations suivantes sont nécessaires :

    - *Chat. Read. All*: permet d’accéder à tous les 1:1 et aux messages de discussion de groupe. 
    - *User. Read. All*: permet d’accéder à la liste des utilisateurs pour un client. 

## <a name="json-representation"></a>Représentation JSON

L’exemple ci-après illustre une représentation JSON de la ressource :

Espace de noms : Microsoft. Graph

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
>Pour plus d’informations sur la ressource chatMessage, voir l’article [type de ressource chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
