---
title: Gérer les stratégies d’équipes dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’équipe dans votre organisation pour contrôler ce que les utilisateurs peuvent faire dans les équipes et les canaux.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: dc3d5fa4880f3255017b535657a4a32a51789c82
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836964"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="64fde-103">Gérer les stratégies d’équipes dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="64fde-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="64fde-104">En tant qu’administrateur, vous pouvez utiliser les stratégies d’équipe de Microsoft teams pour contrôler ce que peuvent faire les utilisateurs de votre organisation dans les équipes et les canaux.</span><span class="sxs-lookup"><span data-stu-id="64fde-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="64fde-105">Par exemple, vous pouvez définir si les utilisateurs sont autorisés à découvrir des équipes privées dans les résultats de la recherche et dans la Galerie d’équipes et si les utilisateurs sont autorisés à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="64fde-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="64fde-106">Pour gérer les stratégies d’équipe, **accédez à** > **stratégies** teams teams dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64fde-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="64fde-107">Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer des stratégies personnalisées et les affecter à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="64fde-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="64fde-108">Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="64fde-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="64fde-109">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="64fde-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="64fde-110">Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64fde-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="64fde-111">Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64fde-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="64fde-112">Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="64fde-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="64fde-113">Créer une stratégie d’équipe personnalisée</span><span class="sxs-lookup"><span data-stu-id="64fde-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="64fde-114">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.</span><span class="sxs-lookup"><span data-stu-id="64fde-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="64fde-115">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="64fde-115">Click **Add**.</span></span>
3. <span data-ttu-id="64fde-116">Entrez le nom et la description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="64fde-116">Enter a name and description for the policy.</span></span>

    ![Capture d’écran des paramètres de stratégie d’équipe](media/teams-policies.png)
4. <span data-ttu-id="64fde-118">Choisissez les paramètres de votre choix :</span><span class="sxs-lookup"><span data-stu-id="64fde-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="64fde-119">**Découvrir les équipes privées**:<a name="discoverteams"> </a> activez ce paramètre pour autoriser les utilisateurs à découvrir les équipes privées dans les résultats de la recherche et dans la Galerie d’équipes.</span><span class="sxs-lookup"><span data-stu-id="64fde-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="64fde-120">**Créer des canaux privés**: <a name="createchannels"> </a>activez ce paramètre pour autoriser les utilisateurs à créer des canaux privés.</span><span class="sxs-lookup"><span data-stu-id="64fde-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="64fde-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64fde-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="64fde-122">Modifier une stratégie d’équipe</span><span class="sxs-lookup"><span data-stu-id="64fde-122">Edit a teams policy</span></span>

<span data-ttu-id="64fde-123">Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="64fde-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="64fde-124">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.</span><span class="sxs-lookup"><span data-stu-id="64fde-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="64fde-125">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="64fde-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="64fde-126">Activez ou désactivez les paramètres souhaités, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64fde-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="64fde-127">Attribuer une stratégie d’équipe personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="64fde-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="64fde-128">Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="64fde-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="64fde-129">Attribuer une stratégie d’équipe personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="64fde-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="64fde-130">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64fde-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="64fde-131">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="64fde-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="64fde-132">Sous **stratégies d’équipe**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64fde-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="64fde-133">Pour attribuer une stratégie d’équipe personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="64fde-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="64fde-134">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="64fde-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="64fde-135">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.</span><span class="sxs-lookup"><span data-stu-id="64fde-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="64fde-136">Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="64fde-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="64fde-137">Sélectionnez **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="64fde-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="64fde-138">Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="64fde-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="64fde-139">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="64fde-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="64fde-140">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64fde-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="64fde-141">Attribuer une stratégie d’équipe personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="64fde-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="64fde-142">Vous pouvez assigner une stratégie d’équipe personnalisée à plusieurs utilisateurs que vous avez déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="64fde-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="64fde-143">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="64fde-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="64fde-144">Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="64fde-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="64fde-145">Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="64fde-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="64fde-146">Dans cet exemple, nous affectons une stratégie équipes appelée politique équipes marketing à tous les utilisateurs du groupe marketing de contoso.</span><span class="sxs-lookup"><span data-stu-id="64fde-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="64fde-147">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="64fde-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="64fde-148">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="64fde-148">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="64fde-149">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="64fde-149">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="64fde-150">Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière.</span><span class="sxs-lookup"><span data-stu-id="64fde-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="64fde-151">Dans cet exemple, il s’agit de la stratégie d’équipes marketing.</span><span class="sxs-lookup"><span data-stu-id="64fde-151">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="64fde-152">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="64fde-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64fde-153">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="64fde-153">Related topics</span></span>

- [<span data-ttu-id="64fde-154">Gérer la découverte des équipes privées dans Teams</span><span class="sxs-lookup"><span data-stu-id="64fde-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="64fde-155">Canaux privés dans teams</span><span class="sxs-lookup"><span data-stu-id="64fde-155">Private channels in Teams</span></span>](private-channels.md)
