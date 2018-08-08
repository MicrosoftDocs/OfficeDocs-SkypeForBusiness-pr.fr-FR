---
title: Paramètres d'administration pour les applications dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Découvrez comment autoriser et activer des applications dans Microsoft Teams, y compris le chargement de version test d'applications externes.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82cd2de00fe053fb7255c7e4a692e1e85a8b1fe6
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "19106489"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="cdd69-103">Paramètres d'administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdd69-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="cdd69-p101">Les applications sont des onglets, les connecteurs, robots ou n’importe quelle combinaison de ces trois fournie par un service tiers. Des équipes d’administration stratégies peuvent être configurés dans le centre d’administration Office 365 pour contrôler les applications de tiers externes autorisées. Ces stratégies permettent de spécifier les applications qui sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications côté-chargement est autorisé.</span><span class="sxs-lookup"><span data-stu-id="cdd69-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="cdd69-107">Pour gérer les paramètres d’administration dans Teams, accédez au centre d’administration Office 365 et ouvrez l’option **Paramètres** > **Services et compléments**, puis sélectionnez **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="cdd69-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="cdd69-108">Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option :</span><span class="sxs-lookup"><span data-stu-id="cdd69-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="cdd69-109">Pour en savoir plus sur les paramètres d’administration, regardez la vidéo suivante :</span><span class="sxs-lookup"><span data-stu-id="cdd69-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="cdd69-110">Gestion de l’expérience des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdd69-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="cdd69-111">Autoriser les applications externes dans Teams</span><span class="sxs-lookup"><span data-stu-id="cdd69-111">Allow external apps in Teams</span></span>

<span data-ttu-id="cdd69-112">Par défaut, le paramètre **Autoriser les applications externes dans Microsoft Teams** est activé avec toutes les applications sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="cdd69-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="cdd69-113">Si vous désactivez cette option, tous les applications tierces externes sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="cdd69-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="cdd69-114">Activer les applications externes nouvelles par défaut</span><span class="sxs-lookup"><span data-stu-id="cdd69-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="cdd69-115">:trophée : meilleure pratique : gérer les applications externes individuellement</span><span class="sxs-lookup"><span data-stu-id="cdd69-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="cdd69-116">Pour activer certaines applications (et en désactiver d'autres), désactivez l'option **Autoriser le chargement de version test d'applications externes**.</span><span class="sxs-lookup"><span data-stu-id="cdd69-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="cdd69-117">Ensuite, désactivez les applications que vous ne voulez pas que les utilisateurs utilisent.</span><span class="sxs-lookup"><span data-stu-id="cdd69-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="cdd69-118">Facultatif : désactivez l'option **Activer les applications externes nouvelles par défaut** (si vous souhaitez contrôler les nouvelles applications).</span><span class="sxs-lookup"><span data-stu-id="cdd69-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="cdd69-119">Applications par défaut, telles que celles créées par Microsoft, ne sont pas affectées par le paramètre **activer de nouvelles applications externes par défaut** .</span><span class="sxs-lookup"><span data-stu-id="cdd69-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="cdd69-120">Nouvelles applications sont activées par défaut lorsque l’utilisateur relâche par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdd69-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="cdd69-121">Lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams.</span><span class="sxs-lookup"><span data-stu-id="cdd69-121">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="cdd69-122">Pour ouvrir le catalogue d'applications Teams, cliquez sur **Store** en bas de Teams et cliquez sur **Applications**.</span><span class="sxs-lookup"><span data-stu-id="cdd69-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="cdd69-123">Si vous souhaitez contrôler la disponibilité des applications, désactivez cette option.</span><span class="sxs-lookup"><span data-stu-id="cdd69-123">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="cdd69-124">Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes.</span><span class="sxs-lookup"><span data-stu-id="cdd69-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="cdd69-125">Le chargement de version test consiste à ajouter un application à Teams en chargeant un fichier .zip directement dans une équipe.</span><span class="sxs-lookup"><span data-stu-id="cdd69-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="cdd69-126">Le chargement de version test vous permet de tester une application au fur et à mesure qu'elle est développée.</span><span class="sxs-lookup"><span data-stu-id="cdd69-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="cdd69-127">Il vous permet également de créer une application à des fins d'utilisation interne uniquement et de la partager avec votre équipe sans l'envoyer dans le catalogue d'applications Teams dans l'Office Store.</span><span class="sxs-lookup"><span data-stu-id="cdd69-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="cdd69-128">Seuls les propriétaires ou membres d'équipes autorisés peuvent charger la version test d'une application dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cdd69-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Capture d’écran de la section applications de développé dans les paramètres au niveau du client.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="cdd69-130">Création et chargement de packages d'application</span><span class="sxs-lookup"><span data-stu-id="cdd69-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="cdd69-131">Pour en savoir plus sur les applications, voir [Develop apps pour les équipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="cdd69-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



