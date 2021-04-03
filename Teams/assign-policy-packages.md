---
title: Attribuer des packages de stratégies à des utilisateurs et groupes
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
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
description: Découvrez les différentes façons d’attribuer des packages de stratégie aux utilisateurs et groupes dans Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574316"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="6144f-103">Attribuer des packages de stratégies à des utilisateurs et groupes</span><span class="sxs-lookup"><span data-stu-id="6144f-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="6144f-104">Cet article passe en revue les différentes façons d’attribuer des packages de stratégie aux utilisateurs et groupes dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6144f-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="6144f-105">Avant de lire, assurez-vous de lire Attribuer [des stratégies dans Teams.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6144f-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="6144f-106">Attribuer un package de stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6144f-106">Assign a policy package to users</span></span>

<span data-ttu-id="6144f-107">Un package de stratégie dans Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles identiques ou similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6144f-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="6144f-108">Chaque package de stratégie est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent des activités classiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="6144f-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="6144f-109">Le package Éducation (enseignant) et le package Soins de santé (travailleurs cliniques) sont quelques exemples de packages de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="6144f-110">Pour en savoir plus, [consultez Gérer les packages de stratégie dans Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="6144f-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="6144f-111">Attribuer un package de stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6144f-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="6144f-112">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Utilisateurs, puis l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6144f-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="6144f-113">Dans la page de l’utilisateur, sélectionnez **Stratégies,** puis, à côté du **package** de stratégie, sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="6144f-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="6144f-114">Dans le **volet Attribuer un package** de stratégie, sélectionnez le package à attribuer, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="6144f-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Capture d’écran du Centre d’administration Teams pour l’affectation d’un package de stratégie à un utilisateur](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="6144f-116">Attribuer un package de stratégie à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6144f-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="6144f-117">Dans la navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis sélectionnez le package de stratégie à attribuer en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="6144f-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="6144f-118">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6144f-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="6144f-119">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6144f-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6144f-120">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="6144f-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="6144f-121">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="6144f-121">When you're finished adding users, select **Save**.</span></span>

![Capture d’écran du Centre d’administration Teams pour l’affectation d’un package de stratégie à plusieurs utilisateurs](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="6144f-123">Attribuer le package stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="6144f-123">Assign a policy package to a group</span></span>

<span data-ttu-id="6144f-124">Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="6144f-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="6144f-125">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="6144f-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6144f-126">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="6144f-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="6144f-127">L’affectation de package de stratégie à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec les groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="6144f-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="6144f-128">Lorsque vous attribuez le package de stratégie, il est immédiatement affecté au groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="6144f-129">Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="6144f-130">Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6144f-131">Avant de commencer, il est important de comprendre[(règles](assign-policies-users-and-groups.md#precedence-rules)de priorité) et[(classement d’affectation de groupe).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="6144f-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="6144f-132">Assurez-vous de lire et de comprendre les concepts dans[(ce](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)que vous devez savoir sur l’affectation de stratégie aux groupes) plus tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6144f-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="6144f-133">Attribuer un package de stratégie à un groupe d’utilisateurs dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="6144f-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="6144f-134">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6144f-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="6144f-135">Dans le dossier de navigation de gauche, allez à la page du package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="6144f-136">Sélectionnez l’onglet Affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="6144f-137">Sélectionnez **Ajouter un groupe,** puis dans le volet Affecter un package de stratégie au volet de groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="6144f-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="6144f-138">a.</span><span class="sxs-lookup"><span data-stu-id="6144f-138">a.</span></span> <span data-ttu-id="6144f-139">Recherchez et ajoutez le groupe à qui vous voulez affecter le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="6144f-140">b.</span><span class="sxs-lookup"><span data-stu-id="6144f-140">b.</span></span> <span data-ttu-id="6144f-141">Sélectionnez un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-141">Select a policy package.</span></span>

    <span data-ttu-id="6144f-142">c.</span><span class="sxs-lookup"><span data-stu-id="6144f-142">c.</span></span> <span data-ttu-id="6144f-143">Définissez le classement pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="6144f-144">d.</span><span class="sxs-lookup"><span data-stu-id="6144f-144">d.</span></span> <span data-ttu-id="6144f-145">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="6144f-145">Select **Apply**.</span></span>

![affiche l’affectation de stratégie de groupe](media/group-pkg-assignment.png)

5. <span data-ttu-id="6144f-147">Pour gérer le classement d’un type de stratégie spécifique, accédez à la page de stratégie spécifique.</span><span class="sxs-lookup"><span data-stu-id="6144f-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="6144f-148">Pour réattribuer un package de stratégie à un groupe, supprimez tout d’abord l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="6144f-149">Ensuite, suivez les étapes ci-dessus pour affecter le package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="6144f-150">Travailler avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="6144f-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="6144f-151">Obtenir le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6144f-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="6144f-152">Pour obtenir une aide étape par étape, voir [Installer Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="6144f-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="6144f-153">Affecter un package de stratégie à un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6144f-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="6144f-154">Utilisez la [cmdlet Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) pour affecter un package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="6144f-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="6144f-155">Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="6144f-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="6144f-156">Lorsque vous attribuez le package de stratégie, spécifiez un ([classement d’affectation](assign-policies-users-and-groups.md#group-assignment-ranking)de groupe) pour chaque type de stratégie dans le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6144f-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="6144f-157">Dans cet exemple, nous affectons le package de stratégie Education_Teacher à un groupe avec un classement d’affectations de 1 pour TeamsAppSetupPolicy et TeamsMeetingBroadcastPolicy et un classement de 2 pour TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="6144f-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="6144f-158">Affecter un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6144f-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="6144f-159">L’affectation de package de stratégie de lot vous permet d’affecter un package de stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="6144f-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="6144f-160">Vous utilisez la cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et le package de stratégie que vous souhaitez affecter.</span><span class="sxs-lookup"><span data-stu-id="6144f-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="6144f-161">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="6144f-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="6144f-162">Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="6144f-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="6144f-163">Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="6144f-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="6144f-164">L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6144f-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="6144f-165">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6144f-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="6144f-166">Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.</span><span class="sxs-lookup"><span data-stu-id="6144f-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="6144f-167">Un lot contient jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6144f-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="6144f-168">Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="6144f-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="6144f-169">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="6144f-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="6144f-170">Utiliser le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6144f-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="6144f-171">Exécutez la commande suivante pour installer [le module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="6144f-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="6144f-172">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="6144f-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6144f-173">Exécutez ce qui suit pour vous connecter à Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="6144f-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6144f-174">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6144f-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="6144f-175">Attribuer des packages de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6144f-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="6144f-176">Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter le package de stratégie Education_PrimaryStudent à un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6144f-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="6144f-177">Voir l’état d’une affectation de lot</span><span class="sxs-lookup"><span data-stu-id="6144f-177">See the status of a batch assignment</span></span>

<span data-ttu-id="6144f-178">Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par ```New-CsBatchPolicyAssignmentOperation``` l’cmdlet pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="6144f-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="6144f-179">Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="6144f-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="6144f-180">Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="6144f-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6144f-181">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6144f-181">Related topics</span></span>

- [<span data-ttu-id="6144f-182">Gérer Teams avec des stratégies</span><span class="sxs-lookup"><span data-stu-id="6144f-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="6144f-183">Gérer les packages de stratégie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6144f-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="6144f-184">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6144f-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6144f-185">Attribuer des stratégies dans Teams - Mise en place</span><span class="sxs-lookup"><span data-stu-id="6144f-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)