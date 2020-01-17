---
title: Gérer les packages de stratégie dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft Teams.
ms.openlocfilehash: 87fda86d1dbe09858c3850dc92ee5085666d8ba7
ms.sourcegitcommit: 52d924e654909a2017ce42ba9d1b4bbc3efa9262
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41205291"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="33466-103">Gérer les packages de stratégie dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="33466-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="33466-104">Un package de stratégie dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="33466-105">Nous avons conçu des packages de stratégie pour simplifier, rationaliser et garantir la cohérence lors de la gestion des stratégies pour les groupes d’utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="33466-106">Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres des stratégies du package en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="33466-107">Qu’est-ce qu’un package de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="33466-107">What is a policy package?</span></span>

<span data-ttu-id="33466-108">Les packages de stratégie vous permettent de contrôler les fonctionnalités d’équipes que vous souhaitez autoriser ou restreindre pour des ensembles de personnes spécifiques au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="33466-109">Chaque package de stratégie dans teams est conçu en fonction d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités de collaboration et de communication qui sont les plus typiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="33466-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="33466-110">Teams inclut actuellement les packages de stratégie suivants.</span><span class="sxs-lookup"><span data-stu-id="33466-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="33466-111">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="33466-111">**Package name**</span></span>  |<span data-ttu-id="33466-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="33466-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="33466-113">Éducation (étudiant de grande éducation)</span><span class="sxs-lookup"><span data-stu-id="33466-113">Education (Higher education student)</span></span>    |<span data-ttu-id="33466-114">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de plus grande éducation.</span><span class="sxs-lookup"><span data-stu-id="33466-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="33466-115">Éducation (étudiant primaire)</span><span class="sxs-lookup"><span data-stu-id="33466-115">Education (Primary school student)</span></span>   |<span data-ttu-id="33466-116">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants principaux.</span><span class="sxs-lookup"><span data-stu-id="33466-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="33466-117">Éducation (étudiant d’école secondaire)</span><span class="sxs-lookup"><span data-stu-id="33466-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="33466-118">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.</span><span class="sxs-lookup"><span data-stu-id="33466-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="33466-119">Éducation (enseignant)</span><span class="sxs-lookup"><span data-stu-id="33466-119">Education (Teacher)</span></span>    |<span data-ttu-id="33466-120">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="33466-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="33466-121">Voix professionnelle</span><span class="sxs-lookup"><span data-stu-id="33466-121">Business voice</span></span> |<span data-ttu-id="33466-122">Crée une stratégie de configuration d’application qui inclut les applications pour une interface vocale professionnelle.</span><span class="sxs-lookup"><span data-stu-id="33466-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="33466-123">Officier de sûreté public</span><span class="sxs-lookup"><span data-stu-id="33466-123">Public safety officer</span></span>   |<span data-ttu-id="33466-124">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-124">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="33466-125">Comme nous allons ajouter d’autres packages de stratégie dans les futures versions de teams, vous pouvez consulter les informations les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="33466-125">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="33466-126">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="33466-126">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="33466-127">Par exemple, lorsque vous attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="33466-127">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Capture d’écran du package de stratégie éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="33466-129">Utiliser des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="33466-129">How to use policy packages</span></span>

<span data-ttu-id="33466-130">Les plans suivants vous expliquent comment utiliser des packages de stratégie dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-130">The following outlines how to use policy packages in your organization.</span></span>

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- <span data-ttu-id="33466-132">**[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="33466-132">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="33466-133">Vérifiez que vous comprenez chaque paramètre et déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous devez les modifier de manière à ce qu’elles soient plus restrictives ou strictes en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-133">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="33466-134">Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pourrez pas modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="33466-134">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="33466-135">Une stratégie supprimée est à nouveau créée à l’aide des paramètres prédéfinis lorsque vous attribuez le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="33466-135">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="33466-136">**[Attribuer](#assign-a-policy-package)**: attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="33466-136">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="33466-137">N’oubliez pas que les stratégies d’un package de stratégie ne sont pas créées tant que vous n’avez pas affecté le package, vous pouvez modifier les paramètres des stratégies individuelles du package.</span><span class="sxs-lookup"><span data-stu-id="33466-137">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="33466-138">**[Personnaliser](#customize-policies-in-a-policy-package)**: Personnalisez les paramètres des stratégies dans le package de stratégie pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33466-138">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="33466-139">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="33466-139">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="33466-140">Voici les étapes à suivre pour afficher, attribuer et personnaliser des packages de stratégie dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33466-140">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="33466-141">Afficher les paramètres d’une stratégie dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="33466-141">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="33466-142">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **packages de stratégie**, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="33466-142">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="33466-143">Cliquez sur la stratégie que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="33466-143">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="33466-144">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="33466-144">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="33466-145">Assigner un package de stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="33466-145">Assign a policy package to one user</span></span>

1. <span data-ttu-id="33466-146">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="33466-146">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="33466-147">Sur la page de l’utilisateur, cliquez sur **stratégies**, puis en regard de **package de stratégie**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="33466-147">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="33466-148">Dans le volet **affecter un package de stratégie** , sélectionnez le package que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="33466-148">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="33466-149">Assigner un package de stratégie à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="33466-149">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="33466-150">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie**, puis sélectionnez le package de stratégie que vous voulez affecter en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="33466-150">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="33466-151">Cliquez sur **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="33466-151">Click **Manage users**.</span></span>
3. <span data-ttu-id="33466-152">Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="33466-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="33466-153">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="33466-153">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="33466-154">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="33466-154">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="33466-155">Personnaliser les stratégies dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="33466-155">Customize policies in a policy package</span></span>

<span data-ttu-id="33466-156">Vous pouvez modifier les paramètres d’une stratégie par le biais de la page **packages de stratégie** ou en accédant directement à la page de stratégie dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33466-156">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="33466-157">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="33466-157">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="33466-158">Cliquez sur **packages de stratégie**, puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="33466-158">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="33466-159">Cliquez sur le type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="33466-159">Click the policy type.</span></span>  <span data-ttu-id="33466-160">Par exemple, cliquez sur **stratégies de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="33466-160">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="33466-161">Cliquez sur la stratégie que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="33466-161">Click the policy you want to edit.</span></span> <span data-ttu-id="33466-162">Les stratégies liées à un package de stratégie portent le même nom que le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="33466-162">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="33466-163">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="33466-163">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="33466-164">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="33466-164">Troubleshooting</span></span>

<span data-ttu-id="33466-165">**Vous recevez un message d’erreur lorsque vous attribuez un package de stratégie**</span><span class="sxs-lookup"><span data-stu-id="33466-165">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="33466-166">Cela risque de se produire si une ou plusieurs stratégies du package n’ont pas été créées ou appliquées.</span><span class="sxs-lookup"><span data-stu-id="33466-166">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="33466-167">Réattribuez-le à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="33466-167">Reassign the policy package to your users.</span></span> <span data-ttu-id="33466-168">Le renouvellement de l’opération résout généralement ce problème.</span><span class="sxs-lookup"><span data-stu-id="33466-168">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33466-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33466-169">Related topics</span></span>

[<span data-ttu-id="33466-170">Packages de stratégie Microsoft Teams pour les administrateurs dans l’éducation</span><span class="sxs-lookup"><span data-stu-id="33466-170">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
