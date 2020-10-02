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
ms.openlocfilehash: bbb03fc030361419e5f42b2e792e752f2007e6d2
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333490"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="eab86-103">Exporter du contenu à l’aide des API d’exportation de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="eab86-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="eab86-104">Les API d’exportation d’équipes vous permettent d’exporter des 1:1 et des discussions de groupe à partir de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eab86-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="eab86-105">Si votre organisation doit exporter des messages de Microsoft Teams, vous pouvez les extraire à l’aide des API d’exportation d’équipes.</span><span class="sxs-lookup"><span data-stu-id="eab86-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="eab86-106">Le *message de discussion* représente un message individuel dans un [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou une [discussion](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="eab86-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="eab86-107">Le message de discussion peut être un message de discussion racine ou une partie d’un thread de réponse défini par la propriété **replyToId** dans le message de discussion.</span><span class="sxs-lookup"><span data-stu-id="eab86-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="eab86-108">Voici quelques exemples de la manière dont vous pouvez utiliser ces API d’exportation :</span><span class="sxs-lookup"><span data-stu-id="eab86-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="eab86-109">**Exemple 1**: Si vous avez activé Microsoft teams au sein de votre organisation et que vous souhaitez exporter tous les messages de Microsoft teams vers une date par programme en passant la plage de dates pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="eab86-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="eab86-110">**Exemple 2**: Si vous souhaitez exporter par programme tous les messages utilisateurs quotidiennement en fournissant une plage de dates.</span><span class="sxs-lookup"><span data-stu-id="eab86-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="eab86-111">Les API d’exportation peuvent récupérer tous les messages créés ou mis à jour pendant la plage de dates donnée.</span><span class="sxs-lookup"><span data-stu-id="eab86-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="eab86-112">Quels sont les fonctionnalités prises en charge par les API d’exportation d’équipes ?</span><span class="sxs-lookup"><span data-stu-id="eab86-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="eab86-113">**Exportation en bloc du message d’équipes :** Les API d’exportation d’équipes prennent en charge jusqu’à 200 RPS par application par client et 600 RPS pour une application, avec ces limites, vous devriez être en mesure d’exporter en bloc des messages Teams.</span><span class="sxs-lookup"><span data-stu-id="eab86-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="eab86-114">**Contexte**de l’application : pour appeler Microsoft Graph, votre application doit acquérir un jeton d’accès auprès de la plateforme d’identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eab86-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="eab86-115">Le jeton d’accès contient des informations sur votre application, ainsi que les autorisations qu’elle contient pour les ressources et API disponibles via Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="eab86-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="eab86-116">Pour obtenir un jeton d’accès, votre application doit être inscrite auprès de la plateforme d’identité Microsoft et être habilitée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.</span><span class="sxs-lookup"><span data-stu-id="eab86-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="eab86-117">Pour obtenir des jetons, voir la section [étapes suivantes](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) pour en savoir plus sur l’intégration d’une application à la plateforme d’identité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eab86-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="eab86-118">**Environnement hybride :** Les API d’exportation prennent en charge les messages envoyés par les utilisateurs approvisionnés dans un environnement hybride (Exchange et équipes locale).</span><span class="sxs-lookup"><span data-stu-id="eab86-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="eab86-119">Les messages envoyés par des utilisateurs qui sont configurés pour un environnement hybride seront accessibles via les API d’exportation.</span><span class="sxs-lookup"><span data-stu-id="eab86-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="eab86-120">**Message supprimé par l’utilisateur :** Il est possible d’accéder aux messages supprimés par un utilisateur à partir du client teams à l’aide d’API d’exportation de 30 jours après la suppression.</span><span class="sxs-lookup"><span data-stu-id="eab86-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="eab86-121">**Pièces jointes de message :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre de messages.</span><span class="sxs-lookup"><span data-stu-id="eab86-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="eab86-122">L’utilisation des API d’exportation vous permet de récupérer les fichiers joints aux messages.</span><span class="sxs-lookup"><span data-stu-id="eab86-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="eab86-123">**Propriétés du message de conversation :** Reportez-vous à la liste complète des [Propriétés prises en](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)charge par teams pour l’API.</span><span class="sxs-lookup"><span data-stu-id="eab86-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="eab86-124">Accès aux API d’exportation d’équipes</span><span class="sxs-lookup"><span data-stu-id="eab86-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="eab86-125">**Exemple 1** est une requête simple permettant de récupérer tous les messages d’un utilisateur sans filtres :</span><span class="sxs-lookup"><span data-stu-id="eab86-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="eab86-126">Dans l' **exemple 2** , vous pouvez récupérer tous les messages d’un utilisateur en spécifiant des filtres de date 50 et des filtres de date :</span><span class="sxs-lookup"><span data-stu-id="eab86-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="eab86-127">L’API renvoie la réponse avec le lien page suivante en cas de plusieurs résultats.</span><span class="sxs-lookup"><span data-stu-id="eab86-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="eab86-128">Pour obtenir le jeu de résultats suivant, il vous suffit d’appeler GET sur l’URL à partir de @odata. nextlink.</span><span class="sxs-lookup"><span data-stu-id="eab86-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="eab86-129">Si @odata. nextlink est absent ou nul, tous les messages sont récupérés.</span><span class="sxs-lookup"><span data-stu-id="eab86-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="eab86-130">Conditions préalables à l’accès aux API d’exportation d’équipes</span><span class="sxs-lookup"><span data-stu-id="eab86-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="eab86-131">Les API d’exportation d’équipes sont actuellement en version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="eab86-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="eab86-132">Elle n’est disponible que pour les utilisateurs et clients disposant des [licences requises](https://aka.ms/teams-changenotification-licenses) pour les API.</span><span class="sxs-lookup"><span data-stu-id="eab86-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="eab86-133">À l’avenir, Microsoft pourra vous exiger que vous ou vos clients payez des frais supplémentaires en fonction de la quantité de données consultée par le biais de l’API.</span><span class="sxs-lookup"><span data-stu-id="eab86-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="eab86-134">Les API Microsoft teams dans Microsoft Graph qui accèdent aux données sensibles sont considérées comme des API protégées.</span><span class="sxs-lookup"><span data-stu-id="eab86-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="eab86-135">Les API d’exportation requièrent une validation supplémentaire au-delà des autorisations et de la consentement avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="eab86-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="eab86-136">Pour demander l’accès à ces API protégées, remplissez le [formulaire de demande](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="eab86-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="eab86-137">Les autorisations d’application sont utilisées par les applications qui s’exécutent sans qu’un utilisateur connecté se trouve ; les autorisations des applications ne peuvent être envoyées que par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="eab86-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="eab86-138">Les autorisations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="eab86-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="eab86-139">*Chat. Read. All*: permet d’accéder à tous les 1:1 et aux messages de discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="eab86-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="eab86-140">*User. Read. All*: permet d’accéder à la liste des utilisateurs pour un client.</span><span class="sxs-lookup"><span data-stu-id="eab86-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="eab86-141">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="eab86-141">JSON representation</span></span>

<span data-ttu-id="eab86-142">L’exemple ci-après illustre une représentation JSON de la ressource :</span><span class="sxs-lookup"><span data-stu-id="eab86-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="eab86-143">Espace de noms : Microsoft. Graph</span><span class="sxs-lookup"><span data-stu-id="eab86-143">Namespace: microsoft.graph</span></span>

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="eab86-144">Pour plus d’informations sur la ressource chatMessage, voir l’article [type de ressource chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="eab86-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
