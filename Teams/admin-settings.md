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
ms.openlocfilehash: d85aa5435d05d5f296b06e56841a2e10c7ddd413
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826872"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="fa49c-103">Paramètres d'administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa49c-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="fa49c-104">Les applications fournissent des outils prédéfinis pour votre organisation afin de tirer le meilleur parti des équipes.</span><span class="sxs-lookup"><span data-stu-id="fa49c-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="fa49c-105">Ces applications associent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des robots proposés par Microsoft, par une tierce partie ou par les développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa49c-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="fa49c-106">Dans le centre d' **administration de Microsoft** Teams, vous pouvez définir des stratégies pour gérer les applications pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa49c-106">In **Teams apps** in the Microsoft Teams admin center, you can set policies to manage apps for your organization.</span></span> <span data-ttu-id="fa49c-107">Par exemple, vous pouvez définir des stratégies pour contrôler les applications qui sont disponibles pour les utilisateurs d’équipes et vous pouvez personnaliser teams en épinglant les applications les plus importantes à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fa49c-107">For example, you can set policies to control what apps are available to Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="fa49c-108">Nous améliorons continuellement l’interface de l’application dans teams et en ajoutant des fonctions et fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="fa49c-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="fa49c-109">Au fil du temps, nous développons des fonctionnalités supplémentaires de gestion des applications, vous pouvez donc rechercher les informations les plus récentes sur les stratégies d’application.</span><span class="sxs-lookup"><span data-stu-id="fa49c-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="fa49c-110">Stratégies d’autorisation d’application</span><span class="sxs-lookup"><span data-stu-id="fa49c-110">App permission policies</span></span>

<span data-ttu-id="fa49c-111">Grâce aux stratégies d’autorisation d’application, vous pouvez bloquer ou autoriser des applications, à l’échelle de l’organisation ou pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fa49c-111">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="fa49c-112">Lorsque vous bloquez une application, toutes les interactions avec cette application sont désactivées et l’application n’apparaît pas dans teams pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fa49c-112">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="fa49c-113">Par exemple, vous pouvez utiliser des stratégies d’autorisation d’application pour :</span><span class="sxs-lookup"><span data-stu-id="fa49c-113">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="fa49c-114">Désactiver une application qui génère un risque d’autorisation ou de perte de données pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa49c-114">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="fa49c-115">Déploiement graduel de nouvelles applications tierces ou personnalisées pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fa49c-115">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="fa49c-116">Simplifiez l’utilisation de l’utilisateur, en particulier lorsque vous commencez à déployer des équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa49c-116">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="fa49c-117">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fa49c-117">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="fa49c-118">Stratégies de configuration des applications</span><span class="sxs-lookup"><span data-stu-id="fa49c-118">App setup policies</span></span>

<span data-ttu-id="fa49c-119">Les stratégies de configuration des applications vous permettent de personnaliser l’interface utilisateur de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fa49c-119">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="fa49c-120">Vous choisissez les applications que vous voulez épingler à la barre de l’application dans les clients équipes et l’ordre dans lequel elles apparaissent, sur les clients Web, de bureau et mobiles.</span><span class="sxs-lookup"><span data-stu-id="fa49c-120">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="fa49c-121">Voici quelques exemples de la manière dont vous pouvez utiliser les stratégies de configuration des applications :</span><span class="sxs-lookup"><span data-stu-id="fa49c-121">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="fa49c-122">Sensibilisation et adoption des applications principales.</span><span class="sxs-lookup"><span data-stu-id="fa49c-122">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="fa49c-123">Par exemple, épinglez une application de gestion personnalisée de recrutement et de talent aux utilisateurs de votre équipe RH.</span><span class="sxs-lookup"><span data-stu-id="fa49c-123">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="fa49c-124">Épinglez de manière sélective les fonctionnalités principales d’équipe, telles que les discussions, les équipes et les appels.</span><span class="sxs-lookup"><span data-stu-id="fa49c-124">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="fa49c-125">Cela permet de garantir que les utilisateurs participent à des activités spécifiques dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fa49c-125">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="fa49c-126">Pour en savoir plus, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fa49c-126">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="fa49c-127">Paramètres et stratégies d’application personnalisés</span><span class="sxs-lookup"><span data-stu-id="fa49c-127">Custom app policies and settings</span></span>

<span data-ttu-id="fa49c-128">Teams permet aux développeurs de votre organisation de créer, tester et déployer des applications personnalisées pour les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fa49c-128">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="fa49c-129">Les applications personnalisées peuvent être ajoutées à teams en téléchargeant un package d’application dans un fichier. zip directement dans une équipe ou dans le contexte personnel.</span><span class="sxs-lookup"><span data-stu-id="fa49c-129">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="fa49c-130">Vous pouvez utiliser les stratégies de configuration des applications pour contrôler les utilisateurs de votre organisation qui peuvent télécharger des applications personnalisées.</span><span class="sxs-lookup"><span data-stu-id="fa49c-130">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="fa49c-131">Vous pouvez également définir les paramètres à l’échelle de l’Organisation pour contrôler si les utilisateurs peuvent interagir avec des applications personnalisées spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fa49c-131">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="fa49c-132">Pour plus d’informations, accédez à [gérer les stratégies et les paramètres d’application personnalisés dans teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fa49c-132">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>