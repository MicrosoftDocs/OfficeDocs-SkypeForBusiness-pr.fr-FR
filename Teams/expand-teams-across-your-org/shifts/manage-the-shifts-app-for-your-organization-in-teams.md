---
title: Gérer l’application Plannings pour votre organisation dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment configurer et gérer l’application Plannings dans Teams pour les employés de bureau de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909088"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="7e997-103">Gérer l’application Plannings pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e997-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e997-104">Microsoft StaffHub n’existe plus depuis le 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="7e997-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="7e997-105">Nous développons les fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7e997-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7e997-106">Aujourd’hui, Teams inclut l’application Plannings pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="7e997-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7e997-107">StaffHub a cessé de fonctionner pour tous les utilisateurs le 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="7e997-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="7e997-108">Toute personne qui essaie d’ouvrir StaffHub s’afficher un message lui permettant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="7e997-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="7e997-109">Pour en savoir plus, consultez l’article [Microsoft StaffHub n’existe plus](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="7e997-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="7e997-110">Vue d’ensemble de Plannings</span><span class="sxs-lookup"><span data-stu-id="7e997-110">Overview of Shifts</span></span>

<span data-ttu-id="7e997-111">L’application Plannings de Microsoft Teams maintient la connexion et la synchronisation des employés de bureau. Il est conçu en avant-première pour la gestion du temps et la communication rapides et efficaces pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="7e997-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="7e997-112">Plannings permet aux employés de première ligne et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et communiquer.  </span><span class="sxs-lookup"><span data-stu-id="7e997-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="7e997-113">Les responsables créent, mettent à jour et gèrent les plannings relatifs aux roulements de équipes.</span><span class="sxs-lookup"><span data-stu-id="7e997-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="7e997-114">Ils peuvent envoyer des messages à un membre en particulier (« du liquide s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="7e997-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="7e997-115">Ils peuvent aussi envoyer des documents stratégiques, des bulletins d’informations et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="7e997-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="7e997-116">Les employés peuvent consulter leurs horaires de travail, voir qui est prévu pour la journée, demander à échanger ou offrir une shift, et demander des congés.</span><span class="sxs-lookup"><span data-stu-id="7e997-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="7e997-117">Il est important de savoir que Plannings ne prend pas en charge les utilisateurs invités pour le moment.</span><span class="sxs-lookup"><span data-stu-id="7e997-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="7e997-118">Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés à des plannings de shift ou utiliser ceux-ci lorsque l’accès invité est désactivé dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7e997-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="7e997-119">Pour plus d’informations sur les fonctionnalités Shifts sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="7e997-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="7e997-120">Disponibilité de Plannings</span><span class="sxs-lookup"><span data-stu-id="7e997-120">Availability of Shifts</span></span>

<span data-ttu-id="7e997-121">Plannings est disponible dans toutes les références Entreprise où Teams est disponible.</span><span class="sxs-lookup"><span data-stu-id="7e997-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="7e997-122">Emplacement des données Plannings</span><span class="sxs-lookup"><span data-stu-id="7e997-122">Location of Shifts data</span></span>

<span data-ttu-id="7e997-123">Les données Plannings sont actuellement stockées dans Azure dans des centres de données en Amérique du Nord, en Europe de l’ouest et en Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="7e997-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="7e997-124">Pour plus d’informations sur l’emplacement de stockage des données, voir [Où se trouvent mes données](http://o365datacentermap.azurewebsites.net/) ?</span><span class="sxs-lookup"><span data-stu-id="7e997-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="7e997-125">Configurer des Plannings</span><span class="sxs-lookup"><span data-stu-id="7e997-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="7e997-126">Activer ou désactiver Plannings dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="7e997-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="7e997-127">Plannings est activé par défaut pour tous les utilisateurs Teams de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7e997-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="7e997-128">Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7e997-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="7e997-129">Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="7e997-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="7e997-130">Dans la liste des applications, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e997-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="7e997-131">Pour désactiver Plannings pour votre organisation, recherchez l’application Plannings, sélectionnez-la, puis sélectionnez **Bloquer**.</span><span class="sxs-lookup"><span data-stu-id="7e997-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="7e997-132">Pour activer Plannings pour votre organisation, recherchez l’application Plannings, sélectionnez-la, puis sélectionnez **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="7e997-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="7e997-133">Activer ou désactiver Plannings pour des utilisateurs spécifiques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="7e997-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="7e997-134">Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Plannings, assurez-vous que Plannings est activé pour votre organisation sur la page [Gérer les applications](../../manage-apps.md), puis créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7e997-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="7e997-135">Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7e997-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="7e997-136">Utiliser une stratégie de configuration d’application pour épingler Tasks dans Teams</span><span class="sxs-lookup"><span data-stu-id="7e997-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="7e997-137">Les stratégies de configuration des applications vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7e997-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="7e997-138">Les applications que vous définissez dans une stratégie sont épinglées à la barre d’applications&mdash;, la barre se trouvant sur le côté du client Teams pour ordinateur de bureau et en bas des clients mobiles Teams&mdash; là où les utilisateurs peuvent y accéder rapidement et facilement.</span><span class="sxs-lookup"><span data-stu-id="7e997-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="7e997-139">Teams inclut une stratégie de configuration d’application FrontlineWorker intégrée que vous pouvez affecter aux employés de terrain dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7e997-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="7e997-140">Par défaut, la stratégie inclut les applications Activité, Plannings, Conversation et Appel.</span><span class="sxs-lookup"><span data-stu-id="7e997-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="7e997-141">Pour afficher la stratégie FrontlineWorker, dans le menu de navigation gauche du Centre d’administration Microsoft Teams, consultez **Application Teams** > **Stratégies configuration d’application**.</span><span class="sxs-lookup"><span data-stu-id="7e997-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="7e997-142">![Capture d’écran de la stratégie de configuration de l’application FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FrontlineWorker dans le Centre d’administration Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="7e997-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="7e997-143">Attribuer la stratégie de configuration de l’application FrontlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7e997-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="7e997-144">Rechercher des événements de Plannings dans le journal d’audit </span><span class="sxs-lookup"><span data-stu-id="7e997-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="7e997-145">**(version d’évaluation)**</span><span class="sxs-lookup"><span data-stu-id="7e997-145">**(in preview)**</span></span>

<span data-ttu-id="7e997-146">Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité shifts au niveau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7e997-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="7e997-147">Pour en savoir plus sur la façon d'effectuer une recherche dans le journal d'audit et pour consulter la liste des [Activités Plannings](../../audit-log-events.md#shifts-in-teams-activities) qui sont enregistrées dans le journal d'audit, consultez [Recherche d'événements dans le journal d'audit dans Teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="7e997-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="7e997-148">Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="7e997-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="7e997-149">Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="7e997-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="7e997-150">N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.</span><span class="sxs-lookup"><span data-stu-id="7e997-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e997-151">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7e997-151">Related topics</span></span>

- [<span data-ttu-id="7e997-152">Aide Plannings pour les employés de bureau</span><span class="sxs-lookup"><span data-stu-id="7e997-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="7e997-153">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7e997-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
