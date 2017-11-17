---
title: "Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5adef4ea4c540523a0efffcf007a516f0a4efbbc
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="1b01b-103">Utiliser des connecteurs Office 365 et personnalisés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b01b-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="1b01b-p101">Les connecteurs permettent à votre équipe de rester informée en fournissant directement à votre canal du contenu et des mises à jour provenant des services que vous utilisez fréquemment. Grâce aux connecteurs, les utilisateurs de Microsoft Teams peuvent recevoir des mises à jour de services populaires, tels que Twitter, Trello, Wunderlist, GitHub et VSTS, dans le flux de conversations de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p101">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="1b01b-p102">Chaque membre d'une équipe peut associer son équipe à des services cloud populaires à l'aide des connecteurs, et tous les membres sont informés des activités de ce service. Si un utilisateur est supprimé d'une équipe, tous les connecteurs ajoutés à cette équipe par l'utilisateur en question cesseront de fonctionner. Les réunions restent programmées, car elles appartiennent au calendrier du groupe.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p102">Any member of a team can connect their team to popular cloud services with the connectors, and all team members are notified of activities from that service. If a user is removed from a team, any connectors added to the team by the removed user do stop working. Scheduled meetings continue to work because they're on the group calendar.</span></span>

<span data-ttu-id="1b01b-p103">Les connecteurs Office 365 peuvent être utilisés avec des groupes Microsoft Teams et Office 365, ce qui facilite la synchronisation de tous les membres et leur permet de recevoir rapidement des informations pertinentes. Microsoft Teams et Exchange utilisent le même modèle de connecteurs, ce qui vous permet d'utiliser les mêmes connecteurs sur les deux plateformes.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p103">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly. Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span>

<span data-ttu-id="1b01b-p104">Actuellement, les connecteurs peuvent être ajoutés à l'aide des clients de bureau et Web Microsoft Teams. Toutefois, les informations publiées par ces connecteurs peuvent être affichées à l'aide de **tous les clients** y compris mobiles.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p104">Currently, connectors can be added by using Microsoft Teams desktop and web clients. However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="1b01b-113">Pour ajouter un connecteur à un canal, cliquez sur les **points de suspension (…),** à droite du nom du canal, puis sur **Connecteurs.**</span><span class="sxs-lookup"><span data-stu-id="1b01b-113">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![Capture d'écran de l'interface Teams avec un nom de canal sélectionné et l'option Connecteurs sélectionnée.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="1b01b-115">Les utilisateurs peuvent effectuer une sélection parmi divers connecteurs disponibles, puis cliquer sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1b01b-115">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![Capture d'écran de la boîte de dialogue Connecteurs affichant les connecteurs disponibles pour être ajoutés.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="1b01b-p105">Renseignez les informations requises pour le connecteur sélectionné et cliquez sur **Enregistrer**. Chaque connecteur nécessite un ensemble d'informations pour fonctionner correctement et certains peuvent également requérir l'ouverture d'une session au service à l'aide des liens fournis dans la page de configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Capture d'écran de la page de configuration du connecteur RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="1b01b-120">Les données fournies par le connecteur sont automatiquement publiées dans le canal.</span><span class="sxs-lookup"><span data-stu-id="1b01b-120">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Capture d'écran de l'interface Teams affichant une conversation dans un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="1b01b-122">Développer des connecteurs personnalisés</span><span class="sxs-lookup"><span data-stu-id="1b01b-122">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="1b01b-p106">Développer des connecteurs personnalisés pouvant être intégrés à vos applications métier est très simple. Vous pouvez utiliser le connecteur **Webhook entrant** intégré pour créer un point de terminaison qui envoie les données à partir d'une application à l'aide des méthodes POST pour HTTP.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p106">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications. You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="1b01b-125">Ajoutez le **webhook entrant** comme tout autre connecteur.</span><span class="sxs-lookup"><span data-stu-id="1b01b-125">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Capture d'écran avec l'option d'ajout du connecteur Webhook entrant.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="1b01b-127">Pour créer un webhook, spécifiez un **nom**, mettez à jour l'image du webhook si nécessaire et cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="1b01b-127">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![<span data-ttu-id="1b01b-128">Capture d'écran de la page de configuration du connecteur Webhook entrant.</span><span class="sxs-lookup"><span data-stu-id="1b01b-128">Screenshot of the configuration page for the Incoming Webhook connector.</span></span> ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="1b01b-p107">Les applications qui envoient des données vers ce canal requièrent l'URL du connecteur webhook. Une **URL unique** est créée lors de la création du **webhook**. Partagez cette URL avec vos développeurs, pour leur permettre de configurer leurs applications pour envoyer des données lorsque nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p107">Applications that push data to this channel, require the Webhook connector URL. A **unique URL** is created when you created the **Webhook**. Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![Capture d'écran de l'URL unique du Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="1b01b-133">Lorsqu'une application externe envoie des données vers un connecteur, le message s'affiche dans la liste de conversations du canal sous forme de message spécial appelé **Carte de connecteur**.</span><span class="sxs-lookup"><span data-stu-id="1b01b-133">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Capture d'écran de l'interface Teams affichant un message Carte de connecteur.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="1b01b-p108">Les développeurs peuvent configurer leurs applications pour créer ces cartes, en envoyant une demande HTTP avec une charge JSON simple à l'adresse de webhook d'une équipe Microsoft, qui est une URL unique de ce point de terminaison fournie par l'assistant. Vos développeurs peuvent consulter l'article [Prise en main des connecteurs Office 365 pour Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), sur la page Microsoft Developer Network, pour obtenir des instructions détaillées et des exemples de connecteur. D'autres ressources telles que l'article [Connecter aux applications à vos groupes dans Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) et le [Centre de développement Office de Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) sont également disponibles.</span><span class="sxs-lookup"><span data-stu-id="1b01b-p108">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard. Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), on the Microsoft Developer Network, with detailed instructions and connector samples. Other resources include [Connect apps to your groups in Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
