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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft teams pour simplifier, simplifier et garantir la cohérence lors de la gestion des stratégies pour les groupes d’utilisateurs.
ms.openlocfilehash: 752995cb31fa1588420b31e8927ce95ad4b52dc0
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43945581"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="6d1f0-103">Gérer les packages de stratégie dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6d1f0-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="6d1f0-104">Un package de stratégie dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="6d1f0-105">Nous avons conçu des packages de stratégie pour simplifier, rationaliser et garantir la cohérence lors de la gestion des stratégies pour les groupes d’utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="6d1f0-106">Lorsque vous attribuez un package de stratégie aux utilisateurs, les stratégies du package sont créées et vous pouvez personnaliser les paramètres des stratégies du package en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="6d1f0-107">Les packages de stratégie ne sont pas disponibles pour les organisations américaines de la communauté Cloud.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="6d1f0-108">Qu’est-ce qu’un package de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="6d1f0-108">What is a policy package?</span></span>

<span data-ttu-id="6d1f0-109">Les packages de stratégie vous permettent de contrôler les fonctionnalités d’équipes que vous souhaitez autoriser ou restreindre pour des ensembles de personnes spécifiques au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="6d1f0-110">Chaque package de stratégie dans teams est conçu en fonction d’un rôle d’utilisateur et comprend des stratégies et des paramètres de stratégie prédéfinis qui prennent en charge les activités de collaboration et de communication qui sont les plus typiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="6d1f0-111">Teams inclut actuellement les packages de stratégie suivants.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="6d1f0-112">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="6d1f0-112">**Package name**</span></span>  |<span data-ttu-id="6d1f0-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="6d1f0-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="6d1f0-114">Éducation (étudiant de grande éducation)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-114">Education (Higher education student)</span></span>    |<span data-ttu-id="6d1f0-115">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de plus grande éducation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="6d1f0-116">Éducation (étudiant primaire)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-116">Education (Primary school student)</span></span>   |<span data-ttu-id="6d1f0-117">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants principaux.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="6d1f0-118">Éducation (étudiant d’école secondaire)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="6d1f0-119">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="6d1f0-120">Éducation (enseignant)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-120">Education (Teacher)</span></span>    |<span data-ttu-id="6d1f0-121">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="6d1f0-122">Travailleurs cliniques médicaux</span><span class="sxs-lookup"><span data-stu-id="6d1f0-122">Healthcare clinical worker</span></span>  |<span data-ttu-id="6d1f0-123">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="6d1f0-124">Travailleurs de l’information sur la santé</span><span class="sxs-lookup"><span data-stu-id="6d1f0-124">Healthcare information worker</span></span>  |<span data-ttu-id="6d1f0-125">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="6d1f0-126">Utilisateurs petites et moyennes entreprises (voix entreprise)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-126">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="6d1f0-127">Crée une stratégie de configuration d’application qui inclut les applications pour une interface vocale professionnelle.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-127">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="6d1f0-128">Utilisateurs petites et moyennes entreprises (sans voix entreprise)</span><span class="sxs-lookup"><span data-stu-id="6d1f0-128">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="6d1f0-129">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux utilisateurs professionnels de petites et moyennes tailles sans fonctions vocales métiers.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-129">Creates a set of policies and policy settings that apply to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="6d1f0-130">Officier de sûreté public</span><span class="sxs-lookup"><span data-stu-id="6d1f0-130">Public safety officer</span></span>   |<span data-ttu-id="6d1f0-131">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-131">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|



> [!NOTE]
> <span data-ttu-id="6d1f0-132">Comme nous allons ajouter d’autres packages de stratégie dans les futures versions de teams, vous pouvez consulter les informations les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-132">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="6d1f0-133">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-133">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="6d1f0-134">Par exemple, lorsque vous attribuez le package de stratégie éducation (enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-134">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Capture d’écran du package de stratégie éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="6d1f0-136">Utiliser des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="6d1f0-136">How to use policy packages</span></span>

<span data-ttu-id="6d1f0-137">Les plans suivants vous expliquent comment utiliser des packages de stratégie dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-137">The following outlines how to use policy packages in your organization.</span></span>

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- <span data-ttu-id="6d1f0-139">**[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-139">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="6d1f0-140">Vérifiez que vous comprenez chaque paramètre et déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous devez les modifier de manière à ce qu’elles soient plus restrictives ou strictes en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-140">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="6d1f0-141">Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pourrez pas modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-141">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="6d1f0-142">Une stratégie supprimée est à nouveau créée à l’aide des paramètres prédéfinis lorsque vous attribuez le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-142">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="6d1f0-143">**[Attribuer](#assign-a-policy-package)**: attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-143">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="6d1f0-144">N’oubliez pas que les stratégies d’un package de stratégie ne sont pas créées tant que vous n’avez pas affecté le package, vous pouvez modifier les paramètres des stratégies individuelles du package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-144">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="6d1f0-145">**[Personnaliser](#customize-policies-in-a-policy-package)**: Personnalisez les paramètres des stratégies dans le package de stratégie pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-145">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="6d1f0-146">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-146">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="6d1f0-147">Voici les étapes à suivre pour afficher, attribuer et personnaliser des packages de stratégie dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-147">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="6d1f0-148">Afficher les paramètres d’une stratégie dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="6d1f0-148">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="6d1f0-149">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **packages de stratégie**, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-149">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="6d1f0-150">Cliquez sur la stratégie que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-150">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="6d1f0-151">Assigner un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="6d1f0-151">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="6d1f0-152">Assigner un package de stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d1f0-152">Assign a policy package to one user</span></span>

1. <span data-ttu-id="6d1f0-153">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6d1f0-154">Sur la page de l’utilisateur, cliquez sur **stratégies**, puis en regard de **package de stratégie**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-154">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="6d1f0-155">Dans le volet **affecter un package de stratégie** , sélectionnez le package que vous voulez attribuer, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-155">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="6d1f0-156">Assigner un package de stratégie à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6d1f0-156">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="6d1f0-157">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **packages de stratégie**, puis sélectionnez le package de stratégie que vous voulez affecter en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-157">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="6d1f0-158">Cliquez sur **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-158">Click **Manage users**.</span></span>
3. <span data-ttu-id="6d1f0-159">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-159">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="6d1f0-160">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-160">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="6d1f0-161">Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-161">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="6d1f0-162">Personnaliser les stratégies dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="6d1f0-162">Customize policies in a policy package</span></span>

<span data-ttu-id="6d1f0-163">Vous pouvez modifier les paramètres d’une stratégie par le biais de la page **packages de stratégie** ou en accédant directement à la page de stratégie dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-163">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="6d1f0-164">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d1f0-164">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="6d1f0-165">Cliquez sur **packages de stratégie**, puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-165">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="6d1f0-166">Cliquez sur le type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-166">Click the policy type.</span></span>  <span data-ttu-id="6d1f0-167">Par exemple, cliquez sur **stratégies de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-167">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="6d1f0-168">Cliquez sur la stratégie que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-168">Click the policy you want to edit.</span></span> <span data-ttu-id="6d1f0-169">Les stratégies liées à un package de stratégie portent le même nom que le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-169">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="6d1f0-170">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-170">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6d1f0-171">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="6d1f0-171">Troubleshooting</span></span>

<span data-ttu-id="6d1f0-172">**Vous recevez un message d’erreur lorsque vous attribuez un package de stratégie**</span><span class="sxs-lookup"><span data-stu-id="6d1f0-172">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="6d1f0-173">Cela risque de se produire si une ou plusieurs stratégies du package n’ont pas été créées ou appliquées.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-173">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="6d1f0-174">Réattribuez-le à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-174">Reassign the policy package to your users.</span></span> <span data-ttu-id="6d1f0-175">Le renouvellement de l’opération résout généralement ce problème.</span><span class="sxs-lookup"><span data-stu-id="6d1f0-175">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d1f0-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d1f0-176">Related topics</span></span>

[<span data-ttu-id="6d1f0-177">Packages de stratégie Microsoft Teams pour les administrateurs dans l’éducation</span><span class="sxs-lookup"><span data-stu-id="6d1f0-177">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
