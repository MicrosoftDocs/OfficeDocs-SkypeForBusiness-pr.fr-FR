---
title: Paramètres d'administration pour les applications dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: En savoir plus sur les stratégies et les paramètres que vous pouvez utiliser pour gérer des applications pour votre organisation dans Microsoft Teams.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30cbb5a29f88494c24474624a79ffa4ea8004025
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160361"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="18b6f-103">Paramètres d'administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18b6f-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="18b6f-104">Les applications fournissent des outils prédéfinis pour votre organisation afin de tirer le meilleur parti des équipes.</span><span class="sxs-lookup"><span data-stu-id="18b6f-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="18b6f-105">Ces applications associent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des robots proposés par Microsoft, par une tierce partie ou par les développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="18b6f-106">Vous gérez les applications pour votre organisation dans les **applications teams** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18b6f-106">You manage apps for your organization in **Teams apps** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="18b6f-107">Par exemple, vous pouvez autoriser ou bloquer des applications au niveau de l’organisation, définir des stratégies pour contrôler les applications disponibles pour les utilisateurs d’équipes et personnaliser les équipes en épinglant les applications les plus importantes à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="18b6f-107">For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="18b6f-108">Nous améliorons continuellement l’interface de l’application dans teams et en ajoutant des fonctions et fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="18b6f-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="18b6f-109">Au fil du temps, nous développons des fonctionnalités supplémentaires de gestion des applications, vous pouvez donc rechercher les informations les plus récentes sur les stratégies d’application.</span><span class="sxs-lookup"><span data-stu-id="18b6f-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="18b6f-110">Gestion des applications</span><span class="sxs-lookup"><span data-stu-id="18b6f-110">Manage apps</span></span>

<span data-ttu-id="18b6f-111">Utilisez la page **gérer les applications** pour afficher et gérer toutes les applications teams dans le catalogue d’applications de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="18b6f-112">Vous pouvez voir l’état de niveau de l’organisation et les propriétés des applications, bloquer ou autoriser des applications au niveau de l’organisation, télécharger de nouvelles applications personnalisées dans votre catalogue de clients et gérer les paramètres de l’application à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="18b6f-113">La page **gérer les applications** vous donne une vue d’ensemble des applications disponibles dans votre catalogue de clients, en fournissant les informations dont vous avez besoin pour déterminer les applications à autoriser ou à bloquer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="18b6f-114">Vous pouvez ensuite utiliser des [stratégies d’autorisation d’application](#app-permission-policies), des stratégies de [configuration d’application](#app-setup-policies)et des [stratégies et paramètres d’application personnalisés](#custom-app-policies-and-settings) pour configurer l’utilisation de l’application pour des utilisateurs spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="18b6f-115">Pour en savoir plus, voir [gérer les applications dans teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="18b6f-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="18b6f-116">Stratégies d’autorisation d’application</span><span class="sxs-lookup"><span data-stu-id="18b6f-116">App permission policies</span></span>

<span data-ttu-id="18b6f-117">Les stratégies d’autorisation d’applications vous permettent de contrôler les applications qui sont disponibles pour des utilisateurs spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="18b6f-118">Vous pouvez autoriser ou bloquer toutes les applications ou applications spécifiques publiées par Microsoft, des tiers et votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="18b6f-119">Par exemple, vous pouvez utiliser des stratégies d’autorisation d’application pour :</span><span class="sxs-lookup"><span data-stu-id="18b6f-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="18b6f-120">Déploiement graduel de nouvelles applications tierces ou personnalisées pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="18b6f-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="18b6f-121">Simplifiez l’utilisation de l’utilisateur, en particulier lorsque vous commencez à déployer des équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18b6f-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="18b6f-122">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="18b6f-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="18b6f-123">Stratégies de configuration des applications</span><span class="sxs-lookup"><span data-stu-id="18b6f-123">App setup policies</span></span>

<span data-ttu-id="18b6f-124">Les stratégies de configuration des applications vous permettent de personnaliser l’interface utilisateur de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="18b6f-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="18b6f-125">Vous choisissez les applications que vous voulez épingler à la barre de l’application dans les clients équipes et l’ordre dans lequel elles apparaissent, sur les clients Web, de bureau et mobiles.</span><span class="sxs-lookup"><span data-stu-id="18b6f-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="18b6f-126">Voici quelques exemples de la manière dont vous pouvez utiliser les stratégies de configuration des applications :</span><span class="sxs-lookup"><span data-stu-id="18b6f-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="18b6f-127">Sensibilisation et adoption des applications principales.</span><span class="sxs-lookup"><span data-stu-id="18b6f-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="18b6f-128">Par exemple, épinglez une application de gestion personnalisée de recrutement et de talent aux utilisateurs de votre équipe RH.</span><span class="sxs-lookup"><span data-stu-id="18b6f-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="18b6f-129">Épinglez de manière sélective les fonctionnalités principales d’équipe, telles que les discussions, les équipes et les appels.</span><span class="sxs-lookup"><span data-stu-id="18b6f-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="18b6f-130">Cela permet de garantir que les utilisateurs participent à des activités spécifiques dans Teams.</span><span class="sxs-lookup"><span data-stu-id="18b6f-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="18b6f-131">Pour en savoir plus, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="18b6f-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="18b6f-132">Paramètres et stratégies d’application personnalisés</span><span class="sxs-lookup"><span data-stu-id="18b6f-132">Custom app policies and settings</span></span>

<span data-ttu-id="18b6f-133">Teams permet aux développeurs de votre organisation de créer, tester et déployer des applications personnalisées pour les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="18b6f-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="18b6f-134">Les applications personnalisées peuvent être ajoutées à teams en téléchargeant un package d’application dans un fichier. zip directement dans une équipe ou dans le contexte personnel.</span><span class="sxs-lookup"><span data-stu-id="18b6f-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="18b6f-135">Vous pouvez utiliser les stratégies de configuration des applications pour contrôler les utilisateurs de votre organisation qui peuvent télécharger des applications personnalisées.</span><span class="sxs-lookup"><span data-stu-id="18b6f-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="18b6f-136">Vous pouvez également définir les paramètres à l’échelle de l’Organisation pour contrôler si les utilisateurs peuvent interagir avec des applications personnalisées spécifiques.</span><span class="sxs-lookup"><span data-stu-id="18b6f-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="18b6f-137">Pour plus d’informations, accédez à [gérer les stratégies et les paramètres d’application personnalisés dans teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="18b6f-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>