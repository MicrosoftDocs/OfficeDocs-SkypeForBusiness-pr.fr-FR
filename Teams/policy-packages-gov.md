---
title: Packages de stratégie d’équipes pour le secteur public
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser et gérer des packages de stratégie d’équipe pour votre organisation gouvernementale.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908593"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="79816-103">Packages de stratégie d’équipes pour le secteur public</span><span class="sxs-lookup"><span data-stu-id="79816-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="79816-104">Pour le moment, les packages de stratégie ne sont pas disponibles dans les déploiements Microsoft 365 Government High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="79816-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="79816-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="79816-105">Overview</span></span>

<span data-ttu-id="79816-106">Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="79816-107">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="79816-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="79816-108">Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79816-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="79816-109">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="79816-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="79816-110">Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79816-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="79816-111">Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :</span><span class="sxs-lookup"><span data-stu-id="79816-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="79816-112">Messagerie</span><span class="sxs-lookup"><span data-stu-id="79816-112">Messaging</span></span>
- <span data-ttu-id="79816-113">Réunions</span><span class="sxs-lookup"><span data-stu-id="79816-113">Meetings</span></span>
- <span data-ttu-id="79816-114">Appel</span><span class="sxs-lookup"><span data-stu-id="79816-114">Calling</span></span>
- <span data-ttu-id="79816-115">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="79816-115">App setup</span></span>
- <span data-ttu-id="79816-116">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="79816-116">Live events</span></span>

<span data-ttu-id="79816-117">Teams inclut actuellement les packages de stratégie suivants pour le gouvernement.</span><span class="sxs-lookup"><span data-stu-id="79816-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="79816-118">Nom du package dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="79816-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="79816-119">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="79816-119">Best used for</span></span>|<span data-ttu-id="79816-120">Description</span><span class="sxs-lookup"><span data-stu-id="79816-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="79816-121">Officier de sûreté public</span><span class="sxs-lookup"><span data-stu-id="79816-121">Public safety officer</span></span>  |<span data-ttu-id="79816-122">Fonctionnaires de la sécurité publique au sein de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="79816-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="79816-123">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="79816-124">Gestionnaire de terrain</span><span class="sxs-lookup"><span data-stu-id="79816-124">Firstline manager</span></span>  |<span data-ttu-id="79816-125">Responsables terrain au sein de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="79816-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="79816-126">Crée un ensemble de stratégies et applique ces paramètres aux responsables terrain de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="79816-127">Collaborateur terrain</span><span class="sxs-lookup"><span data-stu-id="79816-127">Firstline worker</span></span>  |<span data-ttu-id="79816-128">Terrain travailleurs de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="79816-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="79816-129">Crée un ensemble de stratégies et applique ces paramètres aux travailleurs terrain au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Capture d’écran des packages de politique de santé](media/policy-packages-gov.png)

<span data-ttu-id="79816-131">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="79816-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="79816-132">Par exemple, lorsque vous attribuez le package de stratégie de l’officier de sécurité public aux utilisateurs de votre organisation, une stratégie nommée PublicSafety_Officer est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="79816-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="79816-134">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="79816-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="79816-135">Afficher</span><span class="sxs-lookup"><span data-stu-id="79816-135">View</span></span>

<span data-ttu-id="79816-136">Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="79816-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="79816-137">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie** , sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="79816-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="79816-138">Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="79816-139">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="79816-139">Customize</span></span>

<span data-ttu-id="79816-140">Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79816-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="79816-141">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="79816-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="79816-142">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="79816-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="79816-143">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="79816-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="79816-144">Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="79816-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="79816-145">Assignation</span><span class="sxs-lookup"><span data-stu-id="79816-145">Assign</span></span>

<span data-ttu-id="79816-146">Attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79816-146">Assign the policy package to users.</span></span> <span data-ttu-id="79816-147">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="79816-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="79816-148">Assigner un package de stratégie à un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="79816-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="79816-149">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie** , puis **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="79816-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="79816-151">Pour en savoir plus, voir [attribuer un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="79816-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="79816-152">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="79816-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="79816-153">Assigner un package de stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="79816-153">Assign a policy package to a group</span></span>

<span data-ttu-id="79816-154">**Cette fonctionnalité est en version préliminaire privée**</span><span class="sxs-lookup"><span data-stu-id="79816-154">**This feature is in private preview**</span></span>

<span data-ttu-id="79816-155">Attribution de package de stratégie aux groupes vous permettent d’affecter plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="79816-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="79816-156">L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="79816-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="79816-157">Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="79816-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="79816-158">Cette méthode est recommandée pour les groupes d’utilisateurs 50 000, mais fonctionne aussi avec des groupes de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="79816-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="79816-159">Pour en savoir plus, voir [attribuer un package de stratégie à un groupe](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="79816-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="79816-160">Assigner un package de stratégie à un grand jeu (lot) d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="79816-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="79816-161">Utilisez une affectation de package de stratégie de lot pour assigner un package de stratégie à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="79816-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="79816-162">Vous utilisez l’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="79816-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="79816-163">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="79816-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="79816-164">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79816-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="79816-165">Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet, de leur nom d’utilisateur principal, de leur adresse SIP ou de leur adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="79816-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="79816-166">Pour en savoir plus, voir [affecter un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="79816-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="79816-167">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="79816-167">Related topics</span></span>

[<span data-ttu-id="79816-168">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="79816-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="79816-169">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="79816-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
