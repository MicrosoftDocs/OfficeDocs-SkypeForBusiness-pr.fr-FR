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
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493801"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="480d7-103">Affecter des propriétaires d’équipe et des membres dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="480d7-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="480d7-p101">Microsoft Teams inclut deux rôles : **Propriétaire** et **Membre**. Par défaut, un utilisateur qui crée une équipe a le statut de Propriétaire. Si une équipe est créée à partir d'un groupe existant Office 365, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="480d7-p101">Within Microsoft Teams there are two user roles: **Owner** and **Member**. By default, a user who creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="480d7-107">Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre.</span><span class="sxs-lookup"><span data-stu-id="480d7-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="480d7-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="480d7-108">Team Owner</span></span> | <span data-ttu-id="480d7-109">Membre de l’équipe</span><span class="sxs-lookup"><span data-stu-id="480d7-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="480d7-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="480d7-110">**Create team**</span></span>          |    <span data-ttu-id="480d7-111">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="480d7-112">Non</span><span class="sxs-lookup"><span data-stu-id="480d7-112">No</span></span>      |
|          <span data-ttu-id="480d7-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="480d7-113">**Leave team**</span></span>           |    <span data-ttu-id="480d7-114">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-114">Yes</span></span>     |     <span data-ttu-id="480d7-115">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-115">Yes</span></span>     |
|  <span data-ttu-id="480d7-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="480d7-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="480d7-117">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-117">Yes</span></span>     |     <span data-ttu-id="480d7-118">Non</span><span class="sxs-lookup"><span data-stu-id="480d7-118">No</span></span>      |
|          <span data-ttu-id="480d7-119">**Supprimer l’équipe**</span><span class="sxs-lookup"><span data-stu-id="480d7-119">**Delete team**</span></span>          |    <span data-ttu-id="480d7-120">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-120">Yes</span></span>     |     <span data-ttu-id="480d7-121">Non</span><span class="sxs-lookup"><span data-stu-id="480d7-121">No</span></span>      |
|          <span data-ttu-id="480d7-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="480d7-122">**Add channel**</span></span>          |    <span data-ttu-id="480d7-123">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-123">Yes</span></span>     |    <span data-ttu-id="480d7-124">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="480d7-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="480d7-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="480d7-126">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-126">Yes</span></span>     |    <span data-ttu-id="480d7-127">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="480d7-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="480d7-128">**Delete channel**</span></span>         |    <span data-ttu-id="480d7-129">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-129">Yes</span></span>     |    <span data-ttu-id="480d7-130">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="480d7-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="480d7-131">**Add members**</span></span>          |  <span data-ttu-id="480d7-132">Oui<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="480d7-133">Non<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="480d7-134">**Demande d’ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="480d7-134">**Request to add members**</span></span>          |  <span data-ttu-id="480d7-135">S/O</span><span class="sxs-lookup"><span data-stu-id="480d7-135">N/A</span></span>   |     <span data-ttu-id="480d7-136">Oui<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="480d7-137">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="480d7-137">**Add tabs**</span></span>            |    <span data-ttu-id="480d7-138">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-138">Yes</span></span>     |    <span data-ttu-id="480d7-139">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="480d7-140">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="480d7-140">**Add connectors**</span></span>         |    <span data-ttu-id="480d7-141">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-141">Yes</span></span>     |    <span data-ttu-id="480d7-142">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="480d7-143">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="480d7-143">**Add bots**</span></span>            |    <span data-ttu-id="480d7-144">Oui</span><span class="sxs-lookup"><span data-stu-id="480d7-144">Yes</span></span>     |    <span data-ttu-id="480d7-145">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="480d7-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="480d7-146"><sup>1</sup> les propriétaires des équipes peuvent créer des équipes, sauf s’ils sont restreints.</span><span class="sxs-lookup"><span data-stu-id="480d7-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="480d7-147">Voir « Autorisations nécessaires pour créer des équipes » ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="480d7-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="480d7-148"><sup>2</sup> Ces éléments peuvent être désactivés par un propriétaire au niveau d'une équipe, auquel cas les membres n'y auront pas accès.</span><span class="sxs-lookup"><span data-stu-id="480d7-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="480d7-149"><sup>3</sup> après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="480d7-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="480d7-150">Il est également possible pour un propriétaire d’abaisser leur propre état pour un membre.</span><span class="sxs-lookup"><span data-stu-id="480d7-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="480d7-151"><sup>4</sup> les membres de Teams peuvent ajouter d’autres membres à une équipe publique.</span><span class="sxs-lookup"><span data-stu-id="480d7-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="480d7-152"><sup>5</sup> un membre d’équipe ne peut pas ajouter directement des membres à une équipe privée, ils peuvent demander qu’une personne soit ajoutée à une équipe dont ils sont déjà membres.</span><span class="sxs-lookup"><span data-stu-id="480d7-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="480d7-153">Lorsqu’un membre demande l’ajout d»une personne à une équipe, les propriétaires des équipes reçoivent une alerte de demande en attente qu’ils peuvent accepter ou refuser.</span><span class="sxs-lookup"><span data-stu-id="480d7-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="480d7-154">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes.</span><span class="sxs-lookup"><span data-stu-id="480d7-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="480d7-155">Une équipe peut compter 100 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="480d7-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="480d7-156">Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation.</span><span class="sxs-lookup"><span data-stu-id="480d7-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="480d7-157">Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="480d7-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="480d7-158">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="480d7-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="480d7-159">Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes Office 365 et par conséquent une équipe dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="480d7-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="480d7-160">Vous pouvez avoir un contrôle plus étroit et limiter la création d’équipes et par conséquent la création de nouveaux groupes Office 365 en déléguant la gestion des droits et la création de groupes à un ensemble d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="480d7-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="480d7-161">Pour plus d'informations, reportez-vous à l’article[Gérer qui peut créer des Groupes Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="480d7-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Icône représentant un point de décision](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="480d7-163">Point de décision</span><span class="sxs-lookup"><span data-stu-id="480d7-163">Decision Point</span></span>         |<span data-ttu-id="480d7-164">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="480d7-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône représentant les étapes suivantes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="480d7-166">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="480d7-166">Next Steps</span></span>         |<span data-ttu-id="480d7-167">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="480d7-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
