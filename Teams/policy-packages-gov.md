---
title: Packages de stratégie Teams pour le gouvernement
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les packages de stratégie Teams pour votre organisation gouvernementale.
ms.openlocfilehash: 19e2c692f2b5109e3ef0915ced9fd2b68c56e482
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812884"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="94721-103">Packages de stratégie Teams pour le gouvernement</span><span class="sxs-lookup"><span data-stu-id="94721-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="94721-104">Les packages de stratégie ne sont actuellement pas disponibles dans les déploiements Microsoft 365 Government GCC High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="94721-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="94721-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="94721-105">Overview</span></span>

<span data-ttu-id="94721-106">Un [package de](manage-policy-packages.md) stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="94721-107">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="94721-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="94721-108">Vous pouvez personnaliser les paramètres des stratégies dans le package pour répondre aux besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94721-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="94721-109">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="94721-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="94721-110">Vous pouvez gérer des packages de stratégie à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94721-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="94721-111">Les packages de stratégie pré-définissent les stratégies suivantes, selon le package :</span><span class="sxs-lookup"><span data-stu-id="94721-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="94721-112">Messagerie</span><span class="sxs-lookup"><span data-stu-id="94721-112">Messaging</span></span>
- <span data-ttu-id="94721-113">Réunions</span><span class="sxs-lookup"><span data-stu-id="94721-113">Meetings</span></span>
- <span data-ttu-id="94721-114">Appel</span><span class="sxs-lookup"><span data-stu-id="94721-114">Calling</span></span>
- <span data-ttu-id="94721-115">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="94721-115">App setup</span></span>
- <span data-ttu-id="94721-116">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="94721-116">Live events</span></span>

<span data-ttu-id="94721-117">Teams inclut actuellement les packages de stratégie suivants pour le gouvernement.</span><span class="sxs-lookup"><span data-stu-id="94721-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="94721-118">Nom du package dans le Centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94721-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="94721-119">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="94721-119">Best used for</span></span>|<span data-ttu-id="94721-120">Description</span><span class="sxs-lookup"><span data-stu-id="94721-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="94721-121">Responsable de la sécurité publique</span><span class="sxs-lookup"><span data-stu-id="94721-121">Public safety officer</span></span>  |<span data-ttu-id="94721-122">Responsables de la sécurité publique dans votre organisation publique</span><span class="sxs-lookup"><span data-stu-id="94721-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="94721-123">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="94721-124">Gestionnaire de première ligne</span><span class="sxs-lookup"><span data-stu-id="94721-124">Firstline manager</span></span>  |<span data-ttu-id="94721-125">Responsables de première ligne dans votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="94721-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="94721-126">Crée un ensemble de stratégies et applique ces paramètres aux responsables de première ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="94721-127">Employé de première ligne</span><span class="sxs-lookup"><span data-stu-id="94721-127">Firstline worker</span></span>  |<span data-ttu-id="94721-128">Employés de première ligne dans votre organisation publique</span><span class="sxs-lookup"><span data-stu-id="94721-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="94721-129">Crée un ensemble de stratégies et applique ces paramètres aux employés de première ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Capture d’écran des packages de stratégies de santé](media/policy-packages-gov.png)

<span data-ttu-id="94721-131">Le nom du package de stratégies est donné à chaque stratégie individuelle, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="94721-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="94721-132">Par exemple, lorsque vous affectez le package de stratégie du responsable de la sécurité publique à des utilisateurs de votre organisation, une stratégie nommée PublicSafety_Officer est créée pour chaque stratégie du package.</span><span class="sxs-lookup"><span data-stu-id="94721-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Capture d’écran des stratégies dans le package pour les travailleurs médicaux](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="94721-134">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="94721-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="94721-135">Afficher</span><span class="sxs-lookup"><span data-stu-id="94721-135">View</span></span>

<span data-ttu-id="94721-136">Afficher les paramètres de chaque stratégie dans un package de stratégie avant d’attribuer un package.</span><span class="sxs-lookup"><span data-stu-id="94721-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="94721-137">Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="94721-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="94721-138">Déterminez si les valeurs prédéfinies conviennent à votre organisation ou si vous devez les personnaliser pour les rendre plus restrictives ou plus strictes en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="94721-139">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="94721-139">Customize</span></span>

<span data-ttu-id="94721-140">Personnalisez les paramètres des stratégies dans le package de stratégie, le cas échéant, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94721-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="94721-141">Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué.</span><span class="sxs-lookup"><span data-stu-id="94721-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="94721-142">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le Centre d’administration Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="94721-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="94721-143">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies dans un package une fois que vous avez affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="94721-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="94721-144">Pour plus d’informations, consultez [Personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="94721-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="94721-145">Attribuer</span><span class="sxs-lookup"><span data-stu-id="94721-145">Assign</span></span>

<span data-ttu-id="94721-146">Attribuer le package stratégie à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94721-146">Assign the policy package to users.</span></span> <span data-ttu-id="94721-147">Si une stratégie est attribuée à un utilisateur et que vous affectez une autre stratégie plus tard, l’affectation la plus récente prend la priorité.</span><span class="sxs-lookup"><span data-stu-id="94721-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="94721-148">Attribuer un package de stratégie à un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="94721-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="94721-149">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Packages de stratégie**, puis sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="94721-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Capture d’écran de l’attribution d’un package de stratégie dans le Centre d’administration](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="94721-151">Pour plus d’informations, consultez la section [Attribuer un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="94721-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="94721-152">Si une stratégie est attribuée à un utilisateur et que vous affectez une autre stratégie plus tard, l’affectation la plus récente prend la priorité.</span><span class="sxs-lookup"><span data-stu-id="94721-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="94721-153">Attribuer le package stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="94721-153">Assign a policy package to a group</span></span>

<span data-ttu-id="94721-154">**Cette fonctionnalité est en mode privé (préversion)**</span><span class="sxs-lookup"><span data-stu-id="94721-154">**This feature is in private preview**</span></span>

<span data-ttu-id="94721-155">Attribution de package de stratégie aux groupes vous permet d’attribuer plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="94721-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="94721-156">L’affectations de stratégie est propagée aux membres du groupe en fonction de règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="94721-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="94721-157">Lorsque les membres sont ajoutés à un groupe ou supprimés de ceux-ci, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="94721-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="94721-158">Cette méthode est recommandée pour les groupes disposant jusqu’à 50 000 utilisateurs, mais aussi pour les groupes de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="94721-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="94721-159">Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un groupe](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="94721-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="94721-160">Attribuer un package de stratégie à un grand ensemble (lot) d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="94721-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="94721-161">Utilisez l’attribution de package de stratégie de traitement par lots pour attribuer un package de stratégie à d’importants ensembles d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="94721-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="94721-162">L’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) vous permet de soumettre un lot d’utilisateurs et le package de stratégie que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="94721-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="94721-163">Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="94721-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="94721-164">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94721-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="94721-165">Vous pouvez spécifier des utilisateurs à l’aide de leur ID d’objet, de leur nom d’utilisateur, de leur adresse SIP ou de leur adresse de courrier.</span><span class="sxs-lookup"><span data-stu-id="94721-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="94721-166">Pour plus d’informations, consultez la section [Attribuer un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="94721-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="94721-167">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="94721-167">Related topics</span></span>

[<span data-ttu-id="94721-168">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="94721-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="94721-169">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="94721-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
