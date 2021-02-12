---
title: Gérer l’application Shifts pour votre organisation
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
description: Découvrez comment configurer et gérer l’application Shifts dans Teams pour les employés en ligne de votre organisation.
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
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909088"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="fa1bf-103">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa1bf-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa1bf-104">Microsoft StaffHub a été retiré le 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="fa1bf-105">Nous allons développer les fonctionnalités de StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="fa1bf-106">Aujourd’hui, Teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployer au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="fa1bf-107">StaffHub a cessé de fonctionner pour tous les utilisateurs le 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="fa1bf-108">Tous les autres personnes qui tentent d’ouvrir StaffHub s’afficheront un message les en directe pour télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="fa1bf-109">Pour en savoir plus, [voir Microsoft StaffHub a été retiré.](microsoft-staffhub-to-be-retired.md)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="fa1bf-110">Vue d’ensemble de Shifts</span><span class="sxs-lookup"><span data-stu-id="fa1bf-110">Overview of Shifts</span></span>

<span data-ttu-id="fa1bf-111">L’application Shifts de Microsoft Teams maintient la connexion et la synchronisation des employés en contact direct avec les employés en contact. Il est conçu en premier lieu pour une gestion et une communication rapides et efficaces pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="fa1bf-112">Shifts permet aux employés en contact direct et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en contact.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="fa1bf-113">Les responsables créent, actualent et gèrent les plannings des shifts pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="fa1bf-114">Ils peuvent envoyer des messages à une personne (« du spill s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="fa1bf-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="fa1bf-115">Ils peuvent également envoyer des documents stratégiques, des bulletins d’informations et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="fa1bf-116">Les employés voient leurs shifts à venir, voient qui d’autre est programmé pour la journée, demandent à échanger ou proposer un shift et demandent un congé.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="fa1bf-117">Il est important de savoir que Shifts ne prend pas en charge les utilisateurs invités pour le moment.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="fa1bf-118">Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés ou utiliser des plannings de shift lorsque l’accès invité est désactivé dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="fa1bf-119">Pour plus d’informations sur les fonctionnalités de Shifts sur différentes plateformes, consultez [les fonctionnalités de Teams par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="fa1bf-120">Disponibilité de Shifts</span><span class="sxs-lookup"><span data-stu-id="fa1bf-120">Availability of Shifts</span></span>

<span data-ttu-id="fa1bf-121">Shifts est disponible dans toutes les S SKUS Entreprise où Teams est disponible.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="fa1bf-122">Emplacement des données Shifts</span><span class="sxs-lookup"><span data-stu-id="fa1bf-122">Location of Shifts data</span></span>

<span data-ttu-id="fa1bf-123">Les données shifts sont actuellement stockées dans Azure dans des centres de données en Amérique du Nord, en Europe de l’ouest et en Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="fa1bf-124">Pour plus d’informations sur l’endroit où sont stockées les données, voir [Où se trouve mes données](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="fa1bf-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="fa1bf-125">Configurer Shifts</span><span class="sxs-lookup"><span data-stu-id="fa1bf-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="fa1bf-126">Activer ou désactiver shifts dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="fa1bf-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="fa1bf-127">Shifts est activé par défaut pour tous les utilisateurs de Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="fa1bf-128">Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les](../../manage-apps.md) applications du Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="fa1bf-129">Dans le navigation gauche du Centre d’administration Microsoft Teams, allez dans les **applications Teams**  >  **Gérer les applications.**</span><span class="sxs-lookup"><span data-stu-id="fa1bf-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="fa1bf-130">Dans la liste des applications, faites l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa1bf-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="fa1bf-131">Pour désactiver Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis choisissez **Bloquer.**</span><span class="sxs-lookup"><span data-stu-id="fa1bf-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="fa1bf-132">Pour activer Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis **sélectionnez Autoriser.**</span><span class="sxs-lookup"><span data-stu-id="fa1bf-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="fa1bf-133">Activer ou désactiver les shifts pour des utilisateurs spécifiques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="fa1bf-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="fa1bf-134">Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Shifts, assurez-vous que Shifts est désactivé pour votre organisation sur la [page](../../manage-apps.md) Gérer les applications, puis créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="fa1bf-135">Pour en savoir plus, consultez [Gérer les stratégies d’autorisation d’application dans Teams.](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="fa1bf-136">Utiliser la stratégie de configuration de l’application FrontlineWorker pour épingler Shifts à Teams</span><span class="sxs-lookup"><span data-stu-id="fa1bf-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="fa1bf-137">Les stratégies de configuration d’application vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="fa1bf-138">Les applications définies dans une stratégie sont épinglées à la barre de l’application sur le côté du client de bureau Teams et en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et &mdash; &mdash; facilement.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="fa1bf-139">Teams inclut une stratégie de configuration d’application FrontlineWorker intégrée que vous pouvez affecter aux employés de votre organisation qui travaillent en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="fa1bf-140">Par défaut, la stratégie inclut les applications Activité, Shifts, Conversation et Appel.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="fa1bf-141">Pour afficher la stratégie FrontlineWorker, dans le menu de navigation gauche du Centre d’administration Microsoft Teams, consultez les stratégies de configuration de **l’application Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="fa1bf-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="fa1bf-142">![Capture d’écran de la stratégie de configuration de l’application FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FrontlineWorker dans le Centre d’administration Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="fa1bf-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="fa1bf-143">Affecter la stratégie de configuration de l’application FrontlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fa1bf-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="fa1bf-144">Rechercher des événements Shifts dans le journal d’audit</span><span class="sxs-lookup"><span data-stu-id="fa1bf-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="fa1bf-145">**(version d’évaluation)**</span><span class="sxs-lookup"><span data-stu-id="fa1bf-145">**(in preview)**</span></span>

<span data-ttu-id="fa1bf-146">Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité Shifts au niveau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="fa1bf-147">Pour en savoir plus sur la recherche dans le journal d’audit et la liste des activités [Shifts enregistrées](../../audit-log-events.md#shifts-in-teams-activities) dans le journal d’audit, consultez Rechercher des événements dans Teams dans le journal d’audit. [](../../audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="fa1bf-148">Avant d’effectuer des recherches dans le journal d’audit, vous devez activer l’audit dans le Centre [& conformité.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="fa1bf-149">Pour en savoir plus, voir Activer ou désactiver la recherche dans le [journal d’audit.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)</span><span class="sxs-lookup"><span data-stu-id="fa1bf-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="fa1bf-150">N’oubliez pas que les données d’audit sont uniquement disponibles à partir du moment où vous avez désactivé l’audit.</span><span class="sxs-lookup"><span data-stu-id="fa1bf-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa1bf-151">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="fa1bf-151">Related topics</span></span>

- [<span data-ttu-id="fa1bf-152">Aide shifts pour les employés en ligne en avant-première</span><span class="sxs-lookup"><span data-stu-id="fa1bf-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="fa1bf-153">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fa1bf-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
