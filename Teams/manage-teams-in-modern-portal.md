---
title: Gérer les équipes dans le & Microsoft Teams Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes dans le & Microsoft Teams Skype entreprise centre d’administration.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: df8e60f8a5d7aaf2638e1220baf1c41a59075ae0
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706441"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="7d25e-103">Gérer les équipes dans le & Microsoft Teams Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="7d25e-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="7d25e-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="7d25e-104">Overview</span></span>

<span data-ttu-id="7d25e-105">En tant qu’un administrateur informatique, vous devrez peut-être afficher ou mettre à jour les équipes de votre organisation a configuré pour la collaboration, ou vous devrez effectuer des actions telles que l’affectation de propriétaires pour les équipes ownerless correction.</span><span class="sxs-lookup"><span data-stu-id="7d25e-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="7d25e-106">Vous pouvez gérer les équipes utilisés dans votre organisation via le module PowerShell d’équipes Microsoft et la & Microsoft Teams Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="7d25e-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="7d25e-107">Pour les fonctionnalités d’administration complète à l’aide de ces deux ensembles d’outils, assurez-vous que vous sont affectés à un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="7d25e-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="7d25e-108">Administrateur global</span><span class="sxs-lookup"><span data-stu-id="7d25e-108">Global Administrator</span></span>
- <span data-ttu-id="7d25e-109">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="7d25e-109">Teams Service Administrator</span></span>

<span data-ttu-id="7d25e-110">Vous devez également vous assurer que votre compte a été attribué une licence d’équipes non-version d’évaluation pour la gestion.</span><span class="sxs-lookup"><span data-stu-id="7d25e-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="7d25e-111">Dans le cadre d’un problème connu, vous devez vous assurer que votre compte qu' **un** administrateur rôle a été attribué.</span><span class="sxs-lookup"><span data-stu-id="7d25e-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="7d25e-112">Vous en apprendrez plus sur les rôles d’administrateur dans Microsoft Teams dans [utiliser des équipes Microsoft des rôles d’administration pour gérer des équipes](using-admin-roles.md), et vous pouvez en savoir plus sur la façon d’utiliser les applets de commande PowerShell pour la gestion des équipes dans la [référence d’applet de commande équipes Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7d25e-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="7d25e-113">Cet article fournit une vue d’ensemble des outils de gestion des équipes dans le & Microsoft Teams Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="7d25e-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="7d25e-114">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="7d25e-114">Teams overview grid</span></span>

<span data-ttu-id="7d25e-115">Outils de gestion pour les équipes sont sous le nœud **d’équipes** dans le & Microsoft Teams Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="7d25e-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="7d25e-116">(Dans le centre d’administration, sélectionnez **les équipes** > **Gérer les équipes**.) Chaque équipe bénéficie d’un groupe d’Office 365, et ce nœud fournit une vue des groupes qui ont été Microsoft équipes activées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7d25e-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="7d25e-117">Est en cours de renvoi créé précédemment équipes pour vous assurer qu’ils s’affichent dans cette vue.</span><span class="sxs-lookup"><span data-stu-id="7d25e-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Vue d’ensemble des équipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="7d25e-119">La grille affiche les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d25e-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="7d25e-120">**Nom de l'équipe**</span><span class="sxs-lookup"><span data-stu-id="7d25e-120">**Team name**</span></span>
- <span data-ttu-id="7d25e-121">**Canaux** - un décompte de tous les canaux de l’équipe, y compris le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="7d25e-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="7d25e-122">**Utilisateurs** : nombre d’utilisateurs au total, y compris les propriétaires, les invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="7d25e-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="7d25e-123">**Propriétaires** - nombre de propriétaires pour cette association.</span><span class="sxs-lookup"><span data-stu-id="7d25e-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="7d25e-124">**Les invités** - un décompte d’Azure Active Directory B2B invité utilisateurs sont membres de cette association.</span><span class="sxs-lookup"><span data-stu-id="7d25e-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="7d25e-125">**Confidentialité** - le AccessType du groupe sauvegarde Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d25e-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="7d25e-126">Recherche</span><span class="sxs-lookup"><span data-stu-id="7d25e-126">Search</span></span>

<span data-ttu-id="7d25e-127">Recherche actuellement prend en charge la chaîne « Commence par » et recherche dans le champ **nom de l’équipe** .</span><span class="sxs-lookup"><span data-stu-id="7d25e-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="7d25e-128">Modifier</span><span class="sxs-lookup"><span data-stu-id="7d25e-128">Edit</span></span>

<span data-ttu-id="7d25e-129">Vous pouvez modifier les paramètres de groupe et spécifiques à l’équipe en sélectionnant une équipe à partir de la grille, puis cliquez sur le bouton **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="7d25e-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Modifier l’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="7d25e-131">Profil de l’équipe</span><span class="sxs-lookup"><span data-stu-id="7d25e-131">Team profile</span></span>

<span data-ttu-id="7d25e-132">Vous pouvez naviguer vers la page de profil de l’équipe de toute l’équipe à partir de la grille de vue d’ensemble des équipes principale en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7d25e-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="7d25e-133">La page de profil de l’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et sa sauvegarde O365 groupe), ainsi que les canaux et les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7d25e-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="7d25e-134">Dans la page de profil de l’équipe, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="7d25e-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="7d25e-135">Ajouter ou supprimer des membres et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="7d25e-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="7d25e-136">Ajouter ou supprimer des canaux (Notez que vous ne pouvez pas supprimer le canal général).</span><span class="sxs-lookup"><span data-stu-id="7d25e-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="7d25e-137">Mettre à jour de l’équipe et les paramètres de groupe.</span><span class="sxs-lookup"><span data-stu-id="7d25e-137">Update team and group settings.</span></span>
 
![Profil de l’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="7d25e-139">Apporter des modifications aux équipes</span><span class="sxs-lookup"><span data-stu-id="7d25e-139">Making changes to teams</span></span>

<span data-ttu-id="7d25e-140">Vous pouvez modifier les éléments d’une équipe suivants :</span><span class="sxs-lookup"><span data-stu-id="7d25e-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="7d25e-141">**Les utilisateurs de l’équipe** : vous pouvez ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires de</span><span class="sxs-lookup"><span data-stu-id="7d25e-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="7d25e-142">**Canaux** - vous pouvez ajouter de nouvelles voies ou supprimer des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="7d25e-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="7d25e-143">Vous ne pouvez pas supprimer le canal « General » par défaut, une fois créée, vous ne pouvez modifier que le nom de canal, pas de description.</span><span class="sxs-lookup"><span data-stu-id="7d25e-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="7d25e-144">**Nom de l'équipe**</span><span class="sxs-lookup"><span data-stu-id="7d25e-144">**Team name**</span></span>
- <span data-ttu-id="7d25e-145">**Description de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="7d25e-145">**Team description**</span></span>
- <span data-ttu-id="7d25e-146">**Confidentialité de l’équipe** - public ou privé</span><span class="sxs-lookup"><span data-stu-id="7d25e-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="7d25e-147">**Classement de l’équipe** - soutenues par vos classifications de groupe Office 365</span><span class="sxs-lookup"><span data-stu-id="7d25e-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="7d25e-148">**Paramètres du membre d’équipe** - paramètres du membre d’équipe select</span><span class="sxs-lookup"><span data-stu-id="7d25e-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="7d25e-149">Les modifications que vous apportez à une équipe sont consignées.</span><span class="sxs-lookup"><span data-stu-id="7d25e-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="7d25e-150">Si vous modifiez les paramètres de groupe (modifier le nom, description, photo, confidentialité, classement ou membres de l’équipe), ces modifications à attribuer à votre via le pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="7d25e-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="7d25e-151">Si vous effectuez des actions sur les paramètres spécifiques d’équipes, vos modifications seront suivies et attribuer aux vous dans le canal généraux de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7d25e-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7d25e-152">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="7d25e-152">Troubleshooting</span></span>

<span data-ttu-id="7d25e-153">**Problème : Les équipes manquantes dans la grille de vue d’ensemble de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="7d25e-153">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="7d25e-154">Lorsque vous entrez les & Microsoft Teams Skype entreprise centre d’administration, sous l’option **équipes** manque certains de vos équipes à partir de la liste dans la vue d’ensemble des équipes.</span><span class="sxs-lookup"><span data-stu-id="7d25e-154">When you enter the Microsoft Teams & Skype for Business Admin Center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="7d25e-155">**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou non) de profilage par le système qui peut entraîner une propriété manquante pour qu’il puisse être reconnu.</span><span class="sxs-lookup"><span data-stu-id="7d25e-155">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="7d25e-156">**Solution : Définissez manuellement la propriété à la valeur correcte via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="7d25e-156">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="7d25e-157">Remplacez **{groupid}** dans la requête de GroupId réel en question, que vous pouvez obtenir via le Exchange Online powershell, l’applet de commande **«[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , en tant que l’attribut «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="7d25e-157">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="7d25e-158">Accès [graphique Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="7d25e-158">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="7d25e-159">Se connecter à l’Explorateur de graphique dans le menu de gauche</span><span class="sxs-lookup"><span data-stu-id="7d25e-159">Sign in to Graph Explorer on the left-hand side menu</span></span>

3. <span data-ttu-id="7d25e-160">Modifiez la ligne de requête : correctif > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="7d25e-160">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="7d25e-161">Ajoutez la valeur suivante dans le corps de la demande : {« resourceProvisioningOptions » : [« Team »]}</span><span class="sxs-lookup"><span data-stu-id="7d25e-161">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="7d25e-162">Exécutez la requête sur le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="7d25e-162">Run the Query on the Top-Right.</span></span>

6. <span data-ttu-id="7d25e-163">Vérifiez que l’équipe s’affiche correctement sur la & Microsoft Teams Skype pour Business Admin Center - vue d’ensemble de l’équipe</span><span class="sxs-lookup"><span data-stu-id="7d25e-163">Confirm the team appears correctly back on the Microsoft Teams & Skype for Business Admin Center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="7d25e-164">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="7d25e-164">Learn more</span></span>

[<span data-ttu-id="7d25e-165">Référence d’applet de commande Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d25e-165">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="7d25e-166">Rôles d’administrateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d25e-166">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

