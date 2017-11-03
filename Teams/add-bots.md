---
title: "Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b1473a621f9f40ef3220546988db0635721acb7c
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="afb9b-103">Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afb9b-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="afb9b-p101">Les bots sont des programmes automatisés configurés pour répondre à des questions ou proposer des mises à jour et des notifications concernant des informations qui intéressent les utilisateurs ou à propos desquels ils souhaitent rester informés. Les bots permettent aux utilisateurs d'interagir avec des services cloud tels que la gestion des tâches, la planification et les sondages, via des conversations dans Microsoft Teams. Les bots pour Microsoft Teams sont créés dans [Bot Framework de Microsoft ](https://go.microsoft.com/fwlink/?linkid=854370) et les bots développés à l'aide de cette structure peuvent être facilement activés pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="afb9b-p102">Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="afb9b-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="afb9b-p103">Les bots développés par la communauté sont mis à disposition et peuvent être utilisés dans Microsoft Teams. La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels. Les bots peuvent être utilisés dans les conversations et canaux privés. Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p103">Bots developed by the community and are made available, can be leveraged within Microsoft Teams. The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional. Bots can be used in private chats or in channels. For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="afb9b-113">Ajout de bots pour les conversations et canaux privés</span><span class="sxs-lookup"><span data-stu-id="afb9b-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="afb9b-114">Il existe deux méthodes pour intégrer un bot aux conversations et canaux privés :</span><span class="sxs-lookup"><span data-stu-id="afb9b-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="afb9b-p104">Installation publique de bots disponibles pour les **conversations** ou les **canaux privés** (Première option)</span><span class="sxs-lookup"><span data-stu-id="afb9b-p104">Install publicly available bots for **private chat** or **channels**. (This is the first option.)</span></span>

2.  <span data-ttu-id="afb9b-117">Il est également possible de rechercher des bots : sélectionnez **Conversation**, recherchez un **contact,** et cliquez sur **Rechercher des applications.**</span><span class="sxs-lookup"><span data-stu-id="afb9b-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![Capture d'écran de la fenêtre Rechercher avec Rechercher des applications affiché comme résultat de recherche.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="afb9b-119">Sélectionnez le **Bot** avec lequel vous souhaitez discuter, comme indiqué ci-après.</span><span class="sxs-lookup"><span data-stu-id="afb9b-119">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![Capture d'écran de la fenêtre Rechercher des applications avec l'onglet Bots sélectionné.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="afb9b-121">Une fois sélectionné, octroyez des **autorisations** au bot et décidez si vous voulez l'utiliser **dans une conversation privée** ou dans une **équipe**.</span><span class="sxs-lookup"><span data-stu-id="afb9b-121">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![Capture d'écran de la page de l'application AzureBot.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="afb9b-p105">De même, pour utiliser un bot dans le canal d'une équipe, cliquez simplement sur **Afficher l'équipe et les bots**. Vous pouvez rechercher d'autres bots ici.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p105">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**. Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="afb9b-p106">À tout moment, un bot peut être supprimé de l'équipe. Cliquez simplement sur **Afficher l'équipe et les bots,** pour afficher tous les bots puis **supprimez ** celui de votre choix.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p106">At any time, a bot can be removed from the team. Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![Capture d'écran de l'onglet Bots qui affiche la description d'AzureBot.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="afb9b-128">Création de bots personnalisés pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afb9b-128">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="afb9b-p107">Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p107">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="afb9b-p108">Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier ou non. Si vous ne le publiez pas, le bot reste privé. Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot. De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé. Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs à Azure Active Directory, au moyen de bots.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p108">When you create a bot and register it with the Bot Framework, you can choose to publish it or not. If you don't publish it, the bot remains private. You can also require your users to log in before using the bot. Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known. See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="afb9b-136">Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.</span><span class="sxs-lookup"><span data-stu-id="afb9b-136">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="afb9b-137">Chargement de version test de votre propre bot pour une conversation privée</span><span class="sxs-lookup"><span data-stu-id="afb9b-137">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="afb9b-138">Lorsque vous avez créé votre bot, accédez à la page de **tableau de bord** [](https://go.microsoft.com/fwlink/?linkid=854374) du bot que vous avez développé et sous **Détails**, copiez l'**ID d'application Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="afb9b-138">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![Capture d'écran de la page détaillée d'un bot avec l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="afb9b-p109">Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**. Dans **À :,** collez l'**ID d'application Microsoft** de votre bot.</span><span class="sxs-lookup"><span data-stu-id="afb9b-p109">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![Capture d'écran d'un volet de discussion avec l'icône Ajouter une conversation et la ligne À de l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="afb9b-143">L'ID d'application sera convertie en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.</span><span class="sxs-lookup"><span data-stu-id="afb9b-143">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
