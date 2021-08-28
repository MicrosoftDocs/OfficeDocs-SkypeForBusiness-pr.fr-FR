---
title: Exporter du contenu avec les API Microsoft Teams Exporter
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Dans cet article, vous allez découvrir comment exporter du contenu Teams’aide des API Microsoft Teams exporter.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9d298ad18c6ed63c269c5f31b923a89e63a9f96
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620640"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exporter du contenu avec les API Microsoft Teams Exporter

Teams L’exportation d’API vous permet d’exporter des conversations de groupe, des conversations de réunion et des messages de canal à partir d’Microsoft Teams. Si votre organisation doit exporter des messages Microsoft Teams, vous pouvez les extraire à l’aide d’Teams API d’exportation. *Le message de conversation* représente un message de conversation individuel au sein [d’un canal ou](/graph/api/resources/channel?view=graph-rest-beta) d’une [conversation.](/graph/api/resources/chat?view=graph-rest-beta) Le message de conversation peut être un message de conversation racine ou un élément d’un thread de réponse défini par la propriété **replyToId** dans le message de conversation.

Voici quelques exemples sur l’utilisation de ces API d’exportation :

- **Exemple 1**: si vous avez activé Microsoft Teams dans votre organisation et que vous souhaitez exporter tous les messages Microsoft Teams à ce jour par programme en passant la plage de dates pour un utilisateur ou une équipe donné.
- **Exemple 2**: si vous voulez exporter quotidiennement tous les messages des utilisateurs ou de l’équipe par programme en fournissant une plage de dates. Les API d’exportation peuvent extraire tous les messages créés ou mis à jour pendant la plage de dates donnée.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Quels sont les API pris en charge Teams’exportation ?

- Message d’exportation en bloc : les API d’exportation Teams peuvent prendre en charge jusqu’à 200 SSP par application par client et 600 SD pour une application, avec ces limites, vous devez être en mesure d’exporter en bloc des messages Teams. **Teams**
- **Contexte de l’application**: pour appeler microsoft Graph, votre application doit acquérir un jeton d’accès à partir du Plateforme d’identités Microsoft. Le jeton d’accès contient des informations sur votre application et les autorisations qu’elle possède pour les ressources et API disponibles via Microsoft Graph. Pour obtenir un jeton d’accès, votre application doit être inscrite auprès de la Plateforme d’identités Microsoft et être autorisée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.

    Si vous êtes déjà familiarisé avec l’intégration d’une application au Plateforme d’identités Microsoft pour obtenir des jetons, consultez la [section](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Étapes suivantes pour plus d’informations et d’exemples spécifiques de Microsoft Graph.
- **Environnement hybride :** L’exportation d’API prise en charge des messages envoyés par les utilisateurs qui sont provisionés dans un environnement hybride (environnement local Exchange et Teams). Tous les messages envoyés par les utilisateurs configurés pour un environnement hybride seront accessibles à l’aide d’API d’exportation.
- **Messages supprimés par l’utilisateur :** Les messages supprimés par les utilisateurs du client Teams sont accessibles à l’aide d’API d’exportation jusqu’à 21 jours à partir de la suppression.
- **Pièces jointes :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre des messages. Les API d’exportation vous permet de récupérer les fichiers joints aux messages.
- **Propriétés des messages de conversation :** Consultez la liste complète des propriétés que vous ne Teams la prise en charge d’API Export [ici.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Comment accéder aux API Teams Exporter

- **L’exemple 1** est une requête simple qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe sans filtre :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **L’exemple 2** est un exemple de requête qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe en spécifiant les filtres d’heure et les 50 premiers messages :

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>L’API renvoie la réponse avec le lien de page suivant en cas de résultats multiples. Pour obtenir le jeu de résultats suivant, appelez simplement GET sur l’URL depuis @odata.nextlink. Si @odata.nextlink n’est pas présent ou null, tous les messages sont récupérés.

## <a name="prerequisites-to-access-teams-export-apis"></a>Conditions préalables d’accès Teams API Exporter 

- Teams Les API d’exportation sont actuellement en prévisualisation. Elle ne sera disponible que pour les utilisateurs et clients titulaires des [licences requises pour](/graph/teams-licenses) les API. À l’avenir, Microsoft pourra exiger que vous ou vos clients payiez des frais supplémentaires en fonction du montant des données accessibles via l’API.
- Microsoft Teams Les API dans Microsoft Graph qui accèdent aux données sensibles sont considérées comme des API protégées. L’exportation d’API nécessite une validation supplémentaire, au-delà des autorisations et du consentement, avant de pouvoir les utiliser. Pour demander l’accès à ces API protégées, remplissez le [formulaire de demande.](https://aka.ms/teamsgraph/requestaccess)
- Les autorisations d’application sont utilisées par les applications qui s’exécutent sans présentation d’utilisateur inscrit ; autorisations d’application ne peuvent être autorisées que par un administrateur. Les autorisations suivantes sont nécessaires :

    - *Chat.Read.All*: permet d’accéder aux messages de conversation de groupe et de réunion en tête-à-tête 
    - *ChannelMessage.Read.All*: autorise l’accès à tous les messages de canal  
    - *User.Read.All*: active l’accès à la liste des utilisateurs pour un client

## <a name="json-representation"></a>Représentation JSON

L’exemple suivant est une représentation JSON de la ressource :

Espace de noms : microsoft.graph

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

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Pour plus d’informations sur la ressource chatMessage, consultez l’article du type de ressource [chatMessage.](/graph/api/resources/chatmessage)