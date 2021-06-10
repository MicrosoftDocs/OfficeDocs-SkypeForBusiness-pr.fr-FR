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
ms.openlocfilehash: f2e7ccaac78cd7e96581dc1d9371fc9eef096265
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717975"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="2f3f8-103">Exporter du contenu avec les API Microsoft Teams Exporter</span><span class="sxs-lookup"><span data-stu-id="2f3f8-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="2f3f8-104">Teams L’exportation d’API vous permet d’exporter des conversations de groupe, des conversations de réunion et des messages de canal à partir d’Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="2f3f8-105">Si votre organisation doit exporter des messages Microsoft Teams, vous pouvez les extraire à l’aide d’Teams API d’exportation.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="2f3f8-106">*Le message de conversation* représente un message de conversation individuel au sein [d’un canal ou](/graph/api/resources/channel?view=graph-rest-beta) d’une [conversation.](/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="2f3f8-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="2f3f8-107">Le message de conversation peut être un message de conversation racine ou un élément d’un thread de réponse défini par la propriété **replyToId** dans le message de conversation.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="2f3f8-108">Voici quelques exemples sur l’utilisation de ces API d’exportation :</span><span class="sxs-lookup"><span data-stu-id="2f3f8-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="2f3f8-109">**Exemple 1**: si vous avez activé Microsoft Teams dans votre organisation et que vous souhaitez exporter tous les messages Microsoft Teams à ce jour par programme en passant la plage de dates pour un utilisateur ou une équipe donné.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="2f3f8-110">**Exemple 2**: si vous voulez exporter quotidiennement tous les messages des utilisateurs ou de l’équipe par programme en fournissant une plage de dates.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="2f3f8-111">Les API d’exportation peuvent extraire tous les messages créés ou mis à jour pendant la plage de dates donnée.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="2f3f8-112">Quels sont les API pris en charge Teams’exportation ?</span><span class="sxs-lookup"><span data-stu-id="2f3f8-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="2f3f8-113">Message d’exportation en bloc : les API d’exportation Teams peuvent prendre en charge jusqu’à 200 SSP par application par client et 600 SD pour une application, avec ces limites, vous devez être en mesure d’exporter en bloc des messages Teams. **Teams**</span><span class="sxs-lookup"><span data-stu-id="2f3f8-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="2f3f8-114">**Contexte de l’application**: pour appeler microsoft Graph, votre application doit acquérir un jeton d’accès à partir du Plateforme d’identités Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="2f3f8-115">Le jeton d’accès contient des informations sur votre application et les autorisations qu’elle possède pour les ressources et API disponibles via Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="2f3f8-116">Pour obtenir un jeton d’accès, votre application doit être inscrite auprès de la Plateforme d’identités Microsoft et être autorisée par un utilisateur ou un administrateur à accéder aux ressources Microsoft Graph dont elle a besoin.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="2f3f8-117">Si vous êtes déjà familiarisé avec l’intégration d’une application au Plateforme d’identités Microsoft pour obtenir des jetons, consultez la [section](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) Étapes suivantes pour plus d’informations et d’exemples spécifiques de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="2f3f8-118">**Environnement hybride :** L’exportation d’API prise en charge des messages envoyés par les utilisateurs qui sont provisionés dans un environnement hybride (environnement local Exchange et Teams).</span><span class="sxs-lookup"><span data-stu-id="2f3f8-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="2f3f8-119">Tous les messages envoyés par les utilisateurs configurés pour un environnement hybride seront accessibles à l’aide d’API d’exportation.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="2f3f8-120">**Messages supprimés par l’utilisateur :** Les messages supprimés par les utilisateurs du client Teams sont accessibles à l’aide d’API d’exportation jusqu’à 21 jours à partir de la suppression.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="2f3f8-121">**Pièces jointes :** Les API d’exportation incluent les liens vers les pièces jointes envoyées dans le cadre des messages.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="2f3f8-122">Les API d’exportation vous permet de récupérer les fichiers joints aux messages.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="2f3f8-123">**Propriétés des messages de conversation :** Consultez la liste complète des propriétés que vous ne Teams la prise en charge d’API Export [ici.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="2f3f8-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="2f3f8-124">Comment accéder aux API Teams Exporter</span><span class="sxs-lookup"><span data-stu-id="2f3f8-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="2f3f8-125">**L’exemple 1** est une requête simple qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe sans filtre :</span><span class="sxs-lookup"><span data-stu-id="2f3f8-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="2f3f8-126">**L’exemple 2** est un exemple de requête qui vous permettent de récupérer tous les messages d’un utilisateur ou d’une équipe en spécifiant les filtres d’heure et les 50 premiers messages :</span><span class="sxs-lookup"><span data-stu-id="2f3f8-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="2f3f8-127">L’API renvoie la réponse avec le lien de page suivant en cas de résultats multiples.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="2f3f8-128">Pour obtenir le jeu de résultats suivant, appelez simplement GET sur l’URL depuis @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="2f3f8-129">Si @odata.nextlink n’est pas présent ou null, tous les messages sont récupérés.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="2f3f8-130">Conditions préalables d’accès Teams API Exporter</span><span class="sxs-lookup"><span data-stu-id="2f3f8-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="2f3f8-131">Teams Les API d’exportation sont actuellement en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="2f3f8-132">Elle ne sera disponible que pour les utilisateurs et clients titulaires des [licences requises pour](/graph/teams-licenses) les API.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="2f3f8-133">À l’avenir, Microsoft pourra exiger que vous ou vos clients payiez des frais supplémentaires en fonction du montant des données accessibles via l’API.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="2f3f8-134">Microsoft Teams Les API dans Microsoft Graph qui accèdent aux données sensibles sont considérées comme des API protégées.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="2f3f8-135">L’exportation d’API nécessite une validation supplémentaire, au-delà des autorisations et du consentement, avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="2f3f8-136">Pour demander l’accès à ces API protégées, remplissez le [formulaire de demande.](https://aka.ms/teamsgraph/requestaccess)</span><span class="sxs-lookup"><span data-stu-id="2f3f8-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="2f3f8-137">Les autorisations d’application sont utilisées par les applications qui s’exécutent sans présentation d’utilisateur inscrit ; autorisations d’application ne peuvent être autorisées que par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="2f3f8-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="2f3f8-138">Les autorisations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="2f3f8-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="2f3f8-139">*Chat.Read.All*: permet d’accéder aux messages de conversation de groupe et de réunion en tête-à-tête</span><span class="sxs-lookup"><span data-stu-id="2f3f8-139">*Chat.Read.All*: enables access to all 1:1, Group chat, and meeting chat messages</span></span> 
    - <span data-ttu-id="2f3f8-140">*ChannelMessage.Read.All*: autorise l’accès à tous les messages de canal</span><span class="sxs-lookup"><span data-stu-id="2f3f8-140">*ChannelMessage.Read.All*: enables access to all channel messages</span></span>  
    - <span data-ttu-id="2f3f8-141">*User.Read.All*: autorise l’accès à la liste des utilisateurs pour un client</span><span class="sxs-lookup"><span data-stu-id="2f3f8-141">*User.Read.All*: enables access to the list of users for a tenant</span></span>

## <a name="json-representation"></a><span data-ttu-id="2f3f8-142">Représentation JSON</span><span class="sxs-lookup"><span data-stu-id="2f3f8-142">JSON representation</span></span>

<span data-ttu-id="2f3f8-143">L’exemple suivant est une représentation JSON de la ressource :</span><span class="sxs-lookup"><span data-stu-id="2f3f8-143">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="2f3f8-144">Espace de noms : microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="2f3f8-144">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="2f3f8-145">Pour plus d’informations sur la ressource chatMessage, consultez l’article du type de ressource [chatMessage.](/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="2f3f8-145">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>