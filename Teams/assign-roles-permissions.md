---
title: Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d5b3f52caf7de455d2b579a3360d17e18602450
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014290"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="f0885-103">Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0885-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f0885-104">Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et des **membres**.</span><span class="sxs-lookup"><span data-stu-id="f0885-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="f0885-105">Par défaut, un utilisateur qui crée une nouvelle équipe est accordé à l’état de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="f0885-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="f0885-106">Si une équipe est créée à partir d’un groupe de 365 Office existant, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="f0885-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="f0885-107">Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre :</span><span class="sxs-lookup"><span data-stu-id="f0885-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="f0885-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="f0885-108">Team Owner</span></span>  |<span data-ttu-id="f0885-109">Membre d'équipe</span><span class="sxs-lookup"><span data-stu-id="f0885-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f0885-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="f0885-110">**Create team**</span></span>     |<span data-ttu-id="f0885-111">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-111">Yes</span></span>        |<span data-ttu-id="f0885-112">Non</span><span class="sxs-lookup"><span data-stu-id="f0885-112">No</span></span>         |
|<span data-ttu-id="f0885-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="f0885-113">**Leave team**</span></span>     |<span data-ttu-id="f0885-114">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-114">Yes</span></span>         |<span data-ttu-id="f0885-115">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-115">Yes</span></span>         |
|<span data-ttu-id="f0885-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="f0885-116">**Edit team name/description**</span></span>      |<span data-ttu-id="f0885-117">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-117">Yes</span></span>         |<span data-ttu-id="f0885-118">Non</span><span class="sxs-lookup"><span data-stu-id="f0885-118">No</span></span>         |
|<span data-ttu-id="f0885-119">**Supprimer une équipe**</span><span class="sxs-lookup"><span data-stu-id="f0885-119">**Delete team**</span></span>      |<span data-ttu-id="f0885-120">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-120">Yes</span></span>         |<span data-ttu-id="f0885-121">Non</span><span class="sxs-lookup"><span data-stu-id="f0885-121">No</span></span>         |
|<span data-ttu-id="f0885-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="f0885-122">**Add channel**</span></span>      |<span data-ttu-id="f0885-123">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-123">Yes</span></span>         |<span data-ttu-id="f0885-124">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-124">Yes\*</span></span>         |
|<span data-ttu-id="f0885-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="f0885-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="f0885-126">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-126">Yes</span></span>         |<span data-ttu-id="f0885-127">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-127">Yes\*</span></span>         |
|<span data-ttu-id="f0885-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="f0885-128">**Delete channel**</span></span>      |<span data-ttu-id="f0885-129">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-129">Yes</span></span>         |<span data-ttu-id="f0885-130">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-130">Yes\*</span></span>         |
|<span data-ttu-id="f0885-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="f0885-131">**Add members**</span></span>      |<span data-ttu-id="f0885-132">Oui\*\*</span><span class="sxs-lookup"><span data-stu-id="f0885-132">Yes\*\*</span></span>         |<span data-ttu-id="f0885-133">Non</span><span class="sxs-lookup"><span data-stu-id="f0885-133">No</span></span>         |
|<span data-ttu-id="f0885-134">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="f0885-134">**Add tabs**</span></span>      |<span data-ttu-id="f0885-135">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-135">Yes</span></span>         |<span data-ttu-id="f0885-136">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-136">Yes\*</span></span>         |
|<span data-ttu-id="f0885-137">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="f0885-137">**Add connectors**</span></span>      |<span data-ttu-id="f0885-138">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-138">Yes</span></span>         |<span data-ttu-id="f0885-139">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-139">Yes\*</span></span>         |
|<span data-ttu-id="f0885-140">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="f0885-140">**Add bots**</span></span>      |<span data-ttu-id="f0885-141">Oui</span><span class="sxs-lookup"><span data-stu-id="f0885-141">Yes</span></span>         |<span data-ttu-id="f0885-142">Oui\*</span><span class="sxs-lookup"><span data-stu-id="f0885-142">Yes\*</span></span>         |
<span data-ttu-id="f0885-143">\*Ces éléments peuvent être désactivées par un propriétaire à un niveau équipe, dans ce cas membres auront pas accès à ces derniers.</span><span class="sxs-lookup"><span data-stu-id="f0885-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="f0885-p102">\*\*Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de Propriétaire. Il est également possible pour un propriétaire de rétrograder son propre statut à celui de membre.</span><span class="sxs-lookup"><span data-stu-id="f0885-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="f0885-146">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes.</span><span class="sxs-lookup"><span data-stu-id="f0885-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="f0885-147">Une équipe peut compter 100 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="f0885-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="f0885-148">Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation.</span><span class="sxs-lookup"><span data-stu-id="f0885-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="f0885-149">Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="f0885-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="f0885-150">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="f0885-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="f0885-151">Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe au sein de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0885-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="f0885-152">Vous pouvez contrôler plus étroitement et restreindre la création de nouvelles équipes ainsi que la création de nouveaux groupes d’Office 365 en déléguant la création d’un groupe et les droits de gestion pour un ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f0885-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="f0885-153">Pour plus d’informations, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="f0885-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="f0885-155">Point de décision</span><span class="sxs-lookup"><span data-stu-id="f0885-155">Decision Point</span></span>         |<span data-ttu-id="f0885-156">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="f0885-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="f0885-158">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f0885-158">Next Steps</span></span>         |<span data-ttu-id="f0885-159">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="f0885-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
