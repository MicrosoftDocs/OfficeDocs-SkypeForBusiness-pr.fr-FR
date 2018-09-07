---
title: Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver les applications Microsoft Teams dans votre organisation Office 365, notamment des onglets, des connecteurs, des robots ou n’importe quelle combinaison des trois.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9be3c44f441238033c383dc5e42240207f3095c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867700"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="f7203-103">Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365</span><span class="sxs-lookup"><span data-stu-id="f7203-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f7203-104">Tous les paramètres d’équipes seront bientôt migrés au nouveau Microsoft Teams & Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="f7203-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="f7203-105">La seule fonctionnalité équipes qui est gérée dans le centre d’administration Office 365 est apps.</span><span class="sxs-lookup"><span data-stu-id="f7203-105">The only Teams feature that is managed in the Office 365 admin center is apps.</span></span> 

<span data-ttu-id="f7203-106">Sauf indication contraire, une option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="f7203-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="f7203-107">Pour gérer les paramètres d'administration dans Teams, accédez au Centre d'administration Office 365 et ouvrez **Paramètres** > **Services et compléments**, puis sélectionnez **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f7203-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="f7203-108">Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option :</span><span class="sxs-lookup"><span data-stu-id="f7203-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="f7203-109">Paramètres à l'échelle du client Office 365</span><span class="sxs-lookup"><span data-stu-id="f7203-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="f7203-110">Dans les **paramètres au niveau du client**, vous pouvez activer ou désactiver les applications.</span><span class="sxs-lookup"><span data-stu-id="f7203-110">In **Tenant-wide settings**, you can turn on or turn off apps.</span></span>

<span data-ttu-id="f7203-111">Pour modifier les **paramètres à l'échelle du client** de Teams, accédez au Centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7203-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="f7203-112">Sélectionnez **Paramètres** > **Services et compléments** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f7203-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="f7203-113">Applications</span><span class="sxs-lookup"><span data-stu-id="f7203-113">Apps</span></span>

<span data-ttu-id="f7203-114">Les applications sont des onglets, des connecteurs, des bots ou n'importe quelle combinaison de ces éléments, fournis par un service tiers.</span><span class="sxs-lookup"><span data-stu-id="f7203-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="f7203-115">Des stratégies d'administration de Teams peuvent être configurées dans le Centre d'administration Office 365 pour contrôler l'autorisation d'applications tierces externes.</span><span class="sxs-lookup"><span data-stu-id="f7203-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="f7203-116">Ces stratégies permettent de spécifier les applications qui sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications côté-chargement est autorisé.</span><span class="sxs-lookup"><span data-stu-id="f7203-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="f7203-117">La section **Applications** vous permet de configurer les paramètres suivants pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="f7203-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Capture d'écran de la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="f7203-119">**Autoriser les applications externes dans Microsoft Teams :** lorsque cette option est activée, les utilisateurs peuvent ajouter des onglets et des bots disponibles pour le client Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7203-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Capture d'écran de la commande Autoriser les applications externes dans la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="f7203-121">**Activer les applications externes nouvelles par défaut** : lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams.</span><span class="sxs-lookup"><span data-stu-id="f7203-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="f7203-122">Désactivez cette option si vous souhaitez contrôler les nouvelles applications.</span><span class="sxs-lookup"><span data-stu-id="f7203-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="f7203-123">Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes.</span><span class="sxs-lookup"><span data-stu-id="f7203-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="f7203-124">**Autoriser le chargement des versions de test d'applications externes :** lorsque cette option est activée, les utilisateurs peuvent installer et activer des bots et onglets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f7203-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="f7203-125">Pour en savoir plus, consultez la rubrique [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f7203-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

