---
title: Gérer les équipes Microsoft Teams et Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes Microsoft Teams et Skype entreprise centre d’administration.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8d517ce7f2fb614a22c45fcf63d59a7d46b606f
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502333"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="3ff29-103">Gérer les équipes Microsoft Teams et Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="3ff29-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="3ff29-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="3ff29-104">Overview</span></span>

<span data-ttu-id="3ff29-105">En tant qu’un administrateur informatique, vous devrez peut-être afficher ou mettre à jour les équipes de votre organisation a configuré pour la collaboration, ou vous devrez effectuer des actions telles que l’affectation de propriétaires pour les équipes ownerless correction.</span><span class="sxs-lookup"><span data-stu-id="3ff29-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="3ff29-106">Vous pouvez gérer les équipes utilisés dans votre organisation via le module PowerShell d’équipes Microsoft et les Microsoft Teams & Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ff29-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="3ff29-107">Pour les fonctionnalités d’administration complète à l’aide de ces deux ensembles d’outils, assurez-vous que vous sont affectés à un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="3ff29-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="3ff29-108">Administrateur global</span><span class="sxs-lookup"><span data-stu-id="3ff29-108">Global Administrator</span></span>
- <span data-ttu-id="3ff29-109">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="3ff29-109">Teams Service Administrator</span></span>

<span data-ttu-id="3ff29-110">Vous en apprendrez plus sur les rôles d’administrateur dans Microsoft Teams [ici](using-admin-roles.md), et vous pouvez en savoir plus sur la façon d’utiliser les applets de commande PowerShell pour la gestion des équipes dans la [référence d’applet de commande équipes Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="3ff29-110">You can learn more about admin roles in Microsoft Teams [here](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="3ff29-111">Cet article fournit une vue d’ensemble des outils de gestion pour les équipes Microsoft Teams et Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ff29-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="3ff29-112">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="3ff29-112">Teams overview grid</span></span>

<span data-ttu-id="3ff29-113">Outils de gestion pour les équipes sont sous le nœud **équipes** Microsoft Teams et Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ff29-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="3ff29-114">(Dans le centre d’administration, sélectionnez **les équipes** > **Gérer les équipes**.) Chaque équipe bénéficie d’un groupe d’Office 365, et ce nœud fournit un affichage de tous les groupes qui ont été Microsoft équipes activées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3ff29-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of all groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Vue d’ensemble des équipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="3ff29-116">La grille affiche les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="3ff29-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="3ff29-117">**Nom de l'équipe**</span><span class="sxs-lookup"><span data-stu-id="3ff29-117">**Team name**</span></span>
- <span data-ttu-id="3ff29-118">**Canaux** - un décompte de tous les canaux de l’équipe, y compris le canal général par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ff29-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="3ff29-119">**Utilisateurs** : nombre d’utilisateurs au total, y compris les propriétaires, les invités et membres de votre client.</span><span class="sxs-lookup"><span data-stu-id="3ff29-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="3ff29-120">**Propriétaires** - nombre de propriétaires pour cette association.</span><span class="sxs-lookup"><span data-stu-id="3ff29-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="3ff29-121">**Les invités** - un décompte d’Azure Active Directory B2B invité utilisateurs sont membres de cette association.</span><span class="sxs-lookup"><span data-stu-id="3ff29-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="3ff29-122">**Confidentialité** - le AccessType du groupe sauvegarde Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ff29-122">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="3ff29-123">Recherche</span><span class="sxs-lookup"><span data-stu-id="3ff29-123">Search</span></span>

<span data-ttu-id="3ff29-124">Recherche actuellement prend en charge la chaîne « Commence par » et recherche dans le champ **nom de l’équipe** .</span><span class="sxs-lookup"><span data-stu-id="3ff29-124">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="3ff29-125">Modifier</span><span class="sxs-lookup"><span data-stu-id="3ff29-125">Edit</span></span>

<span data-ttu-id="3ff29-126">Vous pouvez modifier les paramètres de groupe et spécifiques à l’équipe en sélectionnant une équipe à partir de la grille, puis cliquez sur le bouton **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="3ff29-126">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Modifier l’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="3ff29-128">Profil de l’équipe</span><span class="sxs-lookup"><span data-stu-id="3ff29-128">Team profile</span></span>

<span data-ttu-id="3ff29-129">Vous pouvez naviguer vers la page de profil de l’équipe de toute l’équipe à partir de la grille de vue d’ensemble des équipes principale en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3ff29-129">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="3ff29-130">La page de profil de l’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et sa sauvegarde O365 groupe), ainsi que les canaux et les paramètres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3ff29-130">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="3ff29-131">Dans la page de profil de l’équipe, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="3ff29-131">From the team profile page, you can:</span></span>

- <span data-ttu-id="3ff29-132">Ajouter ou supprimer des membres et propriétaires.</span><span class="sxs-lookup"><span data-stu-id="3ff29-132">Add or remove members and owners.</span></span>
- <span data-ttu-id="3ff29-133">Ajouter ou supprimer des canaux (Notez que vous ne pouvez pas supprimer le canal général).</span><span class="sxs-lookup"><span data-stu-id="3ff29-133">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="3ff29-134">Mettre à jour de l’équipe et les paramètres de groupe.</span><span class="sxs-lookup"><span data-stu-id="3ff29-134">Update team and group settings.</span></span>
 
![Profil de l’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="3ff29-136">Apporter des modifications aux équipes</span><span class="sxs-lookup"><span data-stu-id="3ff29-136">Making changes to teams</span></span>

<span data-ttu-id="3ff29-137">Vous pouvez modifier les éléments d’une équipe suivants :</span><span class="sxs-lookup"><span data-stu-id="3ff29-137">You can change the following elements of a team:</span></span>
- <span data-ttu-id="3ff29-138">**Les utilisateurs de l’équipe** : vous pouvez ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires de</span><span class="sxs-lookup"><span data-stu-id="3ff29-138">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="3ff29-139">**Canaux** - vous pouvez ajouter de nouvelles voies ou supprimer des canaux existants.</span><span class="sxs-lookup"><span data-stu-id="3ff29-139">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="3ff29-140">Vous ne pouvez pas supprimer le canal « General » par défaut, une fois créée, vous ne pouvez modifier que le nom de canal, pas de description.</span><span class="sxs-lookup"><span data-stu-id="3ff29-140">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="3ff29-141">**Nom de l'équipe**</span><span class="sxs-lookup"><span data-stu-id="3ff29-141">**Team name**</span></span>
- <span data-ttu-id="3ff29-142">**Description de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="3ff29-142">**Team description**</span></span>
- <span data-ttu-id="3ff29-143">**Photo de l’équipe**</span><span class="sxs-lookup"><span data-stu-id="3ff29-143">**Team photo**</span></span>
- <span data-ttu-id="3ff29-144">**Confidentialité de l’équipe** - public ou privé</span><span class="sxs-lookup"><span data-stu-id="3ff29-144">**Team privacy** - public or private</span></span>
- <span data-ttu-id="3ff29-145">**Classement de l’équipe** - soutenues par vos classifications de groupe Office 365</span><span class="sxs-lookup"><span data-stu-id="3ff29-145">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="3ff29-146">**Paramètres du membre d’équipe** - paramètres du membre d’équipe select</span><span class="sxs-lookup"><span data-stu-id="3ff29-146">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="3ff29-147">Les modifications que vous apportez à une équipe sont consignées.</span><span class="sxs-lookup"><span data-stu-id="3ff29-147">The changes that you make to a team are logged.</span></span> <span data-ttu-id="3ff29-148">Si vous modifiez les paramètres de groupe (modifier le nom, description, photo, confidentialité, classement ou membres de l’équipe), ces modifications à attribuer à votre via le pipeline d’audit.</span><span class="sxs-lookup"><span data-stu-id="3ff29-148">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="3ff29-149">Si vous effectuez des actions sur les paramètres spécifiques d’équipes, vos modifications seront suivies et attribuer aux vous dans le canal généraux de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3ff29-149">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="3ff29-150">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="3ff29-150">Learn more</span></span>

[<span data-ttu-id="3ff29-151">Référence d’applet de commande Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ff29-151">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="3ff29-152">Rôles d’administrateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ff29-152">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

