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
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50490b08986f1a8f312aa79d5492b1ed8a97ecc8
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="a041a-103">Paramètres d'administration pour les applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a041a-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a041a-p101">Les applications sont des onglets, des connecteurs, des robots ou n’importe quelle combinaison de ces trois, fournie par un service tiers. Il existe des stratégies d’admin équipes qui peuvent être configurés dans le centre d’administration Office 365 pour contrôler les applications de tiers externes sont autorisées. Ces stratégies vous permettent de spécifier les applications qui sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications à chargement latéral est autorisé.</span><span class="sxs-lookup"><span data-stu-id="a041a-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="a041a-107">Pour gérer les paramètres d’administration dans Teams, accédez au centre d’administration Office 365 et ouvrez l’option **Paramètres** > **Services et compléments**, puis sélectionnez **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="a041a-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="a041a-108">Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option :</span><span class="sxs-lookup"><span data-stu-id="a041a-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="a041a-109">Pour en savoir plus sur les paramètres d’administration, regardez la vidéo suivante :</span><span class="sxs-lookup"><span data-stu-id="a041a-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="a041a-110">Gestion de l’expérience des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a041a-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="a041a-111">Autoriser les applications externes dans Teams</span><span class="sxs-lookup"><span data-stu-id="a041a-111">Allow external apps in Teams</span></span>

<span data-ttu-id="a041a-112">Par défaut, le paramètre **Autoriser les applications externes dans Microsoft Teams** est activé avec toutes les applications sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a041a-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="a041a-113">Si vous désactivez cette option, tous les applications tierces externes sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="a041a-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="a041a-114">Activer les applications externes nouvelles par défaut</span><span class="sxs-lookup"><span data-stu-id="a041a-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="a041a-115">:trophée : meilleure pratique : gérer les applications externes individuellement</span><span class="sxs-lookup"><span data-stu-id="a041a-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="a041a-116">Pour activer certaines applications (et en désactiver d'autres), désactivez l'option **Autoriser le chargement de version test d'applications externes**.</span><span class="sxs-lookup"><span data-stu-id="a041a-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="a041a-117">Ensuite, désactivez les applications que vous ne voulez pas que les utilisateurs utilisent.</span><span class="sxs-lookup"><span data-stu-id="a041a-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="a041a-118">Facultatif : désactivez l'option **Activer les applications externes nouvelles par défaut** (si vous souhaitez contrôler les nouvelles applications).</span><span class="sxs-lookup"><span data-stu-id="a041a-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="a041a-119">Applications par défaut, tels que ceux créés par Microsoft, ne sont pas affectées par le paramètre **activer de nouvelles applications externes par défaut** .</span><span class="sxs-lookup"><span data-stu-id="a041a-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span>

<span data-ttu-id="a041a-120">Lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams.</span><span class="sxs-lookup"><span data-stu-id="a041a-120">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="a041a-121">Pour ouvrir le catalogue d'applications Teams, cliquez sur **Store** en bas de Teams et cliquez sur **Applications**.</span><span class="sxs-lookup"><span data-stu-id="a041a-121">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="a041a-122">Si vous souhaitez contrôler la disponibilité des applications, désactivez cette option.</span><span class="sxs-lookup"><span data-stu-id="a041a-122">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="a041a-123">Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes.</span><span class="sxs-lookup"><span data-stu-id="a041a-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="a041a-124">Le chargement de version test consiste à ajouter un application à Teams en chargeant un fichier .zip directement dans une équipe.</span><span class="sxs-lookup"><span data-stu-id="a041a-124">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="a041a-125">Le chargement de version test vous permet de tester une application au fur et à mesure qu'elle est développée.</span><span class="sxs-lookup"><span data-stu-id="a041a-125">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="a041a-126">Il vous permet également de créer une application à des fins d'utilisation interne uniquement et de la partager avec votre équipe sans l'envoyer dans le catalogue d'applications Teams dans l'Office Store.</span><span class="sxs-lookup"><span data-stu-id="a041a-126">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="a041a-127">Seuls les propriétaires ou membres d'équipes autorisés peuvent charger la version test d'une application dans Teams.</span><span class="sxs-lookup"><span data-stu-id="a041a-127">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Capture d’écran de la section applications de développé dans les paramètres clients.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="a041a-129">Création et chargement de packages d'application</span><span class="sxs-lookup"><span data-stu-id="a041a-129">Creating and uploading app packages</span></span> 

<span data-ttu-id="a041a-130">Pour en savoir plus sur les applications, voir [développer des applications pour les équipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="a041a-130">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



