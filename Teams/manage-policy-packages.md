---
title: Gérer les packages de stratégie dans Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Découvrez comment utiliser et gérer des packages de stratégies dans Microsoft Teams pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d'utilisateurs.
ms.openlocfilehash: 1173f5a626d6ea559dadd75149a0517f515d821b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51699319"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="3106b-103">Gérer les packages de stratégie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3106b-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="3106b-104">Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="3106b-105">Nous avons créé des packages de stratégies pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d'utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="3106b-106">Vous pouvez utiliser les [packages de stratégie inclus dans Teams](#policy-packages-included-in-teams) ou créer vos propres [packages de stratégie personnalisés.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="3106b-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Capture d'écran de la page Packages de stratégie dans le Centre d'administration":::

<span data-ttu-id="3106b-108">Vous pouvez personnaliser les paramètres des stratégies dans un package de stratégies pour répondre aux besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3106b-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="3106b-109">Lorsque vous modifiez les paramètres des stratégies dans un package, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="3106b-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="3106b-110">Vous gérez les packages de stratégie à l'aide du Centre d'administration Microsoft Teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3106b-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="3106b-111">Qu'est-ce qu'un package de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="3106b-111">What is a policy package?</span></span>

<span data-ttu-id="3106b-112">Les packages de stratégie vous permettent de contrôler les fonctionnalités Teams que vous voulez autoriser ou restreindre pour des ensembles spécifiques de personnes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-112">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="3106b-113">Chaque package de stratégie dans Teams est conçu autour d'un rôle d'utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent les activités de collaboration et de communication classiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="3106b-113">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="3106b-114">Les packages de stratégies prisent en charge les types de stratégies Teams suivants :</span><span class="sxs-lookup"><span data-stu-id="3106b-114">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="3106b-115">Stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="3106b-115">Messaging policy</span></span>
- <span data-ttu-id="3106b-116">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="3106b-116">Meeting policy</span></span>
- <span data-ttu-id="3106b-117">Stratégie de configuration de l'application</span><span class="sxs-lookup"><span data-stu-id="3106b-117">App setup policy</span></span>
- <span data-ttu-id="3106b-118">Stratégie d’Appel</span><span class="sxs-lookup"><span data-stu-id="3106b-118">Calling policy</span></span>
- <span data-ttu-id="3106b-119">Stratégie d’événements en direct</span><span class="sxs-lookup"><span data-stu-id="3106b-119">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="3106b-120">Packages de stratégie inclus dans Teams</span><span class="sxs-lookup"><span data-stu-id="3106b-120">Policy packages included in Teams</span></span>

<span data-ttu-id="3106b-121">Teams inclut actuellement les packages de stratégie suivants.</span><span class="sxs-lookup"><span data-stu-id="3106b-121">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="3106b-122">Nom du package</span><span class="sxs-lookup"><span data-stu-id="3106b-122">Package name</span></span> | <span data-ttu-id="3106b-123">Description</span><span class="sxs-lookup"><span data-stu-id="3106b-123">Description</span></span> |
|---------|---------|
|<span data-ttu-id="3106b-124">Éducation (étudiant de l'enseignement supérieur)</span><span class="sxs-lookup"><span data-stu-id="3106b-124">Education (Higher education student)</span></span>    |<span data-ttu-id="3106b-125">Crée un ensemble de stratégies et de paramètres de stratégie qui s'appliquent aux étudiants de l'enseignement supérieur.</span><span class="sxs-lookup"><span data-stu-id="3106b-125">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="3106b-126">Éducation (étudiant du primaire)</span><span class="sxs-lookup"><span data-stu-id="3106b-126">Education (Primary school student)</span></span>   |<span data-ttu-id="3106b-127">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants du primaire.</span><span class="sxs-lookup"><span data-stu-id="3106b-127">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="3106b-128">Éducation (étudiant de l’enseignement secondaire)</span><span class="sxs-lookup"><span data-stu-id="3106b-128">Education (Secondary school student)</span></span>    |<span data-ttu-id="3106b-129">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.</span><span class="sxs-lookup"><span data-stu-id="3106b-129">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="3106b-130">Éducation (enseignant)</span><span class="sxs-lookup"><span data-stu-id="3106b-130">Education (Teacher)</span></span>    |<span data-ttu-id="3106b-131">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="3106b-131">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="3106b-132">Éducation (enseignant du primaire utilisant l’apprentissage à distance)</span><span class="sxs-lookup"><span data-stu-id="3106b-132">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="3106b-133">Création d’un groupe de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.</span><span class="sxs-lookup"><span data-stu-id="3106b-133">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3106b-134">Éducation (étudiant du primaire à l’aide de l’apprentissage à distance)</span><span class="sxs-lookup"><span data-stu-id="3106b-134">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="3106b-135">Création d’un groupe de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.</span><span class="sxs-lookup"><span data-stu-id="3106b-135">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3106b-136">Gestionnaire en ligne</span><span class="sxs-lookup"><span data-stu-id="3106b-136">Frontline manager</span></span> |<span data-ttu-id="3106b-137">Crée un ensemble de stratégies et applique ces paramètres aux responsables en ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-137">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="3106b-138">Employé en ligne</span><span class="sxs-lookup"><span data-stu-id="3106b-138">Frontline worker</span></span> |<span data-ttu-id="3106b-139">Crée un ensemble de stratégies et applique ces paramètres aux employés de votre organisation en ligne.</span><span class="sxs-lookup"><span data-stu-id="3106b-139">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="3106b-140">Professionnel de la santé</span><span class="sxs-lookup"><span data-stu-id="3106b-140">Healthcare clinical worker</span></span>  |<span data-ttu-id="3106b-141">Crée un ensemble de stratégies et de paramètres de stratégies qui offrent aux travailleurs cliniques tels que les infirmières autorisées, les infirmières responsables, les médecins et les travailleurs sociaux un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="3106b-141">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="3106b-142">Travailleurs de l’information sur le secteur de la santé</span><span class="sxs-lookup"><span data-stu-id="3106b-142">Healthcare information worker</span></span>  |<span data-ttu-id="3106b-143">Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’information, par exemple, le personnel de l’information, l’informatique, le personnel financier et les responsables de la mise en conformité, un accès total aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="3106b-143">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="3106b-144">Salle de soins de santé</span><span class="sxs-lookup"><span data-stu-id="3106b-144">Healthcare patient room</span></span>  |<span data-ttu-id="3106b-145">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles des patients dans votre organisation de santé.</span><span class="sxs-lookup"><span data-stu-id="3106b-145">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="3106b-146">Petite et moyenne entreprise (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="3106b-146">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="3106b-147">Crée une stratégie de configuration d’application qui inclut les applications pour une expérience vocale professionnelle.</span><span class="sxs-lookup"><span data-stu-id="3106b-147">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="3106b-148">Petite et moyenne entreprise (sans Voix Entreprise)</span><span class="sxs-lookup"><span data-stu-id="3106b-148">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="3106b-149">Crée une stratégie de configuration d’application pertinente pour les utilisateurs Teams de petite et moyenne entreprise (expérience autre que Voix Entreprise).</span><span class="sxs-lookup"><span data-stu-id="3106b-149">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="3106b-150">Responsable de la sécurité publique</span><span class="sxs-lookup"><span data-stu-id="3106b-150">Public safety officer</span></span>   |<span data-ttu-id="3106b-151">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-151">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="3106b-152">Nous ajouterons d’autres packages de stratégie dans les prochaines publication de Teams. Vérifiez donc à nouveau si vous avez besoin des informations les plus à jour.</span><span class="sxs-lookup"><span data-stu-id="3106b-152">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="3106b-153">Chaque stratégie individuelle reçoit le nom du package de stratégie afin de vous permettre d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="3106b-153">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="3106b-154">Par exemple, lorsque vous affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie du package.</span><span class="sxs-lookup"><span data-stu-id="3106b-154">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Capture d’écran du package de stratégie Éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="3106b-156">Packages de stratégie personnalisée</span><span class="sxs-lookup"><span data-stu-id="3106b-156">Custom policy packages</span></span>

<span data-ttu-id="3106b-157">**Les packages de stratégie personnalisée ne sont pas encore disponibles pour le cloud de la communauté du gouvernement (GCC)**</span><span class="sxs-lookup"><span data-stu-id="3106b-157">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="3106b-158">Les packages de stratégies personnalisées vous offrent votre propre ensemble de stratégies pour les utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-158">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="3106b-159">Créez vos propres packages de stratégies en ajoutant les types de stratégies et les stratégies dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="3106b-159">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="3106b-160">Pour créer un package de stratégie personnalisé :</span><span class="sxs-lookup"><span data-stu-id="3106b-160">To create a new custom policy package:</span></span>

1. <span data-ttu-id="3106b-161">Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="3106b-161">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Capture d'écran du bouton Ajouter dans la page Packages de stratégie du Centre d'administration":::

2. <span data-ttu-id="3106b-163">Entrez un nom et une description pour votre package.</span><span class="sxs-lookup"><span data-stu-id="3106b-163">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Capture d'écran de l'ajout d'un nouveau package de stratégie personnalisée":::

3. <span data-ttu-id="3106b-165">Sélectionnez les types de stratégies et les noms de stratégies à inclure dans le package.</span><span class="sxs-lookup"><span data-stu-id="3106b-165">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="3106b-166">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3106b-166">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="3106b-167">Comment utiliser des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="3106b-167">How to use policy packages</span></span>

<span data-ttu-id="3106b-168">L'exemple suivant explique comment utiliser des packages de stratégie dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-168">The following outlines how to use policy packages in your organization.</span></span>

![Vue d'ensemble de l'utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- <span data-ttu-id="3106b-170">**[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: afficher les stratégies dans un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="3106b-170">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="3106b-171">Vous pouvez ensuite afficher les paramètres de chaque stratégie dans un package avant de l'affecter.</span><span class="sxs-lookup"><span data-stu-id="3106b-171">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="3106b-172">Assurez-vous de comprendre chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="3106b-172">Make sure that you understand each setting.</span></span> <span data-ttu-id="3106b-173">Déterminez si les valeurs prédéfinies sont appropriées pour votre organisation ou si vous devez les modifier pour qu'elles soient plus restrictives ou moins restrictives en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-173">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="3106b-174">Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pouvez pas modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="3106b-174">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="3106b-175">Une stratégie supprimée est re-créée avec les paramètres prédéfinés lorsque vous affectez le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="3106b-175">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="3106b-176">**[Personnaliser](#customize-policies-in-a-policy-package)**: personnalisez les paramètres des stratégies dans le package de stratégies pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3106b-176">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="3106b-177">**[Attribuer :](#assign-a-policy-package)** affecter le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3106b-177">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="3106b-178">Vous pouvez également modifier les paramètres des stratégies dans un package de stratégie après avoir attribué un package.</span><span class="sxs-lookup"><span data-stu-id="3106b-178">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="3106b-179">Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué.</span><span class="sxs-lookup"><span data-stu-id="3106b-179">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="3106b-180">Voici comment afficher, attribuer et personnaliser des packages de stratégie dans le Centre d'administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3106b-180">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="3106b-181">Afficher les paramètres d'une stratégie dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="3106b-181">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="3106b-182">Dans la navigation gauche du Centre d'administration Microsoft Teams, sélectionnez **Packages** de stratégie, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="3106b-182">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="3106b-183">Cliquez sur la stratégie à afficher.</span><span class="sxs-lookup"><span data-stu-id="3106b-183">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="3106b-184">Personnaliser les stratégies dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="3106b-184">Customize policies in a policy package</span></span>

<span data-ttu-id="3106b-185">Vous pouvez modifier les paramètres d'une stratégie via la page **Packages** de stratégie ou en vous rendre directement sur la page stratégie dans le Centre d'administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3106b-185">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="3106b-186">Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, faites l'une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="3106b-186">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="3106b-187">Cliquez **sur Packages de stratégie,** puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="3106b-187">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="3106b-188">Cliquez sur le type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="3106b-188">Click the policy type.</span></span>  <span data-ttu-id="3106b-189">Par exemple, cliquez sur **Stratégies de messagerie.**</span><span class="sxs-lookup"><span data-stu-id="3106b-189">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="3106b-190">Sélectionnez la stratégie à modifier.</span><span class="sxs-lookup"><span data-stu-id="3106b-190">Select the policy you want to edit.</span></span> <span data-ttu-id="3106b-191">Les stratégies liées à un package de stratégies ont le même nom que le package de stratégies.</span><span class="sxs-lookup"><span data-stu-id="3106b-191">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="3106b-192">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="3106b-192">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="3106b-193">Attribuer un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="3106b-193">Assign a policy package</span></span>

<span data-ttu-id="3106b-194">Vous pouvez attribuer un package de stratégie à un utilisateur, un groupe ou un lot d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3106b-194">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="3106b-195">Pour plus d'informations sur l'attribution de packages de stratégie, voir [Attribuer des packages de stratégie à des utilisateurs et groupes.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="3106b-195">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3106b-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3106b-196">Related topics</span></span>

- [<span data-ttu-id="3106b-197">Attribuer des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="3106b-197">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="3106b-198">Packages de stratégie Teams pour les administrateurs EDU</span><span class="sxs-lookup"><span data-stu-id="3106b-198">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="3106b-199">Packages de stratégie Teams pour la santé publique</span><span class="sxs-lookup"><span data-stu-id="3106b-199">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="3106b-200">Packages de stratégie Teams pour le gouvernement</span><span class="sxs-lookup"><span data-stu-id="3106b-200">Teams policy packages for government</span></span>](policy-packages-gov.md)
