---
title: Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce087aed26c22fb97a0ad9b5161927f6a6afea4d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222045"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="3a1d4-103">Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a1d4-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="3a1d4-104">Les liens permettent de mettre à jour votre équipe en fournissant des mises à jour de contenu et de service fréquemment utilisées directement dans un canal.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="3a1d4-105">Les connecteurs permettent aux utilisateurs de Microsoft teams de recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et Azure DevOps services dans le flux de conversation de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="3a1d4-106">Tout membre d’une équipe peut relier son équipe aux services Cloud populaires avec les connecteurs si les autorisations de l’équipe le permettent, et tous les membres de l’équipe sont avertis des activités de ce service.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="3a1d4-107">Les connecteurs continuent de fonctionner même après que le membre qui a initialement configuré le connecteur est resté.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="3a1d4-108">Les membres d’une équipe disposant de l’autorisation d’ajout d’une fonction peuvent modifier les connecteurs configurés par d’autres membres.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="3a1d4-109">Les connecteurs 365 Office peuvent être utilisés avec Microsoft teams et les groupes Office 365, ce qui permet à tous les membres de rester synchronisés et de recevoir rapidement des informations pertinentes.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="3a1d4-110">Microsoft teams et Exchange utilisent le même modèle de connecteur, ce qui vous permet d’utiliser les mêmes connecteurs dans les deux plateformes.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="3a1d4-111">Il est toutefois important de noter que la désactivation de connecteurs pour le groupe Office 365 dont dépend une équipe peut également désactiver la possibilité de créer des liens pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="3a1d4-112">Ajouter un connecteur à un canal</span><span class="sxs-lookup"><span data-stu-id="3a1d4-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="3a1d4-113">Pour l’instant, vous pouvez ajouter des connecteurs à l’aide des clients de bureau et Web Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="3a1d4-114">Toutefois, les informations publiées par ces connecteurs peuvent être affichées dans **tous les clients** , y compris sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="3a1d4-115">Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (...),** à droite du nom d’un canal, puis cliquez sur **connecteurs**.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Capture d’écran de l’interface équipes avec l’option connecteurs sélectionnée](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="3a1d4-117">Vous pouvez choisir parmi un large éventail de connecteurs disponibles, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Capture d’écran de la boîte de dialogue connecteurs montrant les connecteurs disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="3a1d4-p105">Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="3a1d4-122">Les données fournies par le connecteur sont automatiquement publiées dans le canal.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="3a1d4-124">Développer des connecteurs personnalisés</span><span class="sxs-lookup"><span data-stu-id="3a1d4-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="3a1d4-125">Il est très facile de développer des connecteurs personnalisés qui peuvent être intégrés à vos applications métier.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="3a1d4-126">Pour créer un point de terminaison d' \*\*\*\* un canal qui collecte des données à partir de n’importe quelle application à l’aide de méthodes http post, vous pouvez utiliser le connecteur webhook intégré.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="3a1d4-127">Ajoutez le **webhook entrant** comme tout autre connecteur.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Capture d'écran avec l'option d'ajout du connecteur Webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="3a1d4-129">Pour créer un webhook, spécifiez un **nom**, mettez à jour l'image du webhook si nécessaire et cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Capture d’écran de la page de configuration pour le connecteur webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="3a1d4-131">Les applications qui envoient des données à ce canal nécessitent l’URL du connecteur webhook.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="3a1d4-132">Une URL unique est créée lors de la création du webhook.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="3a1d4-133">Partagez cette URL avec vos développeurs de sorte qu’ils puissent configurer leurs applications en fonction de la transmission des données, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Capture d'écran de l'URL unique du Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="3a1d4-135">Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Capture d'écran de l'interface Teams affichant un message Carte de connecteur.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="3a1d4-137">Les développeurs peuvent configurer leurs applications de manière à ce qu’elles créent ces cartes en envoyant une requête HTTP avec une charge utile JSON simple à l’adresse webhook d’une équipe, qui est une URL unique de ce point de terminaison fourni par l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="3a1d4-138">Faites en sorte que vos développeurs se réfèrent à la [prise en main de connecteurs Office 365 pour Microsoft teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), sur le réseau de développement Microsoft, qui comporte des instructions détaillées et des exemples de connecteurs.</span><span class="sxs-lookup"><span data-stu-id="3a1d4-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="3a1d4-139">D’autres ressources incluent [connecter des applications à vos groupes dans Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office-Microsoft teams](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="3a1d4-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
