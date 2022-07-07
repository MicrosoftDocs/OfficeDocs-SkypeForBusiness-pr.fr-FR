---
title: Exporter du contenu avec les API d’exportation Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Dans cet article, vous allez découvrir comment exporter du contenu Teams à l’aide des API Microsoft Teams Export.
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
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647646"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exporter du contenu avec les API d’exportation Microsoft Teams

Les API d’exportation Teams vous permettent d’exporter 1:1, une conversation de groupe, des conversations de réunion et des messages de canal à partir de Microsoft Teams. Si votre organisation doit exporter des messages Microsoft Teams, vous pouvez les extraire à l’aide des API d’exportation Teams. *Le message* de conversation représente un message de conversation individuel au sein d’un [canal](/graph/api/resources/channel) ou [d’une conversation](/graph/api/resources/chat). Le message de conversation peut être un message de conversation racine ou une partie d’un thread de réponse défini par la propriété **replyToId** dans le message de conversation.

Voici quelques exemples sur la façon dont vous pouvez utiliser ces API d’exportation :

- **Exemple 1** : Si vous avez activé Microsoft Teams dans votre organisation et que vous souhaitez exporter tous les messages Microsoft Teams à ce jour par programmation en passant la plage de dates pour un utilisateur ou une équipe donné.
- **Exemple 2** : Si vous souhaitez exporter par programmation tous les messages de l’utilisateur ou de l’équipe quotidiennement en fournissant une plage de dates. Les API d’exportation peuvent récupérer tous les messages créés ou mis à jour pendant la plage de dates donnée.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Qu’est-ce qui est pris en charge par les API d’exportation Teams ?

- **Exportation en bloc du message Teams :** Les API d’exportation Teams prennent en charge jusqu’à 200 RPS par application par locataire et 600 RPS pour une application, avec ces limites, vous devriez être en mesure d’exporter en bloc des messages Teams.
- **Contexte d’application** : pour appeler Microsoft Graph, votre application doit acquérir un jeton d’accès à partir du Plateforme d'identités Microsoft. Le jeton d’accès contient des informations sur votre application et les autorisations dont elle dispose pour les ressources et LES API disponibles via Microsoft Graph. Pour obtenir un jeton d’accès, votre application doit être inscrite auprès du Plateforme d'identités Microsoft et être autorisée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.

    Si vous êtes déjà familiarisé avec l’intégration d’une application à l’Plateforme d'identités Microsoft pour obtenir des jetons, consultez la section [Étapes suivantes](/graph/auth/auth-concepts#next-steps) pour obtenir des informations et des exemples spécifiques à Microsoft Graph.
- **Environnement hybride :** Les API d’exportation prennent en charge les messages envoyés par les utilisateurs approvisionnés sur un environnement hybride (Exchange et Teams locaux). Tous les messages envoyés par les utilisateurs configurés pour un environnement hybride seront accessibles à l’aide des API Export.
- **Messages supprimés par l’utilisateur :** Les messages supprimés par les utilisateurs du client Teams sont accessibles à l’aide des API d’exportation jusqu’à 21 jours à partir du moment de la suppression.
- **Pièces jointes de message :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre des messages. À l’aide des API d’exportation, vous pouvez récupérer les fichiers joints dans les messages.
- **Réactions:** Les API d’exportation prennent en charge les réactions initées par un utilisateur sur un message Teams. Les réactions actuellement prises en charge sont le cœur, la colère, comme, triste, surpris, et rire.
- **Propriétés du message de conversation :** Reportez-vous à la liste complète des propriétés prises en charge par les API d’exportation Teams [ici](/graph/api/resources/chatmessage#properties).


## <a name="how-to-access-teams-export-apis"></a>Comment accéder aux API d’exportation Teams

- **L’exemple 1** est une requête simple pour récupérer tous les messages d’un utilisateur ou d’une équipe sans filtre :

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **L’exemple 2** est un exemple de requête permettant de récupérer tous les messages d’un utilisateur ou d’une équipe en spécifiant des filtres d’heure de date et les 50 premiers messages :

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> L’API retourne la réponse avec le lien de page suivant en cas de résultats multiples. Pour obtenir l’ensemble de résultats suivant, appelez simplement GET sur l’URL à partir de @odata.nextlink. Si @odata.nextlink n’est pas présent ou null, tous les messages sont récupérés.

## <a name="prerequisites-to-access-teams-export-apis"></a>Conditions préalables à l’accès aux API d’exportation Teams

- Les API Microsoft Teams dans Microsoft Graph qui accèdent à des données sensibles sont considérées comme des API protégées. Les API d’exportation nécessitent une validation supplémentaire, au-delà des autorisations et du consentement, avant de pouvoir les utiliser. Pour demander l’accès à ces API protégées, remplissez le [formulaire de demande](https://aka.ms/teamsgraph/requestaccess).
- Les autorisations d’application sont utilisées par les applications qui s’exécutent sans qu’un utilisateur connecté soit présent ; les autorisations d’application ne peuvent être accordées que par un administrateur. Les autorisations suivantes sont nécessaires :
  - *Chat.Read.All* : permet d’accéder à tous les messages 1:1, de conversation de groupe et de conversation de réunion
  - *ChannelMessage.Read.All* : permet d’accéder à tous les messages de canal
  - *User.Read.All* : permet d’accéder à la liste des utilisateurs d’un locataire

## <a name="license-requirements-for-teams-export-apis"></a>Exigences de licence pour les API d’exportation Teams

L’API Export prend en charge les scénarios de sécurité et de conformité (S+C) et d’utilisation générale via un paramètre de requête de modèle. Les scénarios S+C (modèle A) incluent une capacité initiale et nécessitent un abonnement E5 et les scénarios d’utilisation générale (modèle B) sont disponibles pour tous les abonnements et sont utilisés uniquement. Pour plus d’informations sur les frais d’amorçage de la capacité et de la consommation, consultez [les exigences de licence et de paiement pour les API Microsoft Graph Teams](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Scénarios S+C/Model A

Limité aux applications exécutant des fonctions de sécurité et/ou de conformité, les utilisateurs doivent disposer de licences E5 spécifiques pour utiliser cette fonctionnalité et recevoir une capacité initiale. La capacité d’amorçage est par utilisateur et est calculée par mois et agrégée au niveau du locataire. Pour une utilisation au-delà de la capacité initiale, les propriétaires d’applications sont facturés pour la consommation d’API. Le modèle A peut uniquement accéder aux messages des utilisateurs disposant d’une licence E5 attribuée.

### <a name="general-usagemodel-b-scenarios"></a>Scénarios d’utilisation générale/modèle B

Disponible pour tous les scénarios autres que S+C, il n’existe aucune exigence de licence ni capacité initiale. Lorsque les compteurs de consommation deviennent disponibles, les propriétaires d’applications sont facturés pour tous les appels d’API mensuels.

### <a name="evaluation-mode-default"></a>Mode d’évaluation (par défaut)

Aucune déclaration de modèle n’autorise l’accès aux API avec une utilisation limitée pour chaque application demandant une évaluation.

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

> [!NOTE]
> Pour plus d’informations sur la ressource chatMessage, consultez l’article sur le [type de ressource chatMessage](/graph/api/resources/chatmessage) .
