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
ms.openlocfilehash: 67685fc79f2d2cd1f3ef9f76f6802f73119be43a
ms.sourcegitcommit: be8b6383261358e91dcb79bf819502b8b7ac6526
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/19/2018
ms.locfileid: "26618544"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="621bd-103">Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="621bd-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="621bd-104">Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et des **membres**.</span><span class="sxs-lookup"><span data-stu-id="621bd-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="621bd-105">Par défaut, un utilisateur qui crée une nouvelle équipe est accordé à l’état de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="621bd-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="621bd-106">Si une équipe est créée à partir d’un groupe de 365 Office existant, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="621bd-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="621bd-107">Le tableau ci-dessous indique les différences dans les autorisations d’un propriétaire et un membre.</span><span class="sxs-lookup"><span data-stu-id="621bd-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="621bd-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="621bd-108">Team Owner</span></span> | <span data-ttu-id="621bd-109">Membre d'équipe</span><span class="sxs-lookup"><span data-stu-id="621bd-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="621bd-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="621bd-110">**Create team**</span></span>          |    <span data-ttu-id="621bd-111">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="621bd-112">Non</span><span class="sxs-lookup"><span data-stu-id="621bd-112">No</span></span>      |
|          <span data-ttu-id="621bd-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="621bd-113">**Leave team**</span></span>           |    <span data-ttu-id="621bd-114">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-114">Yes</span></span>     |     <span data-ttu-id="621bd-115">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-115">Yes</span></span>     |
|  <span data-ttu-id="621bd-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="621bd-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="621bd-117">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-117">Yes</span></span>     |     <span data-ttu-id="621bd-118">Non</span><span class="sxs-lookup"><span data-stu-id="621bd-118">No</span></span>      |
|          <span data-ttu-id="621bd-119">**Supprimer une équipe**</span><span class="sxs-lookup"><span data-stu-id="621bd-119">**Delete team**</span></span>          |    <span data-ttu-id="621bd-120">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-120">Yes</span></span>     |     <span data-ttu-id="621bd-121">Non</span><span class="sxs-lookup"><span data-stu-id="621bd-121">No</span></span>      |
|          <span data-ttu-id="621bd-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="621bd-122">**Add channel**</span></span>          |    <span data-ttu-id="621bd-123">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-123">Yes</span></span>     |    <span data-ttu-id="621bd-124">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="621bd-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="621bd-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="621bd-126">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-126">Yes</span></span>     |    <span data-ttu-id="621bd-127">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="621bd-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="621bd-128">**Delete channel**</span></span>         |    <span data-ttu-id="621bd-129">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-129">Yes</span></span>     |    <span data-ttu-id="621bd-130">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="621bd-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="621bd-131">**Add members**</span></span>          |  <span data-ttu-id="621bd-132">Oui<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="621bd-133">Non</span><span class="sxs-lookup"><span data-stu-id="621bd-133">No</span></span>      |
|           <span data-ttu-id="621bd-134">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="621bd-134">**Add tabs**</span></span>            |    <span data-ttu-id="621bd-135">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-135">Yes</span></span>     |    <span data-ttu-id="621bd-136">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-136">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="621bd-137">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="621bd-137">**Add connectors**</span></span>         |    <span data-ttu-id="621bd-138">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-138">Yes</span></span>     |    <span data-ttu-id="621bd-139">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-139">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="621bd-140">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="621bd-140">**Add bots**</span></span>            |    <span data-ttu-id="621bd-141">Oui</span><span class="sxs-lookup"><span data-stu-id="621bd-141">Yes</span></span>     |    <span data-ttu-id="621bd-142">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="621bd-142">Yes<sup>2</sup></span></span>|

<span data-ttu-id="621bd-143"><sup>1</sup> les propriétaires de l’équipe peuvent créer des équipes, sauf si elles avoir été restreint de le faire.</span><span class="sxs-lookup"><span data-stu-id="621bd-143"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="621bd-144">Consultez « Autorisations pour créer des équipes » ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="621bd-144">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="621bd-145"><sup>2</sup> ces éléments peuvent être désactivées par un propriétaire à un niveau équipe, auquel cas membres auront pas accès à ces derniers.</span><span class="sxs-lookup"><span data-stu-id="621bd-145"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="621bd-146"><sup>3</sup> après l’ajout d’un membre à une équipe, un propriétaire peut également désigner un membre à l’état de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="621bd-146"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="621bd-147">Il est également possible, pour un propriétaire à rétrograder le statut de leur propres à un membre.</span><span class="sxs-lookup"><span data-stu-id="621bd-147">It is also possible for an owner to demote their own status to a member.</span></span>



> [!NOTE]
> <span data-ttu-id="621bd-148">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes.</span><span class="sxs-lookup"><span data-stu-id="621bd-148">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="621bd-149">Une équipe peut compter 100 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="621bd-149">A team can have up to 100 owners.</span></span> <span data-ttu-id="621bd-150">Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation.</span><span class="sxs-lookup"><span data-stu-id="621bd-150">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="621bd-151">Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="621bd-151">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="621bd-152">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="621bd-152">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="621bd-153">Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe au sein de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="621bd-153">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="621bd-154">Vous pouvez contrôler plus étroitement et restreindre la création de nouvelles équipes ainsi que la création de nouveaux groupes d’Office 365 en déléguant la création d’un groupe et les droits de gestion pour un ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="621bd-154">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="621bd-155">Pour plus d’informations, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="621bd-155">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="621bd-157">Point de décision</span><span class="sxs-lookup"><span data-stu-id="621bd-157">Decision Point</span></span>         |<span data-ttu-id="621bd-158">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="621bd-158">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="621bd-160">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="621bd-160">Next Steps</span></span>         |<span data-ttu-id="621bd-161">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="621bd-161">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
