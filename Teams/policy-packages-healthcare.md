---
title: Packages de stratégie d’équipe pour la santé
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment utiliser et gérer des packages de stratégie d’équipe pour votre organisation de santé.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908513"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="4eb34-103">Packages de stratégie d’équipe pour la santé</span><span class="sxs-lookup"><span data-stu-id="4eb34-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="4eb34-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="4eb34-104">Overview</span></span>

<span data-ttu-id="4eb34-105">Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4eb34-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="4eb34-106">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="4eb34-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="4eb34-107">Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4eb34-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="4eb34-108">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="4eb34-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="4eb34-109">Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4eb34-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="4eb34-110">Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :</span><span class="sxs-lookup"><span data-stu-id="4eb34-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="4eb34-111">Messagerie</span><span class="sxs-lookup"><span data-stu-id="4eb34-111">Messaging</span></span>
- <span data-ttu-id="4eb34-112">Réunions</span><span class="sxs-lookup"><span data-stu-id="4eb34-112">Meetings</span></span>
- <span data-ttu-id="4eb34-113">Appel</span><span class="sxs-lookup"><span data-stu-id="4eb34-113">Calling</span></span>
- <span data-ttu-id="4eb34-114">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="4eb34-114">App setup</span></span>
- <span data-ttu-id="4eb34-115">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="4eb34-115">Live events</span></span>

<span data-ttu-id="4eb34-116">Teams inclut actuellement les packages de politique de santé suivants.</span><span class="sxs-lookup"><span data-stu-id="4eb34-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="4eb34-117">Nom du package dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4eb34-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="4eb34-118">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="4eb34-118">Best used for</span></span>|<span data-ttu-id="4eb34-119">Description</span><span class="sxs-lookup"><span data-stu-id="4eb34-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4eb34-120">Travailleurs cliniques médicaux</span><span class="sxs-lookup"><span data-stu-id="4eb34-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="4eb34-121">Travailleurs cliniques de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="4eb34-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="4eb34-122">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="4eb34-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="4eb34-123">Travailleurs de l’information sur la santé</span><span class="sxs-lookup"><span data-stu-id="4eb34-123">Healthcare information worker</span></span>  |<span data-ttu-id="4eb34-124">Travailleurs de l’information au sein de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="4eb34-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="4eb34-125">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="4eb34-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="4eb34-126">Salle de santé du patient</span><span class="sxs-lookup"><span data-stu-id="4eb34-126">Healthcare patient room</span></span>  |<span data-ttu-id="4eb34-127">Appareils de salle de patient</span><span class="sxs-lookup"><span data-stu-id="4eb34-127">Patient room devices</span></span>|<span data-ttu-id="4eb34-128">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de soins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4eb34-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Capture d’écran des packages de politique de santé](media/policy-packages-healthcare.png)

<span data-ttu-id="4eb34-130">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4eb34-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="4eb34-131">Par exemple, lorsque vous attribuez le package de stratégie de travailleur clinique de santé aux médecins au sein de votre organisation, une stratégie nommée Healthcare_ClinicalWorker est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="4eb34-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="4eb34-133">Découvrir les packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="4eb34-133">Get started with policy packages</span></span>

<span data-ttu-id="4eb34-134">Pour vous aider à prendre en main les packages de stratégie de santé, sur le concentrateur Microsoft Admin Center, sélectionnez **santé** , puis sélectionnez **affecter des paramètres de stratégie par rôle**.</span><span class="sxs-lookup"><span data-stu-id="4eb34-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="4eb34-135">Lorsque vous êtes prêt à commencer, déterminez les packages de stratégie auxquels vous souhaitez affecter des personnes à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4eb34-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="4eb34-136">Pour en savoir plus sur les stratégies spécifiques d’un package et leurs paramètres respectifs, sélectionnez **afficher les détails** de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4eb34-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="4eb34-137">Celles-ci [peuvent être personnalisées](manage-policy-packages.md#customize-policies-in-a-policy-package) après affectation dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="4eb34-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="4eb34-138">Sélectionnez un ou plusieurs packages à attribuer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4eb34-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="4eb34-139">Vous pouvez rechercher et ajouter des personnes au package de stratégie qui conviennent le mieux à leur rôle.</span><span class="sxs-lookup"><span data-stu-id="4eb34-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="4eb34-140">Un individu ne peut pas être attribué à plusieurs packages de stratégies en même temps.</span><span class="sxs-lookup"><span data-stu-id="4eb34-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="4eb34-141">Une fois que vous avez ajouté des personnes au package de stratégie approprié, **Terminer** finalise vos sélections.</span><span class="sxs-lookup"><span data-stu-id="4eb34-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="4eb34-142">Vous pouvez continuer à personnaliser et gérer des packages de stratégie dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4eb34-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="4eb34-143">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="4eb34-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="4eb34-144">Afficher</span><span class="sxs-lookup"><span data-stu-id="4eb34-144">View</span></span>

<span data-ttu-id="4eb34-145">Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="4eb34-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="4eb34-146">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie** , sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="4eb34-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="4eb34-147">Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4eb34-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="4eb34-148">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="4eb34-148">Customize</span></span>

<span data-ttu-id="4eb34-149">Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4eb34-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="4eb34-150">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="4eb34-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="4eb34-151">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie** , sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="4eb34-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="4eb34-152">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="4eb34-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="4eb34-153">Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="4eb34-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="4eb34-154">Assignation</span><span class="sxs-lookup"><span data-stu-id="4eb34-154">Assign</span></span>

<span data-ttu-id="4eb34-155">Attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4eb34-155">Assign the policy package to users.</span></span> <span data-ttu-id="4eb34-156">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4eb34-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="4eb34-157">Assigner un package de stratégie à un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4eb34-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="4eb34-158">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie** , puis **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4eb34-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="4eb34-160">Pour en savoir plus, voir [attribuer un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="4eb34-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="4eb34-161">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4eb34-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="4eb34-162">Assigner un package de stratégie à un groupe</span><span class="sxs-lookup"><span data-stu-id="4eb34-162">Assign a policy package to a group</span></span>

<span data-ttu-id="4eb34-163">**Cette fonctionnalité est en version préliminaire privée**</span><span class="sxs-lookup"><span data-stu-id="4eb34-163">**This feature is in private preview**</span></span>

<span data-ttu-id="4eb34-164">Attribution de package de stratégie aux groupes vous permettent d’affecter plusieurs stratégies à un groupe d’utilisateurs, tel qu’un groupe de sécurité ou une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="4eb34-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="4eb34-165">L’affectation de stratégie est propagée aux membres du groupe conformément aux règles de priorité.</span><span class="sxs-lookup"><span data-stu-id="4eb34-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4eb34-166">Les membres étant ajoutés ou supprimés d’un groupe, leurs affectations de stratégie héritées sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="4eb34-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="4eb34-167">Cette méthode est recommandée pour les groupes d’utilisateurs 50 000, mais fonctionne aussi avec des groupes de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="4eb34-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="4eb34-168">Pour en savoir plus, voir [attribuer un package de stratégie à un groupe](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="4eb34-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="4eb34-169">Assigner un package de stratégie à un grand jeu (lot) d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4eb34-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="4eb34-170">Utilisez une affectation de package de stratégie de lot pour assigner un package de stratégie à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="4eb34-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="4eb34-171">Vous utilisez l’applet de commande [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour transmettre un lot d’utilisateurs et le package de stratégie que vous voulez affecter.</span><span class="sxs-lookup"><span data-stu-id="4eb34-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="4eb34-172">Les affectations sont traitées en tant qu’opérations en arrière-plan et chaque lot est généré.</span><span class="sxs-lookup"><span data-stu-id="4eb34-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="4eb34-173">Un lot peut contenir jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4eb34-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="4eb34-174">Vous pouvez spécifier des utilisateurs en fonction de leur ID d’objet, de leur nom d’utilisateur principal, de leur adresse SIP ou de leur adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="4eb34-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="4eb34-175">Pour en savoir plus, voir [affecter un package de stratégie à un lot d’utilisateurs](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="4eb34-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4eb34-176">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="4eb34-176">Related topics</span></span>

[<span data-ttu-id="4eb34-177">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="4eb34-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="4eb34-178">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="4eb34-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
