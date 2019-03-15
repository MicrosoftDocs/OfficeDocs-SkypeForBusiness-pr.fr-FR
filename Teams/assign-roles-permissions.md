---
title: Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569957"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="864b9-103">Affecter des propriétaires d’équipe et des membres dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="864b9-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="864b9-104">Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et des **membres**.</span><span class="sxs-lookup"><span data-stu-id="864b9-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="864b9-105">Par défaut, un utilisateur qui crée une nouvelle équipe est accordé à l’état de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="864b9-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="864b9-106">Si une équipe est créée à partir d’un groupe de 365 Office existant, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="864b9-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="864b9-107">Le tableau ci-dessous indique les différences dans les autorisations d’un propriétaire et un membre.</span><span class="sxs-lookup"><span data-stu-id="864b9-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="864b9-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="864b9-108">Team Owner</span></span> | <span data-ttu-id="864b9-109">Membre d'équipe</span><span class="sxs-lookup"><span data-stu-id="864b9-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="864b9-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="864b9-110">**Create team**</span></span>          |    <span data-ttu-id="864b9-111">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="864b9-112">Non</span><span class="sxs-lookup"><span data-stu-id="864b9-112">No</span></span>      |
|          <span data-ttu-id="864b9-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="864b9-113">**Leave team**</span></span>           |    <span data-ttu-id="864b9-114">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-114">Yes</span></span>     |     <span data-ttu-id="864b9-115">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-115">Yes</span></span>     |
|  <span data-ttu-id="864b9-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="864b9-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="864b9-117">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-117">Yes</span></span>     |     <span data-ttu-id="864b9-118">Non</span><span class="sxs-lookup"><span data-stu-id="864b9-118">No</span></span>      |
|          <span data-ttu-id="864b9-119">**Supprimer une équipe**</span><span class="sxs-lookup"><span data-stu-id="864b9-119">**Delete team**</span></span>          |    <span data-ttu-id="864b9-120">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-120">Yes</span></span>     |     <span data-ttu-id="864b9-121">Non</span><span class="sxs-lookup"><span data-stu-id="864b9-121">No</span></span>      |
|          <span data-ttu-id="864b9-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="864b9-122">**Add channel**</span></span>          |    <span data-ttu-id="864b9-123">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-123">Yes</span></span>     |    <span data-ttu-id="864b9-124">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="864b9-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="864b9-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="864b9-126">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-126">Yes</span></span>     |    <span data-ttu-id="864b9-127">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="864b9-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="864b9-128">**Delete channel**</span></span>         |    <span data-ttu-id="864b9-129">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-129">Yes</span></span>     |    <span data-ttu-id="864b9-130">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="864b9-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="864b9-131">**Add members**</span></span>          |  <span data-ttu-id="864b9-132">Oui<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="864b9-133">Aucun<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="864b9-134">**Demande d’ajout de membres**</span><span class="sxs-lookup"><span data-stu-id="864b9-134">**Request to add members**</span></span>          |  <span data-ttu-id="864b9-135">N/A</span><span class="sxs-lookup"><span data-stu-id="864b9-135">N/A</span></span>   |     <span data-ttu-id="864b9-136">Oui<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="864b9-137">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="864b9-137">**Add tabs**</span></span>            |    <span data-ttu-id="864b9-138">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-138">Yes</span></span>     |    <span data-ttu-id="864b9-139">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="864b9-140">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="864b9-140">**Add connectors**</span></span>         |    <span data-ttu-id="864b9-141">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-141">Yes</span></span>     |    <span data-ttu-id="864b9-142">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="864b9-143">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="864b9-143">**Add bots**</span></span>            |    <span data-ttu-id="864b9-144">Oui</span><span class="sxs-lookup"><span data-stu-id="864b9-144">Yes</span></span>     |    <span data-ttu-id="864b9-145">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="864b9-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="864b9-146"><sup>1</sup> les propriétaires de l’équipe peuvent créer des équipes, sauf si elles avoir été restreint de le faire.</span><span class="sxs-lookup"><span data-stu-id="864b9-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="864b9-147">Consultez « Autorisations pour créer des équipes » ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="864b9-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="864b9-148"><sup>2</sup> ces éléments peuvent être désactivées par un propriétaire à un niveau équipe, auquel cas membres auront pas accès à ces derniers.</span><span class="sxs-lookup"><span data-stu-id="864b9-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="864b9-149"><sup>3</sup> après l’ajout d’un membre à une équipe, un propriétaire peut également désigner un membre à l’état de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="864b9-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="864b9-150">Il est également possible, pour un propriétaire à rétrograder le statut de leur propres à un membre.</span><span class="sxs-lookup"><span data-stu-id="864b9-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="864b9-151"><sup>4</sup> membres de l’équipe peuvent ajouter d’autres membres à une équipe publique.</span><span class="sxs-lookup"><span data-stu-id="864b9-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="864b9-152"><sup>5</sup> pendant un membre d’équipe ne peut pas ajouter directement des membres à une équipe privée, ils peuvent demander une personne à ajouter à une équipe, ils sont déjà membre.</span><span class="sxs-lookup"><span data-stu-id="864b9-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="864b9-153">Lorsqu’un membre demande une personne à ajouter à une équipe, les propriétaires de l’équipe reçoivent une alerte qu’ils possèdent une demande en attente qu’elles peuvent accepter ou refuser.</span><span class="sxs-lookup"><span data-stu-id="864b9-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="864b9-154">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes.</span><span class="sxs-lookup"><span data-stu-id="864b9-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="864b9-155">Une équipe peut compter 100 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="864b9-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="864b9-156">Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation.</span><span class="sxs-lookup"><span data-stu-id="864b9-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="864b9-157">Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="864b9-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="864b9-158">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="864b9-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="864b9-159">Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe au sein de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="864b9-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="864b9-160">Vous pouvez contrôler plus étroitement et restreindre la création de nouvelles équipes ainsi que la création de nouveaux groupes d’Office 365 en déléguant la création d’un groupe et les droits de gestion pour un ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="864b9-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="864b9-161">Pour plus d’informations, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="864b9-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="864b9-163">Point de décision</span><span class="sxs-lookup"><span data-stu-id="864b9-163">Decision Point</span></span>         |<span data-ttu-id="864b9-164">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="864b9-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="864b9-166">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="864b9-166">Next Steps</span></span>         |<span data-ttu-id="864b9-167">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="864b9-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
