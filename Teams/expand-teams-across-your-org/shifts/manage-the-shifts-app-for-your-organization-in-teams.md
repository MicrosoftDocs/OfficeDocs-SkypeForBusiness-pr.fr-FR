---
title: Gestion de l’application Shifts pour votre organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment configurer et gérer l’application Shifts dans teams pour terrain travailleurs de votre organisation.
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
ms.openlocfilehash: d89ca8938c80b2afb8c1b32a395ab4a984327dcc
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790506"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="de6ad-103">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de6ad-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de6ad-104">À compter du 30 juin 2020, Microsoft StaffHub a été annulé.</span><span class="sxs-lookup"><span data-stu-id="de6ad-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="de6ad-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de6ad-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="de6ad-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="de6ad-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="de6ad-107">StaffHub a cessé de fonctionner pour tous les utilisateurs du 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="de6ad-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="de6ad-108">Tout utilisateur qui tente d’ouvrir StaffHub est affiché un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="de6ad-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="de6ad-109">Pour en savoir plus, consultez la section le [retrait de Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="de6ad-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="de6ad-110">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="de6ad-110">Overview of Shifts</span></span>

<span data-ttu-id="de6ad-111">L’application Shifts dans Microsoft teams permet aux utilisateurs de terrain de se connecter et de se synchroniser avec eux. Il s’agit d’abord sur un appareil mobile pour une gestion rapide et efficace du temps pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="de6ad-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="de6ad-112">Les Shifts permettent à terrain travailleurs et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en interaction.</span><span class="sxs-lookup"><span data-stu-id="de6ad-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="de6ad-113">Les responsables créent, mettent à jour et gèrent les plannings de Shifts pour Teams.</span><span class="sxs-lookup"><span data-stu-id="de6ad-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="de6ad-114">Ils peuvent envoyer des messages à une personne (« il y a un renversé sur le plancher ») ou à l’équipe entière (« le GM régional arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="de6ad-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="de6ad-115">Ils peuvent également envoyer des documents de stratégie, des bulletins d’actualité et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="de6ad-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="de6ad-116">Les employés peuvent afficher leurs Shifts à venir, peuvent voir qui est programmé pour la journée, demander à échanger ou proposer un Shift et demander du temps.</span><span class="sxs-lookup"><span data-stu-id="de6ad-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="de6ad-117">Il est important de savoir que les Shifts ne prennent actuellement pas en charge les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="de6ad-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="de6ad-118">Cela signifie que les invités ne peuvent pas être ajoutés à une équipe ou utiliser les plannings de décalage lorsque l’accès invité est activé dans Teams.</span><span class="sxs-lookup"><span data-stu-id="de6ad-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="de6ad-119">Pour plus d’informations sur les fonctionnalités de décalage sur différentes plateformes, voir [fonctionnalités d’équipes par plate-forme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="de6ad-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="de6ad-120">Disponibilité des équipes</span><span class="sxs-lookup"><span data-stu-id="de6ad-120">Availability of Shifts</span></span>

<span data-ttu-id="de6ad-121">Le changement est disponible dans toutes les références de l’entreprise, où teams est disponible.</span><span class="sxs-lookup"><span data-stu-id="de6ad-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="de6ad-122">Emplacement des données de décalage</span><span class="sxs-lookup"><span data-stu-id="de6ad-122">Location of Shifts data</span></span>

<span data-ttu-id="de6ad-123">Les données de décalage sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord, en Europe de l’Ouest et en Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="de6ad-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="de6ad-124">Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="de6ad-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="de6ad-125">Configurer les Shifts</span><span class="sxs-lookup"><span data-stu-id="de6ad-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="de6ad-126">Activer ou désactiver les équipes au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="de6ad-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="de6ad-127">Les Shifts sont activés par défaut pour tous les utilisateurs d’équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="de6ad-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="de6ad-128">Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de6ad-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="de6ad-129">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.</span><span class="sxs-lookup"><span data-stu-id="de6ad-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="de6ad-130">Dans la liste des applications, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="de6ad-130">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="de6ad-131">Pour désactiver les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **bloquer** .</span><span class="sxs-lookup"><span data-stu-id="de6ad-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block** .</span></span>
    - <span data-ttu-id="de6ad-132">Pour activer les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **allow** .</span><span class="sxs-lookup"><span data-stu-id="de6ad-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow** .</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="de6ad-133">Activer ou désactiver les équipes pour des utilisateurs spécifiques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="de6ad-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="de6ad-134">Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des équipes, assurez-vous que les Shifts sont activés pour votre organisation dans la page [gérer les applications](../../manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de6ad-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="de6ad-135">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de6ad-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="de6ad-136">Utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler les équipes dans teams</span><span class="sxs-lookup"><span data-stu-id="de6ad-136">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="de6ad-137">Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="de6ad-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="de6ad-138">Les applications définies dans une stratégie sont épinglées à la barre de l’application &mdash; , qui se trouve sur le côté du client de bureau teams et dans la partie inférieure des clients mobiles Teams, &mdash; où les utilisateurs peuvent y accéder rapidement et facilement.</span><span class="sxs-lookup"><span data-stu-id="de6ad-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="de6ad-139">Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez affecter à des employés terrain dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="de6ad-139">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="de6ad-140">Par défaut, la stratégie inclut les applications activités, équipes, discussions et appels.</span><span class="sxs-lookup"><span data-stu-id="de6ad-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="de6ad-141">Pour afficher la stratégie FirstlineWorker, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration de l’application **teams**  >  **App setup policies** .</span><span class="sxs-lookup"><span data-stu-id="de6ad-141">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies** .</span></span>

<span data-ttu-id="de6ad-142">![Capture d’écran de la stratégie de configuration de l’application FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FirstlineWorker dans le centre d’administration Microsoft teams")</span><span class="sxs-lookup"><span data-stu-id="de6ad-142">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="de6ad-143">Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="de6ad-143">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="de6ad-144">Effectuer une recherche dans le journal d’audit pour les événements de décalage</span><span class="sxs-lookup"><span data-stu-id="de6ad-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="de6ad-145">**(version d’évaluation)**</span><span class="sxs-lookup"><span data-stu-id="de6ad-145">**(in preview)**</span></span>

<span data-ttu-id="de6ad-146">Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité de décalage au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="de6ad-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="de6ad-147">Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des [activités de décalage](../../audit-log-events.md#shifts-in-teams-activities) enregistrées dans le journal d’audit, voir [effectuer des recherches dans le journal d’audit pour les événements dans teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="de6ad-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="de6ad-148">Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="de6ad-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="de6ad-149">Pour plus d’informations, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="de6ad-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="de6ad-150">Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.</span><span class="sxs-lookup"><span data-stu-id="de6ad-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="de6ad-151">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="de6ad-151">Related topics</span></span>

- [<span data-ttu-id="de6ad-152">Aide sur les équipes pour les travailleurs terrain</span><span class="sxs-lookup"><span data-stu-id="de6ad-152">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="de6ad-153">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="de6ad-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
