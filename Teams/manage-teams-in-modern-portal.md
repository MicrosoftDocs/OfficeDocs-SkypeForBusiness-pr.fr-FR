---
title: Gérer les équipes dans le centre Microsoft Teams’administration
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Découvrez comment afficher ou mettre à jour les équipes que votre organisation a définies pour la collaboration dans le Microsoft Teams d’administration.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237540"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="da6e0-103">Gérer les équipes dans le centre Microsoft Teams’administration</span><span class="sxs-lookup"><span data-stu-id="da6e0-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="da6e0-104">Présentation</span><span class="sxs-lookup"><span data-stu-id="da6e0-104">Overview</span></span>

<span data-ttu-id="da6e0-105">Cet article fournit une vue d’ensemble des outils de gestion Teams dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="da6e0-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="da6e0-106">En tant qu’administrateur, vous devrez peut-être afficher ou mettre à jour les équipes que votre organisation a définies pour la collaboration, ou vous devrez peut-être effectuer des actions de correction, telles que l’attribution de propriétaires à des équipes sans propriétaire.</span><span class="sxs-lookup"><span data-stu-id="da6e0-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="da6e0-107">Vous pouvez gérer les équipes utilisées dans votre organisation à la fois via le module Microsoft Teams PowerShell et le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="da6e0-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="da6e0-108">Vous pouvez accéder au Centre d’administration à <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> l’adresse .</span><span class="sxs-lookup"><span data-stu-id="da6e0-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="da6e0-109">Pour des fonctionnalités d’administration complètes utilisant ces deux jeux d’outils, vous devez vous assurer qu’un des rôles suivants vous est attribué :</span><span class="sxs-lookup"><span data-stu-id="da6e0-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="da6e0-110">Administrateur général</span><span class="sxs-lookup"><span data-stu-id="da6e0-110">Global Administrator</span></span>
- <span data-ttu-id="da6e0-111">Teams Administrateur</span><span class="sxs-lookup"><span data-stu-id="da6e0-111">Teams Administrator</span></span>

<span data-ttu-id="da6e0-112">Vous pouvez en savoir plus sur les rôles d’administrateur dans Teams dans Utiliser les rôles d’administrateur Microsoft Teams pour gérer [des Teams,](using-admin-roles.md)et en savoir plus sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la référence de l’cmdlet [Microsoft Teams.](/powershell/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="da6e0-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="da6e0-113">Teams de vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="da6e0-113">Teams overview grid</span></span>

<span data-ttu-id="da6e0-114">Les outils de gestion pour les équipes se **Teams** le nœud de gestion dans Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="da6e0-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="da6e0-115">(Dans le Centre d’administration, **sélectionnez Teams**  >  **Gérer les équipes**.) Chaque équipe est backed by a Microsoft 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span><span class="sxs-lookup"><span data-stu-id="da6e0-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Capture d’écran de la Teams vue d’ensemble](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="da6e0-117">La grille affiche les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="da6e0-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="da6e0-118">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="da6e0-118">**Team name**</span></span>
- <span data-ttu-id="da6e0-119">**Canaux** : un nombre de canaux dans l’équipe, y compris le canal Général par défaut.</span><span class="sxs-lookup"><span data-stu-id="da6e0-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="da6e0-120">**Membres d’une** équipe : un nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="da6e0-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="da6e0-121">**Propriétaires** : un nombre de propriétaires pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="da6e0-122">**Invités** : nombre d’Azure Active Directory invités B2B qui sont membres de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="da6e0-123">**Confidentialité** - Visibilité/Type d’accès du groupe Microsoft 365 de sécurité.</span><span class="sxs-lookup"><span data-stu-id="da6e0-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="da6e0-124">**État** : état Archivé ou Actif pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="da6e0-125">En savoir plus sur l’archivage des équipes [dans Archiver ou restaurer une équipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="da6e0-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="da6e0-126">**Description** : description du groupe de Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="da6e0-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="da6e0-127">**Classification** : classification (si elle est utilisée dans votre organisation) assignée au groupe Microsoft 365 personnel.</span><span class="sxs-lookup"><span data-stu-id="da6e0-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="da6e0-128">Pour plus d’informations sur les [classifications, Office classifications pour les groupes de votre organisation.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="da6e0-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="da6e0-129">**GroupID** - GroupID unique du groupe de Microsoft 365 groupe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="da6e0-130">Si vous ne voyez pas toutes ces propriétés dans la grille, cliquez sur **l’icône Modifier les colonnes.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="da6e0-131">Dans le **volet Modifier les** colonnes, vous pouvez utiliser les boutons bascule pour activer ou désactiver les colonnes dans la grille.</span><span class="sxs-lookup"><span data-stu-id="da6e0-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="da6e0-132">Lorsque vous avez terminé, cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="da6e0-133">Ajouter</span><span class="sxs-lookup"><span data-stu-id="da6e0-133">Add</span></span>

<span data-ttu-id="da6e0-134">Pour ajouter une équipe, cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="da6e0-135">Dans le **volet Ajouter** une nouvelle équipe, donnez un nom et une description à l’équipe, définissez si vous souhaitez en faire une équipe privée ou publique et définissez la classification.</span><span class="sxs-lookup"><span data-stu-id="da6e0-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="da6e0-136">Les équipes nouvellement créées peuvent être gérées immédiatement dans le Teams d’administration, contrairement à l’expérience d’autres clients tels que Outlook.</span><span class="sxs-lookup"><span data-stu-id="da6e0-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="da6e0-137">Modifier</span><span class="sxs-lookup"><span data-stu-id="da6e0-137">Edit</span></span>

<span data-ttu-id="da6e0-138">Pour modifier les paramètres des groupes et des équipes, sélectionnez l’équipe en cliquant à gauche du nom de l’équipe, puis sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="da6e0-139">Archivage</span><span class="sxs-lookup"><span data-stu-id="da6e0-139">Archive</span></span>

<span data-ttu-id="da6e0-140">Vous pouvez archiver une équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-140">You can archive a team.</span></span> <span data-ttu-id="da6e0-141">L’archivage d’une équipe place l’équipe en mode lecture seule dans Teams.</span><span class="sxs-lookup"><span data-stu-id="da6e0-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="da6e0-142">En tant qu’administrateur, vous pouvez archiver et dés archiver des équipes pour le compte de votre organisation dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="da6e0-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="da6e0-143">Supprimer</span><span class="sxs-lookup"><span data-stu-id="da6e0-143">Delete</span></span>

<span data-ttu-id="da6e0-144">La suppression d’une équipe est une suppression (suppression soft) de l’équipe et de la Microsoft 365 groupe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="da6e0-145">Pour restaurer une équipe supprimée par erreur, suivez les instructions dans [Restaurer un groupe supprimé.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="da6e0-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="da6e0-146">Rechercher</span><span class="sxs-lookup"><span data-stu-id="da6e0-146">Search</span></span>

<span data-ttu-id="da6e0-147">La recherche prend actuellement en charge la chaîne « Commence par » et recherche dans le champ Nom de **l’équipe.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="da6e0-148">Profil d’équipe</span><span class="sxs-lookup"><span data-stu-id="da6e0-148">Team profile</span></span>

<span data-ttu-id="da6e0-149">Vous pouvez accéder à la page de profil d’une équipe à partir de la grille de vue d’ensemble principale des équipes en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="da6e0-150">La page de profil d’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et son groupe Microsoft 365), ainsi que les canaux et paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="da6e0-151">Dans la page de profil de l’équipe, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="da6e0-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="da6e0-152">Ajoutez ou supprimez des membres et des propriétaires.</span><span class="sxs-lookup"><span data-stu-id="da6e0-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="da6e0-153">Ajouter ou supprimer des canaux (notez que vous ne pouvez pas supprimer le canal Général).</span><span class="sxs-lookup"><span data-stu-id="da6e0-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="da6e0-154">Modifiez les paramètres des équipes et des groupes.</span><span class="sxs-lookup"><span data-stu-id="da6e0-154">Change team and group settings.</span></span>
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="da6e0-156">Apporter des modifications aux équipes</span><span class="sxs-lookup"><span data-stu-id="da6e0-156">Making changes to teams</span></span>

<span data-ttu-id="da6e0-157">Dans la page de profil de l’équipe, vous pouvez modifier les éléments suivants d’une équipe :</span><span class="sxs-lookup"><span data-stu-id="da6e0-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="da6e0-158">**Membres :** ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires.</span><span class="sxs-lookup"><span data-stu-id="da6e0-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="da6e0-159">**Canaux** : ajoutez de nouveaux canaux et modifiez ou supprimez des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="da6e0-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="da6e0-160">N’oubliez pas que vous ne pouvez pas supprimer le canal Général par défaut.</span><span class="sxs-lookup"><span data-stu-id="da6e0-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="da6e0-161">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="da6e0-161">**Team name**</span></span>
- <span data-ttu-id="da6e0-162">**Description**</span><span class="sxs-lookup"><span data-stu-id="da6e0-162">**Description**</span></span>
- <span data-ttu-id="da6e0-163">**Confidentialité** : définir si l’équipe est publique ou privée.</span><span class="sxs-lookup"><span data-stu-id="da6e0-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="da6e0-164">**Classification** : cette classification est backed by your Microsoft 365 group classifications.</span><span class="sxs-lookup"><span data-stu-id="da6e0-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="da6e0-165">Sélectionnez **Confidentiel,** **Hautement confidentiel** ou **Général.**</span><span class="sxs-lookup"><span data-stu-id="da6e0-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="da6e0-166">**Paramètres des conversations** : définir si les membres peuvent modifier et supprimer les messages envoyés.</span><span class="sxs-lookup"><span data-stu-id="da6e0-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="da6e0-167">**Paramètres des canaux** : définir si les membres peuvent créer et modifier des canaux existants, et ajouter, modifier et supprimer des onglets, des connecteurs et des applications.</span><span class="sxs-lookup"><span data-stu-id="da6e0-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="da6e0-168">Les modifications que vous a apportées à une équipe sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="da6e0-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="da6e0-169">Si vous modifiez les paramètres du groupe (modification du nom, de la description, de la photo, de la confidentialité, de la classification ou des membres d’une équipe), les modifications vous sont attribuées via le pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="da6e0-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="da6e0-170">Si vous effectuez des actions par rapport Teams paramètres spécifiques, vos modifications sont suivis et vous sont attribuées dans le canal Général de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="da6e0-171">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="da6e0-171">Troubleshooting</span></span>

<span data-ttu-id="da6e0-172">**Problème : Teams manquants dans la grille de vue d’ensemble de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="da6e0-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="da6e0-173">Certaines de vos équipes sont manquantes dans la liste des équipes dans la Teams de vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="da6e0-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="da6e0-174">**Cause**: ce problème se produit lorsque l’équipe a été profilée de façon incorrecte (ou pas encore) par le système, ce qui peut entraîner une propriété manquante pour qu’elle soit reconnue.</span><span class="sxs-lookup"><span data-stu-id="da6e0-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="da6e0-175">**Résolution : définir manuellement la propriété sur la valeur correcte via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="da6e0-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="da6e0-176">Remplacez **{groupid}** dans la requête pour le GroupId réel en question, que vous pouvez obtenir via la Exchange Online powershell, par l’attribut « **[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** comme attribut **« ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="da6e0-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="da6e0-177">Accédez [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="da6e0-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="da6e0-178">Connectez-vous Graph’Explorateur dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="da6e0-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="da6e0-179">Modifiez la ligne de requête en : PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.</span><span class="sxs-lookup"><span data-stu-id="da6e0-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="da6e0-180">Ajoutez la valeur suivante dans le corps de la demande : {"resourceProvisioningOptions »: ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="da6e0-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="da6e0-181">Exécutez la requête en haut à droite.</span><span class="sxs-lookup"><span data-stu-id="da6e0-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="da6e0-182">Confirmez que l’équipe s’affiche correctement dans le Microsoft Teams d’administration - Vue d’ensemble de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="da6e0-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="da6e0-183">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="da6e0-183">Learn more</span></span>

- [<span data-ttu-id="da6e0-184">Teams des cmdlet</span><span class="sxs-lookup"><span data-stu-id="da6e0-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="da6e0-185">Utiliser Teams rôles d’administrateur pour gérer les Teams</span><span class="sxs-lookup"><span data-stu-id="da6e0-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="da6e0-186">Planifier la gestion du cycle de vie dans Teams</span><span class="sxs-lookup"><span data-stu-id="da6e0-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)