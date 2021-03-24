---
title: Paramètres d'administration pour les applications dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Découvrez les stratégies et paramètres que vous pouvez utiliser pour gérer les applications pour votre organisation dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0594317c21f3ef2a30d1772959458f33bef393eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094380"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="51c81-103">Paramètres d'administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51c81-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="51c81-104">Les applications fournissent des outils pré-pratiques pour votre organisation afin de mieux out out de Teams.</span><span class="sxs-lookup"><span data-stu-id="51c81-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="51c81-105">Ces applications combinent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des bots fournis par Microsoft, par un tiers ou par des développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="51c81-106">Vous gérez les applications pour votre organisation dans **les applications Teams** dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="51c81-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="51c81-107">(Pour en [savoir plus sur l’obtention](./using-admin-roles.md) de rôles et d’autorisations d’administrateur, voir Utiliser les rôles d’administrateur Teams pour gérer Teams.) Par exemple, vous pouvez autoriser ou bloquer des applications au niveau de l’organisation, définir des stratégies pour contrôler quelles applications sont disponibles pour les utilisateurs de Teams et personnaliser Teams en épinglage des applications les plus importantes pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51c81-107">(See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="51c81-108">Nous améliorons continuellement l’expérience des applications dans Teams et ajoutons des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="51c81-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="51c81-109">Au fil du temps, nous allons créer des fonctionnalités de gestion des applications supplémentaires. Vérifiez donc que vous avez besoin des informations les plus à jour sur les stratégies d’application.</span><span class="sxs-lookup"><span data-stu-id="51c81-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="51c81-110">Gérer les applications</span><span class="sxs-lookup"><span data-stu-id="51c81-110">Manage apps</span></span>

<span data-ttu-id="51c81-111">Utilisez la page **Gérer les applications** pour afficher et gérer toutes les applications Teams dans le catalogue d’applications de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="51c81-112">Vous pouvez voir l’état au niveau de l’organisation et les propriétés des applications, bloquer ou autoriser des applications au niveau de l’organisation, télécharger de nouvelles applications personnalisées dans votre catalogue client et gérer les paramètres des applications à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="51c81-113">La page **Gérer les** applications vous permet d’afficher toutes les applications disponibles dans votre catalogue client, en vous fournissant les informations dont vous avez besoin pour décider des applications à autoriser ou bloquer dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="51c81-114">Vous pouvez ensuite utiliser des stratégies [d’autorisation](#app-permission-policies)d’application, [](#app-setup-policies)des stratégies de configuration d’application et des stratégies et paramètres d’application [personnalisés](#custom-app-policies-and-settings) pour configurer l’expérience d’application pour des utilisateurs spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="51c81-115">Pour en savoir plus, [consultez Gérer les applications dans Teams.](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="51c81-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="51c81-116">Stratégies d’autorisation d’application</span><span class="sxs-lookup"><span data-stu-id="51c81-116">App permission policies</span></span>

<span data-ttu-id="51c81-117">Les stratégies d’autorisation d’application vous permettent de contrôler quelles applications sont disponibles pour des utilisateurs spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="51c81-118">Vous pouvez autoriser ou bloquer toutes les applications ou des applications spécifiques publiées par Microsoft, par des tiers et par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="51c81-119">Par exemple, vous pouvez utiliser des stratégies d’autorisation d’application pour :</span><span class="sxs-lookup"><span data-stu-id="51c81-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="51c81-120">Déployer progressivement de nouvelles applications tierces ou personnalisées intégrées à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="51c81-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="51c81-121">Simplifiez l’expérience utilisateur, en particulier lorsque vous commencez à déployer Teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51c81-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="51c81-122">Pour en savoir plus, voir Gérer [les stratégies d’autorisation d’application dans Teams.](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="51c81-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="51c81-123">Stratégies de configuration des applications</span><span class="sxs-lookup"><span data-stu-id="51c81-123">App setup policies</span></span>

<span data-ttu-id="51c81-124">Les stratégies de configuration d’application vous personnalisationnt pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51c81-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="51c81-125">Vous choisissez les applications que vous voulez épingler à la barre de l’application dans les clients Teams et dans l’ordre dans lequel elles apparaissent, sur les clients web, de bureau et mobiles.</span><span class="sxs-lookup"><span data-stu-id="51c81-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="51c81-126">Voici quelques exemples d’utilisation des stratégies de configuration d’application :</span><span class="sxs-lookup"><span data-stu-id="51c81-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="51c81-127">Sens de la connaissance et de l’adoption des applications principales.</span><span class="sxs-lookup"><span data-stu-id="51c81-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="51c81-128">Par exemple, épinglez une application personnalisée de recrutement et de gestion des talents pour les utilisateurs de votre équipe RH.</span><span class="sxs-lookup"><span data-stu-id="51c81-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="51c81-129">Épinglez de manière sélective les principales fonctionnalités de Teams, telles que conversation, équipes et appels.</span><span class="sxs-lookup"><span data-stu-id="51c81-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="51c81-130">Cette action permet de s’assurer que les utilisateurs participent à des activités spécifiques dans Teams.</span><span class="sxs-lookup"><span data-stu-id="51c81-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="51c81-131">Pour en savoir plus, consultez [Gérer les stratégies de configuration d’application dans Teams.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="51c81-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="51c81-132">Stratégies et paramètres d’application personnalisés</span><span class="sxs-lookup"><span data-stu-id="51c81-132">Custom app policies and settings</span></span>

<span data-ttu-id="51c81-133">Teams permet aux développeurs de votre organisation de créer, tester et déployer des applications personnalisées vers d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51c81-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="51c81-134">Des applications personnalisées peuvent être ajoutées à Teams en téléchargeant un package d’application dans un fichier .zip directement dans une équipe ou dans le contexte personnel.</span><span class="sxs-lookup"><span data-stu-id="51c81-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="51c81-135">Vous pouvez utiliser des stratégies de configuration d’application pour contrôler les membres de votre organisation qui peuvent télécharger des applications personnalisées.</span><span class="sxs-lookup"><span data-stu-id="51c81-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="51c81-136">Vous pouvez également définir des paramètres à l’échelle de l’organisation pour contrôler si les utilisateurs peuvent interagir avec des applications personnalisées spécifiques.</span><span class="sxs-lookup"><span data-stu-id="51c81-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="51c81-137">Pour en savoir plus, voir Gérer les stratégies et [paramètres d’application personnalisées dans Teams.](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="51c81-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>