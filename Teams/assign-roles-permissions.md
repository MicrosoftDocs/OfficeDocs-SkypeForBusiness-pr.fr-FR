---
title: Assigner des rôles et des autorisations dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b6dfc74b3d7dc740cc970f711f32fac1d75e2d5
ms.sourcegitcommit: c18710a46018fe4c1d0ceb99710f18bbc25aad54
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2018
ms.locfileid: "19441660"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="d27d0-103">Assigner des rôles et des autorisations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d27d0-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d27d0-p101">Microsoft Teams inclut deux rôles : **Propriétaire** et **Membre**. Par défaut, un utilisateur qui crée une équipe a le statut de Propriétaire. Si une équipe est créée à partir d'un groupe existant Office 365, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="d27d0-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="d27d0-107">Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre :</span><span class="sxs-lookup"><span data-stu-id="d27d0-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="d27d0-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="d27d0-108">Team Owner</span></span>  |<span data-ttu-id="d27d0-109">Membre d'équipe</span><span class="sxs-lookup"><span data-stu-id="d27d0-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d27d0-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="d27d0-110">**Create team**</span></span>     |<span data-ttu-id="d27d0-111">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-111">Yes</span></span>        |<span data-ttu-id="d27d0-112">Non</span><span class="sxs-lookup"><span data-stu-id="d27d0-112">No</span></span>         |
|<span data-ttu-id="d27d0-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="d27d0-113">**Leave team**</span></span>     |<span data-ttu-id="d27d0-114">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-114">Yes</span></span>         |<span data-ttu-id="d27d0-115">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-115">Yes</span></span>         |
|<span data-ttu-id="d27d0-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="d27d0-116">**Edit team name/description**</span></span>      |<span data-ttu-id="d27d0-117">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-117">Yes</span></span>         |<span data-ttu-id="d27d0-118">Non</span><span class="sxs-lookup"><span data-stu-id="d27d0-118">No</span></span>         |
|<span data-ttu-id="d27d0-119">**Supprimer une équipe**</span><span class="sxs-lookup"><span data-stu-id="d27d0-119">**Delete team**</span></span>      |<span data-ttu-id="d27d0-120">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-120">Yes</span></span>         |<span data-ttu-id="d27d0-121">Non</span><span class="sxs-lookup"><span data-stu-id="d27d0-121">No</span></span>         |
|<span data-ttu-id="d27d0-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="d27d0-122">**Add channel**</span></span>      |<span data-ttu-id="d27d0-123">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-123">Yes</span></span>         |<span data-ttu-id="d27d0-124">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-124">Yes\*</span></span>         |
|<span data-ttu-id="d27d0-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="d27d0-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="d27d0-126">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-126">Yes</span></span>         |<span data-ttu-id="d27d0-127">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-127">Yes\*</span></span>         |
|<span data-ttu-id="d27d0-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="d27d0-128">**Delete channel**</span></span>      |<span data-ttu-id="d27d0-129">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-129">Yes</span></span>         |<span data-ttu-id="d27d0-130">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-130">Yes\*</span></span>         |
|<span data-ttu-id="d27d0-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="d27d0-131">**Add members**</span></span>      |<span data-ttu-id="d27d0-132">Oui**</span><span class="sxs-lookup"><span data-stu-id="d27d0-132">Yes**</span></span>         |<span data-ttu-id="d27d0-133">Non</span><span class="sxs-lookup"><span data-stu-id="d27d0-133">No</span></span>         |
|<span data-ttu-id="d27d0-134">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="d27d0-134">**Add tabs**</span></span>      |<span data-ttu-id="d27d0-135">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-135">Yes</span></span>         |<span data-ttu-id="d27d0-136">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-136">Yes\*</span></span>         |
|<span data-ttu-id="d27d0-137">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="d27d0-137">**Add connectors**</span></span>      |<span data-ttu-id="d27d0-138">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-138">Yes</span></span>         |<span data-ttu-id="d27d0-139">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-139">Yes\*</span></span>         |
|<span data-ttu-id="d27d0-140">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="d27d0-140">**Add bots**</span></span>      |<span data-ttu-id="d27d0-141">Oui</span><span class="sxs-lookup"><span data-stu-id="d27d0-141">Yes</span></span>         |<span data-ttu-id="d27d0-142">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d27d0-142">Yes\*</span></span>         |
<span data-ttu-id="d27d0-143">\* Ces éléments peuvent être désactivés par un propriétaire au niveau d'une équipe, auquel cas les membres n'y auront pas accès.</span><span class="sxs-lookup"><span data-stu-id="d27d0-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="d27d0-p102">\*\*Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de Propriétaire. Il est également possible pour un propriétaire de rétrograder son propre statut à celui de membre.</span><span class="sxs-lookup"><span data-stu-id="d27d0-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="d27d0-146">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes.</span><span class="sxs-lookup"><span data-stu-id="d27d0-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="d27d0-147">Une équipe peut compter 100 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="d27d0-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="d27d0-148">Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation.</span><span class="sxs-lookup"><span data-stu-id="d27d0-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="d27d0-149">Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="d27d0-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="d27d0-150">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="d27d0-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="d27d0-151">Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe au sein de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d27d0-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="d27d0-152">Vous pouvez contrôler plus étroitement et restreindre la création de nouvelles équipes ainsi que la création de nouveaux groupes d’Office 365 en déléguant la création d’un groupe et les droits de gestion pour un ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d27d0-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="d27d0-153">Pour plus d’informations, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/en-us/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="d27d0-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/en-us/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="d27d0-155">Point de décision</span><span class="sxs-lookup"><span data-stu-id="d27d0-155">Decision Point</span></span>         |<span data-ttu-id="d27d0-156">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="d27d0-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="d27d0-158">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d27d0-158">Next Steps</span></span>         |<span data-ttu-id="d27d0-159">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="d27d0-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
