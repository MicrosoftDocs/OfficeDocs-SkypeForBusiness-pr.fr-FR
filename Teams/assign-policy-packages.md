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
ms.openlocfilehash: e70d5e2bf0db6cb7dfd93e35a8207fce61fa75fd
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796828"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="945ae-103">Attribuer des packages de stratégies à des utilisateurs et groupes</span><span class="sxs-lookup"><span data-stu-id="945ae-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="945ae-104">Cet article passe en revue les différentes manières d’attribuer des packages de stratégie aux utilisateurs et groupes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="945ae-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="945ae-105">Avant de lire, veillez à lire Attribuer des stratégies [Teams mise en place.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="945ae-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="945ae-106">Chaque utilisateur aura besoin du module de communication avancée pour recevoir une affectation de package de stratégie personnalisé.</span><span class="sxs-lookup"><span data-stu-id="945ae-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="945ae-107">Pour plus d’informations, [consultez le module complémentaire Communications avancées pour Microsoft Teams.](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="945ae-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="945ae-108">Attribuer un package de stratégies aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="945ae-108">Assign a policy package to users</span></span>

<span data-ttu-id="945ae-109">Un package de stratégie dans Teams est un ensemble de stratégies et paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles identiques ou similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="945ae-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="945ae-110">Chaque package de stratégie est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent des activités classiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="945ae-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="945ae-111">Le package Éducation (enseignant) et le package Soins de santé (travailleurs cliniques) sont quelques exemples de packages de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="945ae-112">Pour plus d’informations, [voir Gérer les packages de stratégie dans Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="945ae-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="945ae-113">Attribuer un package de stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="945ae-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="945ae-114">Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez Utilisateurs, puis l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="945ae-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="945ae-115">Dans la page de l’utilisateur, sélectionnez **Stratégies,** puis, à côté du **package** de stratégie, sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="945ae-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="945ae-116">Dans le **volet Attribuer un package** de stratégie, sélectionnez le package à attribuer, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="945ae-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams d’administration pour l’affectation d’un package de stratégie à un utilisateur](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="945ae-118">Attribuer un package de stratégie à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="945ae-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="945ae-119">Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Packages de **stratégie,** puis sélectionnez le package de stratégie à attribuer en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="945ae-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="945ae-120">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="945ae-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="945ae-121">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="945ae-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="945ae-122">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="945ae-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="945ae-123">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="945ae-123">When you're finished adding users, select **Save**.</span></span>

![Teams d’administration pour l’affectation d’un package de stratégie à plusieurs utilisateurs](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="945ae-125">Attribuer le package stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="945ae-125">Assign a policy package to a group</span></span>

<span data-ttu-id="945ae-126">Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="945ae-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="945ae-127">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="945ae-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="945ae-128">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="945ae-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="945ae-129">L’affectation de package de stratégie à des groupes est recommandée pour les groupes de jusqu’à 50 000 utilisateurs, mais elle fonctionne également avec les groupes plus importants.</span><span class="sxs-lookup"><span data-stu-id="945ae-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="945ae-130">Lorsque vous attribuez le package de stratégie, il est immédiatement affecté au groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="945ae-131">Toutefois, la propagation de l’affectation de stratégie aux membres du groupe est effectuée comme une opération en arrière-plan et peut prendre du temps, selon la taille du groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="945ae-132">Il en va de même lorsqu’une stratégie est non signée dans un groupe, ou lorsque des membres sont ajoutés ou supprimés d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="945ae-133">Avant de commencer, il est important de comprendre[(règles](assign-policies-users-and-groups.md#precedence-rules)de priorité) et[(classement d’affectation de groupe).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="945ae-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="945ae-134">Assurez-vous de lire et de comprendre les concepts dans[(ce](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)que vous devez savoir sur l’affectation de stratégie aux groupes) plus tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="945ae-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="945ae-135">Attribuer un package de stratégie à un groupe d’utilisateurs dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="945ae-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="945ae-136">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="945ae-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="945ae-137">Dans le dossier de navigation de gauche, allez à la page du package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="945ae-138">Sélectionnez l’onglet Affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="945ae-139">Sélectionnez **Ajouter un groupe,** puis dans le volet Affecter un package de stratégie au volet de groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="945ae-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="945ae-140">a.</span><span class="sxs-lookup"><span data-stu-id="945ae-140">a.</span></span> <span data-ttu-id="945ae-141">Recherchez et ajoutez le groupe à qui vous voulez affecter le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="945ae-142">b.</span><span class="sxs-lookup"><span data-stu-id="945ae-142">b.</span></span> <span data-ttu-id="945ae-143">Sélectionnez un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-143">Select a policy package.</span></span>

    <span data-ttu-id="945ae-144">c.</span><span class="sxs-lookup"><span data-stu-id="945ae-144">c.</span></span> <span data-ttu-id="945ae-145">Définissez le classement pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="945ae-146">d.</span><span class="sxs-lookup"><span data-stu-id="945ae-146">d.</span></span> <span data-ttu-id="945ae-147">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="945ae-147">Select **Apply**.</span></span>

![affiche l’affectation de stratégie de groupe](media/group-pkg-assignment.png)

5. <span data-ttu-id="945ae-149">Pour gérer le classement d’un type de stratégie spécifique, accédez à la page de stratégie spécifique.</span><span class="sxs-lookup"><span data-stu-id="945ae-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="945ae-150">Pour réattribuer un package de stratégie à un groupe, supprimez tout d’abord l’affectation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="945ae-151">Ensuite, suivez les étapes ci-dessus pour affecter le package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="945ae-152">Travailler avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="945ae-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="945ae-153">Obtenir le module PowerShell Teams’équipe</span><span class="sxs-lookup"><span data-stu-id="945ae-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="945ae-154">Pour obtenir des instructions pas à pas, voir [Installer Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="945ae-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="945ae-155">Affecter un package de stratégie à un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="945ae-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="945ae-156">Utilisez la [cmdlet Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) pour affecter un package de stratégie à un groupe.</span><span class="sxs-lookup"><span data-stu-id="945ae-156">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="945ae-157">Vous pouvez spécifier un groupe à l’aide de l’ID d’objet, de l’adresse SIP ou de l’adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="945ae-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="945ae-158">Lorsque vous attribuez le package de stratégie, spécifiez un ([classement d’affectation](assign-policies-users-and-groups.md#group-assignment-ranking)de groupe) pour chaque type de stratégie dans le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="945ae-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="945ae-159">Dans cet exemple, nous affectons le package de stratégie Education_Teacher à un groupe avec un classement d’affectations de 1 pour TeamsAppSetupPolicy et TeamsMeetingBroadcastPolicy et un classement de 2 pour TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="945ae-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="945ae-160">Affecter un package de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="945ae-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="945ae-161">L’affectation de package de stratégie de lot vous permet d’affecter un package de stratégie à de grands ensembles d’utilisateurs à la fois sans utiliser de script.</span><span class="sxs-lookup"><span data-stu-id="945ae-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="945ae-162">Vous utilisez la cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour envoyer un lot d’utilisateurs et le package de stratégie que vous souhaitez affecter.</span><span class="sxs-lookup"><span data-stu-id="945ae-162">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="945ae-163">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="945ae-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="945ae-164">Vous pouvez ensuite utiliser la cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre l’avancement et l’état des devoirs d’un lot.</span><span class="sxs-lookup"><span data-stu-id="945ae-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="945ae-165">Spécifiez les utilisateurs selon leur ID d’objet ou leur adresse SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="945ae-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="945ae-166">L’adresse SIP d’un utilisateur a souvent la même valeur que le nom d’utilisateur principal (UPN) ou l’adresse de courrier, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="945ae-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="945ae-167">Si un utilisateur est spécifié à l’aide de son nom d’utilisateur supérieur ou de son adresse de courrier, mais que sa valeur est différente de celle de son adresse SIP, l’attribution de stratégie échoue pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="945ae-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="945ae-168">Si un lot inclut des utilisateurs en double, les doublons sont supprimés du lot avant que le traitement et l’état ne soient fournis qu’aux utilisateurs uniques restants du lot.</span><span class="sxs-lookup"><span data-stu-id="945ae-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="945ae-169">Un lot contient jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="945ae-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="945ae-170">Pour de meilleurs résultats, n’envoyez pas plus de quelques lots à la fois.</span><span class="sxs-lookup"><span data-stu-id="945ae-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="945ae-171">Autorisez le traitement des lots avant l’envoi d’autres lots.</span><span class="sxs-lookup"><span data-stu-id="945ae-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="945ae-172">Utiliser le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="945ae-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="945ae-173">Exécutez la commande suivante pour installer [Microsoft Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si vous ne l’avez pas déjà fait).</span><span class="sxs-lookup"><span data-stu-id="945ae-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="945ae-174">Veillez à installer la version 1.0.5 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="945ae-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="945ae-175">Exécutez ce qui suit pour vous connecter Teams et démarrer une session.</span><span class="sxs-lookup"><span data-stu-id="945ae-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="945ae-176">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="945ae-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="945ae-177">Attribuer des packages de stratégie à un lot d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="945ae-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="945ae-178">Dans cet exemple, nous utilisons la cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour affecter le package de stratégie Education_PrimaryStudent à un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="945ae-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="945ae-179">Voir l’état d’une affectation de lot</span><span class="sxs-lookup"><span data-stu-id="945ae-179">See the status of a batch assignment</span></span>

<span data-ttu-id="945ae-180">Exécutez ce qui suit pour obtenir l’état d’une affectation de lot, où OperationId est l’ID d’opération renvoyé par ```New-CsBatchPolicyAssignmentOperation``` l’cmdlet pour un lot donné.</span><span class="sxs-lookup"><span data-stu-id="945ae-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="945ae-181">Si la sortie indique qu’une erreur s’est produite, exécutez l’erreur suivante pour obtenir plus d’informations sur les erreurs, qui se trouver dans la ```UserState``` propriété.</span><span class="sxs-lookup"><span data-stu-id="945ae-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="945ae-182">Pour en savoir plus, [consultez Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="945ae-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="945ae-183">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="945ae-183">Related topics</span></span>

- [<span data-ttu-id="945ae-184">Gérer les Teams des stratégies</span><span class="sxs-lookup"><span data-stu-id="945ae-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="945ae-185">Gérer les packages de stratégie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="945ae-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="945ae-186">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="945ae-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="945ae-187">Attribuer des stratégies dans Teams - mise en place</span><span class="sxs-lookup"><span data-stu-id="945ae-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
