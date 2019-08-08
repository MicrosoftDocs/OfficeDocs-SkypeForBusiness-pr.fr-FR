---
title: Gérer teams dans le centre d’administration Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes dans le centre d’administration Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233351"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="eb1c3-103">Gérer teams dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="eb1c3-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="eb1c3-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="eb1c3-104">Overview</span></span>

<span data-ttu-id="eb1c3-105">En tant qu’administrateur informatique, il est possible que vous deviez afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration, ou vous devrez peut-être effectuer des actions de correction telles que l’affectation de propriétaires à des équipes propriétaires.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="eb1c3-106">Vous pouvez gérer les équipes utilisées dans votre organisation via le module Microsoft teams PowerShell et le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="eb1c3-107">Pour pouvoir bénéficier d’une administration complète de ces deux ensembles d’outils, assurez-vous que vous disposez de l’un des rôles suivants:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="eb1c3-108">Administrateur général</span><span class="sxs-lookup"><span data-stu-id="eb1c3-108">Global Administrator</span></span>
- <span data-ttu-id="eb1c3-109">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="eb1c3-109">Teams Service Administrator</span></span>

<span data-ttu-id="eb1c3-110">Pour en savoir plus sur les rôles d’administrateur dans équipes, [Utilisez les rôles d’administrateur de Microsoft teams pour gérer teams](using-admin-roles.md), et apprenez-en davantage sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la référence des cmdlets de [Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="eb1c3-111">Cet article fournit une vue d’ensemble des outils de gestion pour teams dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="eb1c3-112">Grille de vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="eb1c3-112">Teams overview grid</span></span>

<span data-ttu-id="eb1c3-113">Les outils de gestion pour teams se trouvent sous le nœud **équipes** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="eb1c3-114">(Dans le centre d’administration, sélectionnez **équipes** > **gérer les équipes**.) Chaque équipe est stockée par un groupe Office 365 et ce nœud fournit une vue des groupes qui ont été activés par Microsoft teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Capture d’écran de la grille de vue d’ensemble de teams](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="eb1c3-116">La grille affiche les propriétés suivantes:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="eb1c3-117">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="eb1c3-117">**Team name**</span></span>
- <span data-ttu-id="eb1c3-118">**Canaux** : nombre de canaux de l’équipe, y compris le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="eb1c3-119">**Utilisateurs** : nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="eb1c3-120">**Propriétaires** -nombre de propriétaires pour cette équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="eb1c3-121">**Invités** -nombre d’utilisateurs invités d’Azure Active Directory B2B membres de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="eb1c3-122">**Protection de la vie privée** -le groupe de AccessTypes 365 Office.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="eb1c3-123">**État** : le statut archivé ou actif de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="eb1c3-124">En savoir plus sur l’archivage d’équipes dans l' [archivage ou la restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="eb1c3-125">**GroupID** -le GroupID unique du groupe Office 365 de stockage</span><span class="sxs-lookup"><span data-stu-id="eb1c3-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="eb1c3-126">**Classification** : classification (si utilisée au sein de votre organisation) affectée au groupe Office 365 de stockage.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="eb1c3-127">Pour plus d’informations sur [les catégories, voir créer des classifications pour les groupes Office au sein de votre organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="eb1c3-128">**Description** -la description définie pour le groupe de 365 Office</span><span class="sxs-lookup"><span data-stu-id="eb1c3-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="eb1c3-129">Rechercher</span><span class="sxs-lookup"><span data-stu-id="eb1c3-129">Search</span></span>

<span data-ttu-id="eb1c3-130">La recherche prend actuellement en charge la chaîne «commence par» et recherche le champ nom de l' **équipe** .</span><span class="sxs-lookup"><span data-stu-id="eb1c3-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="eb1c3-131">Validation</span><span class="sxs-lookup"><span data-stu-id="eb1c3-131">Edit</span></span>

<span data-ttu-id="eb1c3-132">Vous pouvez modifier les paramètres spécifiques d’une équipe ou d’un groupe en sélectionnant une équipe dans la grille, puis en cliquant sur le bouton **modifier** .</span><span class="sxs-lookup"><span data-stu-id="eb1c3-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Capture d’écran des options de modification d’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="eb1c3-134">Profil d’équipe</span><span class="sxs-lookup"><span data-stu-id="eb1c3-134">Team profile</span></span>

<span data-ttu-id="eb1c3-135">Vous pouvez accéder à la page de profil d’équipe de n’importe quelle équipe à partir de la grille de vue d’ensemble des équipes en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="eb1c3-136">La page de profil d’équipe montre les membres, les propriétaires et les invités qui appartiennent à l’équipe (et à son groupe O365 de stockage), ainsi que les canaux et les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="eb1c3-137">À partir de la page de profil d’équipe, vous pouvez:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="eb1c3-138">Ajoutez ou supprimez des membres et des propriétaires.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="eb1c3-139">Ajoutez ou supprimez des canaux (Notez que vous ne pouvez pas supprimer le canal général).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="eb1c3-140">Mettez à jour les paramètres d’équipe et de groupe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-140">Update team and group settings.</span></span>
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="eb1c3-142">Modification d’équipes</span><span class="sxs-lookup"><span data-stu-id="eb1c3-142">Making changes to teams</span></span>

<span data-ttu-id="eb1c3-143">Vous pouvez modifier les éléments suivants d’une équipe:</span><span class="sxs-lookup"><span data-stu-id="eb1c3-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="eb1c3-144">**Utilisateurs au sein de l’équipe** : vous pouvez ajouter ou supprimer des membres, et promouvoir ou abaisser des propriétaires.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="eb1c3-145">**Canaux** : vous pouvez ajouter de nouveaux canaux ou supprimer des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="eb1c3-146">Vous ne pouvez pas supprimer le canal «général» par défaut, et une fois créé, vous pouvez uniquement modifier le nom d’un canal, et non une description.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="eb1c3-147">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="eb1c3-147">**Team name**</span></span>
- <span data-ttu-id="eb1c3-148">**Description de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="eb1c3-148">**Team description**</span></span>
- <span data-ttu-id="eb1c3-149">**Confidentialité** de l’équipe-public ou privé</span><span class="sxs-lookup"><span data-stu-id="eb1c3-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="eb1c3-150">**Classification d’équipe** -par vos classifications de groupe Office 365</span><span class="sxs-lookup"><span data-stu-id="eb1c3-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="eb1c3-151">**Paramètres des membres** de l’équipe-sélectionner les paramètres des membres de l’équipe</span><span class="sxs-lookup"><span data-stu-id="eb1c3-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="eb1c3-152">Autres modifications prises en charge dans teams</span><span class="sxs-lookup"><span data-stu-id="eb1c3-152">Other supported changes to teams</span></span>

- <span data-ttu-id="eb1c3-153">**Supprimer** : la suppression d’une équipe consiste à supprimer par le biais d’une équipe et d’un groupe Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="eb1c3-154">Pour restaurer une équipe supprimée par erreur, suivez les instructions de la procédure de [restauration d’un groupe Office 365 supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="eb1c3-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="eb1c3-155">**Archive** -archivage une équipe place l’équipe en mode lecture seule dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="eb1c3-156">En tant qu’administrateur, vous pouvez archiver et désarchiver des équipes au nom de votre organisation via le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="eb1c3-157">Les modifications que vous apportez à une équipe sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="eb1c3-158">Si vous modifiez les paramètres de groupe (en modifiant le nom, la description, la photo, la confidentialité, la classification ou les membres d’une équipe), ces modifications vous seront attribuées par le biais du pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="eb1c3-159">Si vous effectuez des actions sur des paramètres spécifiques aux équipes, vos modifications sont suivies et attribuées dans le canal général de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="eb1c3-160">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="eb1c3-160">Troubleshooting</span></span>

<span data-ttu-id="eb1c3-161">**Problème: les équipes n’apparaissent pas dans la grille de vue d’ensemble de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="eb1c3-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="eb1c3-162">Lorsque vous entrez dans le centre d’administration de Microsoft Teams, certaines de vos équipes ne figurent pas dans la liste de la grille de vue d’ensemble de teams. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="eb1c3-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="eb1c3-163">**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou pas encore) profilée par le système qui peut entraîner une propriété manquante pour qu’elle soit reconnue.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="eb1c3-164">**Résolution: définissez manuellement la propriété sur la valeur correcte via MS Graph.**</span><span class="sxs-lookup"><span data-stu-id="eb1c3-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="eb1c3-165">Remplacez **{GroupID}** dans la requête pour le GroupID réel en question, que vous pouvez obtenir par le biais d’Exchange Online PowerShell avec l’applet de requête **«[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , qui est l’attribut «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="eb1c3-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="eb1c3-166">[Explorateur de graphiques](https://developer.microsoft.com/en-us/graph/graph-explorer) Access</span><span class="sxs-lookup"><span data-stu-id="eb1c3-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="eb1c3-167">Se connecter à l’Explorateur de graphiques dans le menu de gauche</span><span class="sxs-lookup"><span data-stu-id="eb1c3-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="eb1c3-168">Changer la ligne de requête en: correctif > version 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="eb1c3-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="eb1c3-169">Ajoutez la valeur suivante dans le corps de la requête: {"resourceProvisioningOptions": ["équipe"]}</span><span class="sxs-lookup"><span data-stu-id="eb1c3-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="eb1c3-170">Exécuter la requête en haut à droite.</span><span class="sxs-lookup"><span data-stu-id="eb1c3-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="eb1c3-171">Confirmez que l’équipe apparaît correctement dans le centre d’administration Microsoft teams-présentation de l’équipe</span><span class="sxs-lookup"><span data-stu-id="eb1c3-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="eb1c3-172">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="eb1c3-172">Learn more</span></span>

[<span data-ttu-id="eb1c3-173">Référence sur les applets de passe Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="eb1c3-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="eb1c3-174">Rôles d’administrateur dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="eb1c3-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

