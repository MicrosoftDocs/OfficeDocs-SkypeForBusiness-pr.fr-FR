---
title: Gérer les équipes dans le centre d’administration Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes dans le centre d’administration Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202736"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="42500-103">Gérer les équipes dans le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42500-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="42500-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="42500-104">Overview</span></span>

<span data-ttu-id="42500-105">En tant qu’un administrateur informatique, vous devrez peut-être afficher ou mettre à jour les équipes de votre organisation a configuré pour la collaboration, ou vous devrez effectuer des actions telles que l’affectation de propriétaires pour les équipes ownerless correction.</span><span class="sxs-lookup"><span data-stu-id="42500-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="42500-106">Vous pouvez gérer les équipes utilisés dans votre organisation via le module PowerShell d’équipes Microsoft et le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42500-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="42500-107">Pour les fonctionnalités d’administration complète à l’aide de ces deux ensembles d’outils, assurez-vous que vous sont affectés à un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="42500-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="42500-108">Administrateur global</span><span class="sxs-lookup"><span data-stu-id="42500-108">Global Administrator</span></span>
- <span data-ttu-id="42500-109">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="42500-109">Teams Service Administrator</span></span>

<span data-ttu-id="42500-110">Vous en apprendrez plus sur les rôles d’administrateur dans les équipes dans [utiliser des équipes Microsoft des rôles d’administration pour gérer des équipes](using-admin-roles.md), et vous pouvez en savoir plus sur la façon d’utiliser les applets de commande PowerShell pour la gestion des équipes dans la [référence d’applet de commande équipes Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="42500-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="42500-111">Cet article fournit une vue d’ensemble des outils de gestion des équipes dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42500-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="42500-112">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="42500-112">Teams overview grid</span></span>

<span data-ttu-id="42500-113">Outils de gestion pour les équipes sont sous le nœud **d’équipes** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42500-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="42500-114">(Dans le centre d’administration, sélectionnez **les équipes** > **Gérer les équipes**.) Chaque équipe bénéficie d’un groupe d’Office 365, et ce nœud fournit une vue des groupes qui ont été Microsoft équipes activées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="42500-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Vue d’ensemble des équipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="42500-116">La grille affiche les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="42500-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="42500-117">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="42500-117">**Team name**</span></span>
- <span data-ttu-id="42500-118">**Canaux** - un décompte de tous les canaux de l’équipe, y compris le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="42500-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="42500-119">**Utilisateurs** : nombre d’utilisateurs au total, y compris les propriétaires, les invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="42500-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="42500-120">**Propriétaires** - nombre de propriétaires pour cette association.</span><span class="sxs-lookup"><span data-stu-id="42500-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="42500-121">**Les invités** - un décompte d’Azure Active Directory B2B invité utilisateurs sont membres de cette association.</span><span class="sxs-lookup"><span data-stu-id="42500-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="42500-122">**Confidentialité** - la visibilité/AccessType du groupe sauvegarde Office 365.</span><span class="sxs-lookup"><span data-stu-id="42500-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="42500-123">**État** - l’archivé ou un statut actif pour cette association.</span><span class="sxs-lookup"><span data-stu-id="42500-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="42500-124">Pour plus d’informations sur l’archivage des équipes dans l' [Archive ou la restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="42500-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="42500-125">**GroupID** - GroupID unique du groupe de stockage Office 365</span><span class="sxs-lookup"><span data-stu-id="42500-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="42500-126">**Classification** - la classification (si utilisé dans votre organisation) affectée au groupe de sauvegarde Office 365.</span><span class="sxs-lookup"><span data-stu-id="42500-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="42500-127">Pour plus d’informations sur les classifications à [créer des classifications pour les groupes d’Office dans votre organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="42500-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="42500-128">**Description** : la description pour le groupe de stockage Office 365</span><span class="sxs-lookup"><span data-stu-id="42500-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="42500-129">Rechercher</span><span class="sxs-lookup"><span data-stu-id="42500-129">Search</span></span>

<span data-ttu-id="42500-130">Recherche actuellement prend en charge la chaîne « Commence par » et recherche dans le champ **nom de l’équipe** .</span><span class="sxs-lookup"><span data-stu-id="42500-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="42500-131">Modifier</span><span class="sxs-lookup"><span data-stu-id="42500-131">Edit</span></span>

<span data-ttu-id="42500-132">Vous pouvez modifier les paramètres de groupe et spécifiques à l’équipe en sélectionnant une équipe à partir de la grille, puis cliquez sur le bouton **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="42500-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Modifier l’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="42500-134">Profil de l’équipe</span><span class="sxs-lookup"><span data-stu-id="42500-134">Team profile</span></span>

<span data-ttu-id="42500-135">Vous pouvez naviguer vers la page de profil de l’équipe de toute l’équipe à partir de la grille de vue d’ensemble des équipes principale en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="42500-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="42500-136">La page de profil de l’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et sa sauvegarde O365 groupe), ainsi que les canaux et les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="42500-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="42500-137">Dans la page de profil de l’équipe, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="42500-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="42500-138">Ajouter ou supprimer des membres et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="42500-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="42500-139">Ajouter ou supprimer des canaux (Notez que vous ne pouvez pas supprimer le canal général).</span><span class="sxs-lookup"><span data-stu-id="42500-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="42500-140">Mettre à jour de l’équipe et les paramètres de groupe.</span><span class="sxs-lookup"><span data-stu-id="42500-140">Update team and group settings.</span></span>
 
![Profil de l’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="42500-142">Apporter des modifications aux équipes</span><span class="sxs-lookup"><span data-stu-id="42500-142">Making changes to teams</span></span>

<span data-ttu-id="42500-143">Vous pouvez modifier les éléments d’une équipe suivants :</span><span class="sxs-lookup"><span data-stu-id="42500-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="42500-144">**Les utilisateurs de l’équipe** : vous pouvez ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires de</span><span class="sxs-lookup"><span data-stu-id="42500-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="42500-145">**Canaux** - vous pouvez ajouter de nouvelles voies ou supprimer des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="42500-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="42500-146">Vous ne pouvez pas supprimer le canal « General » par défaut, une fois créée, vous ne pouvez modifier que le nom de canal, pas de description.</span><span class="sxs-lookup"><span data-stu-id="42500-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="42500-147">**Nom de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="42500-147">**Team name**</span></span>
- <span data-ttu-id="42500-148">**Description de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="42500-148">**Team description**</span></span>
- <span data-ttu-id="42500-149">**Confidentialité de l’équipe** - public ou privé</span><span class="sxs-lookup"><span data-stu-id="42500-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="42500-150">**Classement de l’équipe** - soutenues par vos classifications de groupe Office 365</span><span class="sxs-lookup"><span data-stu-id="42500-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="42500-151">**Paramètres du membre d’équipe** - paramètres du membre d’équipe select</span><span class="sxs-lookup"><span data-stu-id="42500-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="42500-152">Autres modifications aux équipes pris en charge</span><span class="sxs-lookup"><span data-stu-id="42500-152">Other supported changes to teams</span></span>

- <span data-ttu-id="42500-153">**Supprimer** : suppression d’une équipe est une suppression logicielle de l’équipe et le groupe d’Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="42500-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="42500-154">Pour restaurer une équipe supprimé par inadvertance, suivez les instructions à [restaurer un groupe de 365 Office supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="42500-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="42500-155">**Archive** : l’archivage d’une équipe place l’équipe en mode lecture seule dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42500-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="42500-156">En tant qu’administrateur, vous pouvez archiver et réactivation équipes d'archivée au nom de votre organisation via le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="42500-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="42500-157">Les modifications que vous apportez à une équipe sont consignées.</span><span class="sxs-lookup"><span data-stu-id="42500-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="42500-158">Si vous modifiez les paramètres de groupe (modifier le nom, description, photo, confidentialité, classement ou membres de l’équipe), ces modifications à attribuer à votre via le pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="42500-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="42500-159">Si vous effectuez des actions sur les paramètres spécifiques d’équipes, vos modifications seront suivies et attribuer aux vous dans le canal généraux de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="42500-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="42500-160">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="42500-160">Troubleshooting</span></span>

<span data-ttu-id="42500-161">**Problème : Les équipes manquantes dans la grille de vue d’ensemble de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="42500-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="42500-162">Lorsque vous entrez le centre d’administration Microsoft Teams, sous l’option **équipes** manque certains de vos équipes à partir de la liste dans la vue d’ensemble des équipes.</span><span class="sxs-lookup"><span data-stu-id="42500-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="42500-163">**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou non) de profilage par le système qui peut entraîner une propriété manquante pour qu’il puisse être reconnu.</span><span class="sxs-lookup"><span data-stu-id="42500-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="42500-164">**Solution : Définissez manuellement la propriété à la valeur correcte via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="42500-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="42500-165">Remplacez **{groupid}** dans la requête de GroupId réel en question, que vous pouvez obtenir via le Exchange Online powershell, l’applet de commande **«[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , en tant que l’attribut «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="42500-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="42500-166">Accès [graphique Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="42500-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="42500-167">Se connecter à l’Explorateur de graphique dans le menu de gauche</span><span class="sxs-lookup"><span data-stu-id="42500-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="42500-168">Modifiez la ligne de requête : correctif > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="42500-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="42500-169">Ajoutez la valeur suivante dans le corps de la demande : {« resourceProvisioningOptions » : [« Team »]}</span><span class="sxs-lookup"><span data-stu-id="42500-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="42500-170">Exécutez la requête sur le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="42500-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="42500-171">Vérifiez que l’équipe s’affiche correctement dans le centre d’administration Microsoft Teams - vue d’ensemble de l’équipe</span><span class="sxs-lookup"><span data-stu-id="42500-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="42500-172">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="42500-172">Learn more</span></span>

[<span data-ttu-id="42500-173">Référence d’applet de commande Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42500-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="42500-174">Rôles d’administrateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42500-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

