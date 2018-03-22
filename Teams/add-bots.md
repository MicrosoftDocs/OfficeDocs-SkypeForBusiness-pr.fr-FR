---
title: Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50abaf5e6fb15451bfa1695ab2a16e0ce1747232
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="0d658-103">Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d658-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0d658-104">Les robots sont des programmes automatisés qui répondent aux requêtes ou donnent des mises à jour et notifications relatives aux utilisateurs de détails intéresser ou souhaitez rester informé sur.</span><span class="sxs-lookup"><span data-stu-id="0d658-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="0d658-105">Robots permettent aux utilisateurs d’interagir avec les services cloud tels que de la gestion des tâches, la planification et de l’interrogation, par le biais des conversations dans Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d658-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="0d658-106">Robots de Teams de Microsoft sont appuient sur le [Framework de robots de Microsoft](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="0d658-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="0d658-107">Les robots sont développés à l’aide de cette infrastructure peuvent être activés facilement pour Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d658-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="0d658-108">Pour plus d’informations, consultez [fonctionnalités de gérer des équipes de Microsoft dans votre organisation d’Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0d658-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="0d658-p102">Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="0d658-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="0d658-111">Les bots développés par la communauté peuvent être utilisés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d658-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="0d658-112">La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="0d658-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="0d658-113">Les bots peuvent être utilisés dans les conversations et canaux privés.</span><span class="sxs-lookup"><span data-stu-id="0d658-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="0d658-114">Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.</span><span class="sxs-lookup"><span data-stu-id="0d658-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="0d658-115">Pour plus d'informations, reportez-vous à la section « Utilisation des bots » dans la rubrique [Applications et services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="0d658-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="0d658-116">Création de bots personnalisés pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d658-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="0d658-p104">Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.</span><span class="sxs-lookup"><span data-stu-id="0d658-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="0d658-119">Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier.</span><span class="sxs-lookup"><span data-stu-id="0d658-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="0d658-120">Si vous ne le publiez pas, il reste privé.</span><span class="sxs-lookup"><span data-stu-id="0d658-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="0d658-121">Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot.</span><span class="sxs-lookup"><span data-stu-id="0d658-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="0d658-122">De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé.</span><span class="sxs-lookup"><span data-stu-id="0d658-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="0d658-123">Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs sur Azure Active Directory, au moyen de bots.</span><span class="sxs-lookup"><span data-stu-id="0d658-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="0d658-124">Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.</span><span class="sxs-lookup"><span data-stu-id="0d658-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="0d658-125">Chargement de version test de votre propre bot pour une conversation privée</span><span class="sxs-lookup"><span data-stu-id="0d658-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="0d658-126">Après avoir créé votre bot, accédez à la [page](https://go.microsoft.com/fwlink/?linkid=854374) de **tableau de bord** du bot que vous avez développé et sous **Détails**, copiez l **ID d’application Microsoft**.![Capture d'écran de la page détaillée d'un bot avec l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="0d658-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="0d658-127">Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**.</span><span class="sxs-lookup"><span data-stu-id="0d658-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="0d658-128">Dans **À**, collez l’**ID d’application Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0d658-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="0d658-129">![Capture d'écran d'un volet de discussion avec l'icône Ajouter une conversation et la ligne À de l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="0d658-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="0d658-130">L'ID d'application sera converti en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.</span><span class="sxs-lookup"><span data-stu-id="0d658-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
