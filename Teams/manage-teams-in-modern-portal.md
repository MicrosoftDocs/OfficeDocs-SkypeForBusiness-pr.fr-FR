---
title: Gérer teams dans le centre d’administration Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Découvrez comment afficher ou mettre à jour vos équipes dans le centre d’administration Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fea7081ee66cbd7b103f4292f577aaf5d841e11
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37571933"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ceae0-103">Gérer teams dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ceae0-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="ceae0-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ceae0-104">Overview</span></span>

<span data-ttu-id="ceae0-105">En tant qu’administrateur, il est possible que vous deviez afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration, ou vous devrez peut-être effectuer des actions de correction, comme affecter des propriétaires à des équipes propriétaires.</span><span class="sxs-lookup"><span data-stu-id="ceae0-105">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="ceae0-106">Vous pouvez gérer les équipes utilisées dans votre organisation via le module Microsoft teams PowerShell et le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae0-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="ceae0-107">Pour pouvoir bénéficier d’une administration complète de ces deux ensembles d’outils, assurez-vous que vous disposez de l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="ceae0-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="ceae0-108">Administrateur général</span><span class="sxs-lookup"><span data-stu-id="ceae0-108">Global Administrator</span></span>
- <span data-ttu-id="ceae0-109">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="ceae0-109">Teams Service Administrator</span></span>

<span data-ttu-id="ceae0-110">Pour en savoir plus sur les rôles d’administrateur dans équipes, [Utilisez les rôles d’administrateur de Microsoft teams pour gérer teams](using-admin-roles.md), et apprenez-en davantage sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la [référence des cmdlets de Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ceae0-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>

<span data-ttu-id="ceae0-111">Cet article fournit une vue d’ensemble des outils de gestion pour teams dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae0-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="ceae0-112">Grille de vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="ceae0-112">Teams overview grid</span></span>

<span data-ttu-id="ceae0-113">Les outils de gestion pour teams se trouvent sous le nœud **équipes** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae0-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ceae0-114">(Dans le centre d’administration, sélectionnez **équipes** > **gérer les équipes**.) Chaque équipe est stockée par un groupe Office 365 et ce nœud fournit une vue des groupes qui ont été activés par Microsoft teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ceae0-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Capture d’écran de la grille de vue d’ensemble de teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="ceae0-116">La grille affiche les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="ceae0-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="ceae0-117">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="ceae0-117">**Team name**</span></span>
- <span data-ttu-id="ceae0-118">**Canaux** : nombre de canaux de l’équipe, y compris le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="ceae0-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="ceae0-119">**Membres** d’une équipe : nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="ceae0-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="ceae0-120">**Propriétaires** -nombre de propriétaires pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="ceae0-121">**Invités** -nombre d’utilisateurs invités d’Azure Active Directory B2B membres de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="ceae0-122">**Protection de la vie privée** -le groupe de AccessTypes 365 Office.</span><span class="sxs-lookup"><span data-stu-id="ceae0-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="ceae0-123">**État** : le statut archivé ou actif de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="ceae0-124">En savoir plus sur l’archivage d’équipes dans l' [archivage ou la restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="ceae0-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="ceae0-125">**Description** : description du groupe de stockage 365.</span><span class="sxs-lookup"><span data-stu-id="ceae0-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="ceae0-126">**Classification** : classification (si utilisée au sein de votre organisation) affectée au groupe Office 365 de stockage.</span><span class="sxs-lookup"><span data-stu-id="ceae0-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="ceae0-127">Pour plus d’informations sur [les catégories, voir créer des classifications pour les groupes Office au sein de votre organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ceae0-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="ceae0-128">**GroupID** -le GroupID unique du groupe Office 365 de stockage.</span><span class="sxs-lookup"><span data-stu-id="ceae0-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="ceae0-129">Si vous ne voyez pas ces propriétés dans la grille, cliquez sur l’icône **modifier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="ceae0-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="ceae0-130">Dans le volet **modifier les colonnes** , vous pouvez utiliser les boutons bascule pour activer ou désactiver les colonnes dans la grille.</span><span class="sxs-lookup"><span data-stu-id="ceae0-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="ceae0-131">Lorsque vous avez terminé, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="ceae0-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="ceae0-132">Ajoutée</span><span class="sxs-lookup"><span data-stu-id="ceae0-132">Add</span></span>

<span data-ttu-id="ceae0-133">Pour ajouter une nouvelle équipe, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ceae0-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="ceae0-134">Dans le volet **Ajouter une nouvelle équipe** , attribuez un nom et une description à l’équipe, définissez si vous souhaitez la définir comme une équipe privée ou publique et définir la classification.</span><span class="sxs-lookup"><span data-stu-id="ceae0-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="ceae0-135">Validation</span><span class="sxs-lookup"><span data-stu-id="ceae0-135">Edit</span></span>

<span data-ttu-id="ceae0-136">Pour modifier les paramètres spécifiques d’une équipe ou d’un groupe, sélectionnez l’équipe en cliquant à gauche du nom de l’équipe, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="ceae0-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="ceae0-137">Archivage</span><span class="sxs-lookup"><span data-stu-id="ceae0-137">Archive</span></span>

<span data-ttu-id="ceae0-138">Vous pouvez archiver une équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-138">You can archive a team.</span></span> <span data-ttu-id="ceae0-139">L’archivage d’une équipe place l’équipe en mode lecture seule dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ceae0-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="ceae0-140">En tant qu’administrateur, vous pouvez archiver et désarchiver des équipes au nom de votre organisation dans le centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="ceae0-140">As an admin, you can archive and unarchive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="ceae0-141">Annuler</span><span class="sxs-lookup"><span data-stu-id="ceae0-141">Delete</span></span>

<span data-ttu-id="ceae0-142">La suppression d’une équipe consiste à supprimer de l’équipe et au groupe Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="ceae0-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="ceae0-143">Pour restaurer une équipe supprimée par erreur, suivez les instructions de la procédure de [restauration d’un groupe Office 365 supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="ceae0-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="ceae0-144">Rechercher</span><span class="sxs-lookup"><span data-stu-id="ceae0-144">Search</span></span>

<span data-ttu-id="ceae0-145">La recherche prend actuellement en charge la chaîne « commence par » et recherche le champ nom de l' **équipe** .</span><span class="sxs-lookup"><span data-stu-id="ceae0-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="ceae0-146">Profil d’équipe</span><span class="sxs-lookup"><span data-stu-id="ceae0-146">Team profile</span></span>

<span data-ttu-id="ceae0-147">Vous pouvez accéder à la page de profil d’équipe de n’importe quelle équipe à partir de la grille de vue d’ensemble des équipes en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="ceae0-148">La page de profil de l’équipe montre les membres, les propriétaires et les invités qui appartiennent à l’équipe (et à son groupe Office 365), ainsi que les canaux et les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="ceae0-149">À partir de la page de profil d’équipe, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ceae0-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="ceae0-150">Ajoutez ou supprimez des membres et des propriétaires.</span><span class="sxs-lookup"><span data-stu-id="ceae0-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="ceae0-151">Ajoutez ou supprimez des canaux (Notez que vous ne pouvez pas supprimer le canal général).</span><span class="sxs-lookup"><span data-stu-id="ceae0-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="ceae0-152">Modifiez les paramètres d’équipe et de groupe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-152">Change team and group settings.</span></span>
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="ceae0-154">Modification d’équipes</span><span class="sxs-lookup"><span data-stu-id="ceae0-154">Making changes to teams</span></span>

<span data-ttu-id="ceae0-155">Dans la page de profil de l’équipe, vous pouvez modifier les éléments suivants d’une équipe :</span><span class="sxs-lookup"><span data-stu-id="ceae0-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="ceae0-156">**Membres** : ajoutez ou supprimez des membres et promouvez ou abaissez les propriétaires.</span><span class="sxs-lookup"><span data-stu-id="ceae0-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="ceae0-157">**Canaux** : ajoutez de nouveaux canaux, puis modifiez ou supprimez des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="ceae0-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="ceae0-158">N’oubliez pas que vous ne pouvez pas supprimer le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="ceae0-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="ceae0-159">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="ceae0-159">**Team name**</span></span>
- <span data-ttu-id="ceae0-160">**Description**</span><span class="sxs-lookup"><span data-stu-id="ceae0-160">**Description**</span></span>
- <span data-ttu-id="ceae0-161">**Confidentialité** : définissez si l’équipe est publique ou privée.</span><span class="sxs-lookup"><span data-stu-id="ceae0-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="ceae0-162">**Classification** : cette catégorie est stockée par vos classifications de groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="ceae0-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="ceae0-163">Sélectionnez **confidentiel**, **hautement confidentiel**ou **général**.</span><span class="sxs-lookup"><span data-stu-id="ceae0-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="ceae0-164">**Paramètres des conversations** : définir si les membres peuvent modifier et supprimer les messages envoyés.</span><span class="sxs-lookup"><span data-stu-id="ceae0-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="ceae0-165">**Paramètres des canaux** : définir si les membres peuvent créer de nouveaux canaux et modifier les canaux existants, et ajouter, modifier et supprimer des onglets, des connecteurs et des applications.</span><span class="sxs-lookup"><span data-stu-id="ceae0-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="ceae0-166">Les modifications que vous apportez à une équipe sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="ceae0-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="ceae0-167">Si vous modifiez les paramètres de groupe (en modifiant le nom, la description, la photo, la confidentialité, la classification ou les membres d’une équipe), les modifications vous sont attribuées via le pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="ceae0-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="ceae0-168">Si vous effectuez des actions sur des paramètres spécifiques aux équipes, vos modifications sont suivies et attribuées dans le canal général de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ceae0-169">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="ceae0-169">Troubleshooting</span></span>

<span data-ttu-id="ceae0-170">**Problème : les équipes n’apparaissent pas dans la grille de vue d’ensemble de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="ceae0-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="ceae0-171">Certaines de vos équipes ne figurent pas dans la liste des équipes de la grille de vue d’ensemble de teams.</span><span class="sxs-lookup"><span data-stu-id="ceae0-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="ceae0-172">**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou pas encore) profilée par le système qui peut entraîner une propriété manquante pour qu’elle soit reconnue.</span><span class="sxs-lookup"><span data-stu-id="ceae0-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="ceae0-173">**Résolution : définissez manuellement la propriété sur la valeur correcte via MS Graph.**</span><span class="sxs-lookup"><span data-stu-id="ceae0-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="ceae0-174">Remplacez **{GroupID}** dans la requête pour le GroupID réel en question, que vous pouvez obtenir par le biais d’Exchange Online PowerShell avec l’applet de requête **«[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , qui est l’attribut «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="ceae0-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="ceae0-175">[Explorateur de graphiques](https://developer.microsoft.com/en-us/graph/graph-explorer)Access.</span><span class="sxs-lookup"><span data-stu-id="ceae0-175">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span></span>

2. <span data-ttu-id="ceae0-176">Connectez-vous à l’Explorateur de graphiques dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="ceae0-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="ceae0-177">Modifiez la ligne de requête en : PATCH > > https://graph.microsoft.com/v1.0/groups/{groupid}.</span><span class="sxs-lookup"><span data-stu-id="ceae0-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="ceae0-178">Ajoutez la valeur suivante dans le corps de la requête : {"resourceProvisioningOptions" : ["équipe"]}.</span><span class="sxs-lookup"><span data-stu-id="ceae0-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="ceae0-179">Exécuter la requête en haut à droite.</span><span class="sxs-lookup"><span data-stu-id="ceae0-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="ceae0-180">Confirmez que l’équipe apparaît correctement dans le centre d’administration Microsoft teams-présentation de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="ceae0-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ceae0-181">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="ceae0-181">Learn more</span></span>

- [<span data-ttu-id="ceae0-182">Référence sur les applets de fonction teams</span><span class="sxs-lookup"><span data-stu-id="ceae0-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="ceae0-183">Utiliser les rôles d’administrateur d’équipes pour gérer teams</span><span class="sxs-lookup"><span data-stu-id="ceae0-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="ceae0-184">Planifier la gestion du cycle de vie dans Teams</span><span class="sxs-lookup"><span data-stu-id="ceae0-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
