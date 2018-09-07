---
title: Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lucarras
description: Découvrez comment ajouter des bots dans Microsoft Teams pour des conversations et des canaux privés, créer des bots personnalisés et charger une version test de votre propre bot pour une conversation privée.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ddb68dd5251d943e1fe3b6cca1aae2cf8fcb45
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867652"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="2615e-103">Ajouter des bots à des conversations et des canaux privés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2615e-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2615e-104">Robots sont des programmes automatisés qui répondent aux requêtes ou donnent des mises à jour et les notifications relatives aux utilisateurs de détails intéresser ou doit rester informés.</span><span class="sxs-lookup"><span data-stu-id="2615e-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="2615e-105">Robots permettent aux utilisateurs d’interagir avec les services de cloud comme la gestion de la tâche, la planification et l’interrogation, par le biais des conversations dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2615e-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="2615e-106">Robots pour Teams Microsoft reposent sur l' [Infrastructure de robot de Microsoft](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="2615e-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="2615e-107">Robots qui sont développées à l’aide de cette infrastructure peuvent être facilement activés pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2615e-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="2615e-108">Pour plus d’informations, voir [fonctionnalités de gestion des équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2615e-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="2615e-p102">Actuellement, Microsoft Teams prend en charge les bots dans les conversations et canaux privés dans une équipe. Les administrateurs peuvent contrôler l'autorisation ou l'interdiction de l'utilisation de bots dans le client Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="2615e-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="2615e-111">Les bots développés par la communauté peuvent être utilisés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2615e-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="2615e-112">La fonctionnalité et le chargement de version test de bot doivent être activés au niveau du client pour rendre les bots personnalisés fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="2615e-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="2615e-113">Les bots peuvent être utilisés dans les conversations et canaux privés.</span><span class="sxs-lookup"><span data-stu-id="2615e-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="2615e-114">Dans le cas des canaux, les propriétaires ou membres d'équipe peuvent ajouter des bots.</span><span class="sxs-lookup"><span data-stu-id="2615e-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="2615e-115">Pour plus d'informations, reportez-vous à la section « Utilisation des bots » dans la rubrique [Applications et services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="2615e-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="2615e-116">Création de bots personnalisés pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2615e-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="2615e-p104">Vous pouvez facilement créer un bot qui s'intègre à vos applications métier à l'aide de Bot Framework de Microsoft. Reportez-vous au guide [Creating and Testing a bot for Microsoft Teams (Création et test de bots pour Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=854371) pour connaître la procédure de développement et de publication de vos propres bots.</span><span class="sxs-lookup"><span data-stu-id="2615e-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="2615e-119">Lorsque vous créez un bot et l'enregistrez avec Bot Framework, vous pouvez décider de le publier.</span><span class="sxs-lookup"><span data-stu-id="2615e-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="2615e-120">Si vous ne le publiez pas, il reste privé.</span><span class="sxs-lookup"><span data-stu-id="2615e-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="2615e-121">Vous pouvez également demander à vos utilisateurs de se connecter avant d'utiliser le bot.</span><span class="sxs-lookup"><span data-stu-id="2615e-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="2615e-122">De cette manière, vous serez certain que seuls les employés de votre organisation y accèdent, même si l'ID d'application du bot venait à être révélé.</span><span class="sxs-lookup"><span data-stu-id="2615e-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="2615e-123">Reportez-vous à la page dédiée à [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) sur GitHub pour obtenir un exemple de code d'authentification des utilisateurs sur Azure Active Directory, au moyen de bots.</span><span class="sxs-lookup"><span data-stu-id="2615e-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="2615e-124">Les bots peuvent être testés à l'aide de l'[émulateur Bot Framework](https://go.microsoft.com/fwlink/?linkid=854373) avant de les déployer dans Teams.</span><span class="sxs-lookup"><span data-stu-id="2615e-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="2615e-125">Chargement de version test de votre propre bot pour une conversation privée</span><span class="sxs-lookup"><span data-stu-id="2615e-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="2615e-126">Après avoir créé votre robot, les **Paramètres de l’Application** pour le composant WebBot que vous avez développé, puis sous **paramètres de l’application**, copiez la valeur du paramètre **MicrosoftAppId** . ![Page de paramètres de capture d’écran de l’Application pour un robot avec l’ID d’application de Microsoft en surbrillance.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="2615e-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="2615e-127">Dans le volet **Conversation** de Microsoft Teams, sélectionnez l'icône **Ajouter une conversation**.</span><span class="sxs-lookup"><span data-stu-id="2615e-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="2615e-128">Dans **À**, collez l’**ID d’application Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="2615e-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="2615e-129">![Capture d'écran d'un volet de discussion avec l'icône Ajouter une conversation et la ligne À de l'ID d'application Microsoft mis en évidence.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="2615e-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="2615e-130">L'ID d'application sera converti en **nom de bot** et vous pourrez démarrer une conversation avec ce bot.</span><span class="sxs-lookup"><span data-stu-id="2615e-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
