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
description: Découvrez comment utiliser et gérer des packages de stratégie dans Microsoft Teams simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs.
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810187"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="56953-103">Gérer les packages de stratégie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56953-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="56953-104">Un package de stratégie dans Microsoft Teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="56953-105">Nous avons créé des packages de stratégies pour simplifier, rationaliser et offrir une cohérence dans le cadre de la gestion des stratégies pour des groupes d’utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="56953-106">Vous pouvez utiliser les [packages de stratégie inclus dans Teams](#policy-packages-included-in-teams) créer vos propres [packages de stratégie personnalisés.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="56953-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Capture d’écran de la page Packages de stratégie dans le Centre d’administration":::

<span data-ttu-id="56953-108">Vous pouvez personnaliser les paramètres des stratégies dans un package de stratégies pour répondre aux besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="56953-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="56953-109">Lorsque vous modifiez les paramètres des stratégies dans un package, tous les utilisateurs affectés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="56953-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="56953-110">Vous gérez les packages de stratégies à l’aide Microsoft Teams centre d’administration ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56953-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="56953-111">Chaque utilisateur aura besoin du module de communication avancée pour recevoir une affectation de package de stratégie personnalisé.</span><span class="sxs-lookup"><span data-stu-id="56953-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="56953-112">Pour plus d’informations, [consultez le module complémentaire Communications avancées pour Microsoft Teams.](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="56953-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="56953-113">Qu’est-ce qu’un package de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="56953-113">What is a policy package?</span></span>

<span data-ttu-id="56953-114">Les packages de stratégie vous permettent de Teams fonctionnalités que vous voulez autoriser ou restreindre pour des ensembles spécifiques de personnes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="56953-115">Chaque package de stratégie dans Teams est conçu autour d’un rôle d’utilisateur et inclut des stratégies et paramètres de stratégie prédéfinés qui supportent les activités de collaboration et de communication classiques pour ce rôle.</span><span class="sxs-lookup"><span data-stu-id="56953-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="56953-116">Les packages de stratégies prisent en charge les types Teams suivants :</span><span class="sxs-lookup"><span data-stu-id="56953-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="56953-117">Stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="56953-117">Messaging policy</span></span>
- <span data-ttu-id="56953-118">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="56953-118">Meeting policy</span></span>
- <span data-ttu-id="56953-119">Stratégie de configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="56953-119">App setup policy</span></span>
- <span data-ttu-id="56953-120">Stratégie d’Appel</span><span class="sxs-lookup"><span data-stu-id="56953-120">Calling policy</span></span>
- <span data-ttu-id="56953-121">Stratégie d’événements en direct</span><span class="sxs-lookup"><span data-stu-id="56953-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="56953-122">Packages de stratégie inclus dans Teams</span><span class="sxs-lookup"><span data-stu-id="56953-122">Policy packages included in Teams</span></span>

<span data-ttu-id="56953-123">Teams inclut actuellement les packages de stratégie suivants.</span><span class="sxs-lookup"><span data-stu-id="56953-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="56953-124">Nom du package</span><span class="sxs-lookup"><span data-stu-id="56953-124">Package name</span></span> | <span data-ttu-id="56953-125">Description</span><span class="sxs-lookup"><span data-stu-id="56953-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="56953-126">Éducation (étudiant de l’enseignement supérieur)</span><span class="sxs-lookup"><span data-stu-id="56953-126">Education (Higher education student)</span></span>    |<span data-ttu-id="56953-127">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants de l’enseignement supérieur.</span><span class="sxs-lookup"><span data-stu-id="56953-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="56953-128">Éducation (étudiant du primaire)</span><span class="sxs-lookup"><span data-stu-id="56953-128">Education (Primary school student)</span></span>   |<span data-ttu-id="56953-129">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants du primaire.</span><span class="sxs-lookup"><span data-stu-id="56953-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="56953-130">Éducation (étudiant de l’enseignement secondaire)</span><span class="sxs-lookup"><span data-stu-id="56953-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="56953-131">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux étudiants secondaires.</span><span class="sxs-lookup"><span data-stu-id="56953-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="56953-132">Éducation (enseignant)</span><span class="sxs-lookup"><span data-stu-id="56953-132">Education (Teacher)</span></span>    |<span data-ttu-id="56953-133">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux enseignants.</span><span class="sxs-lookup"><span data-stu-id="56953-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="56953-134">Éducation (enseignant du primaire utilisant l’apprentissage à distance)</span><span class="sxs-lookup"><span data-stu-id="56953-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="56953-135">Création d’un groupe de stratégies qui s’appliquent aux enseignants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.</span><span class="sxs-lookup"><span data-stu-id="56953-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="56953-136">Éducation (étudiant du primaire à l’aide de l’apprentissage à distance)</span><span class="sxs-lookup"><span data-stu-id="56953-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="56953-137">Création d’un groupe de stratégies qui s’appliquent aux étudiants du primaire pour optimiser la sécurité et la collaboration des étudiants lors de l’utilisation de l’apprentissage à distance.</span><span class="sxs-lookup"><span data-stu-id="56953-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="56953-138">Gestionnaire en ligne</span><span class="sxs-lookup"><span data-stu-id="56953-138">Frontline manager</span></span> |<span data-ttu-id="56953-139">Crée un ensemble de stratégies et applique ces paramètres aux responsables en ligne de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="56953-140">Employé en ligne</span><span class="sxs-lookup"><span data-stu-id="56953-140">Frontline worker</span></span> |<span data-ttu-id="56953-141">Crée un ensemble de stratégies et applique ces paramètres aux employés de votre organisation en ligne.</span><span class="sxs-lookup"><span data-stu-id="56953-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="56953-142">Professionnel de la santé</span><span class="sxs-lookup"><span data-stu-id="56953-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="56953-143">Crée un ensemble de stratégies et de paramètres de stratégies qui offrent aux travailleurs cliniques tels que les infirmières autorisées, les infirmières responsables, les médecins et les travailleurs sociaux un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="56953-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="56953-144">Travailleurs de l’information sur le secteur de la santé</span><span class="sxs-lookup"><span data-stu-id="56953-144">Healthcare information worker</span></span>  |<span data-ttu-id="56953-145">Crée un ensemble de stratégies et de paramètres de stratégie qui donnent aux travailleurs de l’information, par exemple, le personnel de l’information, l’informatique, le personnel financier et les responsables de la mise en conformité, un accès total aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="56953-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="56953-146">Salle de soins de santé</span><span class="sxs-lookup"><span data-stu-id="56953-146">Healthcare patient room</span></span>  |<span data-ttu-id="56953-147">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles des patients dans votre organisation de santé.</span><span class="sxs-lookup"><span data-stu-id="56953-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="56953-148">Petite et moyenne entreprise (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="56953-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="56953-149">Crée une stratégie de configuration d’application qui inclut les applications pour une expérience vocale professionnelle.</span><span class="sxs-lookup"><span data-stu-id="56953-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="56953-150">Petite et moyenne entreprise (sans Voix Entreprise)</span><span class="sxs-lookup"><span data-stu-id="56953-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="56953-151">Crée une stratégie de configuration d’application pertinente pour les utilisateurs de pme Teams d’entreprise (expérience voice non professionnelle).</span><span class="sxs-lookup"><span data-stu-id="56953-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="56953-152">Responsable de la sécurité publique</span><span class="sxs-lookup"><span data-stu-id="56953-152">Public safety officer</span></span>   |<span data-ttu-id="56953-153">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="56953-154">Nous ajouterons d’autres packages de stratégie dans les prochaines Teams, aussi consultez-nous à nouveau pour obtenir les informations les plus à jour.</span><span class="sxs-lookup"><span data-stu-id="56953-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="56953-155">Chaque stratégie individuelle reçoit le nom du package de stratégie afin de vous permettre d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="56953-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="56953-156">Par exemple, lorsque vous affectez le package de stratégie Éducation (Enseignant) aux enseignants de votre établissement scolaire, une stratégie nommée Education_Teacher est créée pour chaque stratégie du package.</span><span class="sxs-lookup"><span data-stu-id="56953-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Capture d’écran du package de stratégie Éducation (enseignant)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="56953-158">Packages de stratégie personnalisée</span><span class="sxs-lookup"><span data-stu-id="56953-158">Custom policy packages</span></span>

<span data-ttu-id="56953-159">**Les packages de stratégie personnalisée ne sont pas encore disponibles pour Cloud de la communauté du secteur public (Cloud de la communauté du secteur public)**</span><span class="sxs-lookup"><span data-stu-id="56953-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="56953-160">Les packages de stratégies personnalisées vous offrent votre propre ensemble de stratégies pour les utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="56953-161">Créez vos propres packages de stratégies en ajoutant les types de stratégies et les stratégies dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="56953-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="56953-162">Pour créer un package de stratégie personnalisé :</span><span class="sxs-lookup"><span data-stu-id="56953-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="56953-163">Dans la barre de navigation gauche du Microsoft Teams d’administration, sélectionnez **Packages** de stratégie, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="56953-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Capture d’écran du bouton Ajouter dans la page Packages de stratégie du Centre d’administration":::

2. <span data-ttu-id="56953-165">Entrez un nom et une description pour votre package.</span><span class="sxs-lookup"><span data-stu-id="56953-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Capture d’écran de l’ajout d’un nouveau package de stratégie personnalisée":::

3. <span data-ttu-id="56953-167">Sélectionnez les types de stratégies et les noms de stratégies à inclure dans le package.</span><span class="sxs-lookup"><span data-stu-id="56953-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="56953-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="56953-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="56953-169">Comment utiliser des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="56953-169">How to use policy packages</span></span>

<span data-ttu-id="56953-170">L’exemple suivant explique comment utiliser des packages de stratégie dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-170">The following outlines how to use policy packages in your organization.</span></span>

![Vue d’ensemble de l’utilisation des packages de stratégie](media/manage-policy-packages-overview.png)

- <span data-ttu-id="56953-172">**[Affichage](#view-the-settings-of-a-policy-in-a-policy-package)**: afficher les stratégies dans un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="56953-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="56953-173">Vous pouvez ensuite afficher les paramètres de chaque stratégie dans un package avant de l’affecter.</span><span class="sxs-lookup"><span data-stu-id="56953-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="56953-174">Assurez-vous de comprendre chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="56953-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="56953-175">Déterminez si les valeurs prédéfinies sont appropriées pour votre organisation ou si vous devez les modifier pour qu’elles soient plus restrictives ou moins restrictives en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="56953-176">Si une stratégie est supprimée, vous pouvez toujours afficher les paramètres, mais vous ne pouvez pas modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="56953-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="56953-177">Une stratégie supprimée est re-créée avec les paramètres prédéfinés lorsque vous affectez le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="56953-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="56953-178">**[Personnaliser](#customize-policies-in-a-policy-package)**: personnalisez les paramètres des stratégies dans le package de stratégies pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56953-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="56953-179">**[Attribuer :](#assign-a-policy-package)** affecter le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="56953-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="56953-180">Vous pouvez également modifier les paramètres des stratégies dans un package de stratégie après avoir attribué un package.</span><span class="sxs-lookup"><span data-stu-id="56953-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="56953-181">Les modifications que vous apportez aux paramètres de stratégie sont automatiquement appliquées aux utilisateurs auxquels le package est attribué.</span><span class="sxs-lookup"><span data-stu-id="56953-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="56953-182">Voici comment afficher, attribuer et personnaliser des packages de stratégie dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="56953-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="56953-183">Afficher les paramètres d’une stratégie dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="56953-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="56953-184">Dans le navigation gauche du Microsoft Teams d’administration, sélectionnez **Packages** de stratégie, puis sélectionnez un package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="56953-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="56953-185">Cliquez sur la stratégie à afficher.</span><span class="sxs-lookup"><span data-stu-id="56953-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="56953-186">Personnaliser les stratégies dans un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="56953-186">Customize policies in a policy package</span></span>

<span data-ttu-id="56953-187">Vous pouvez modifier les paramètres d’une stratégie via la page **Packages** de stratégie ou en vous rendre directement sur la page stratégie dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="56953-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="56953-188">Dans le panneau de navigation gauche du Microsoft Teams d’administration, faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="56953-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="56953-189">Cliquez **sur Packages de stratégie,** puis sélectionnez le package de stratégie en cliquant à gauche du nom du package.</span><span class="sxs-lookup"><span data-stu-id="56953-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="56953-190">Cliquez sur le type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="56953-190">Click the policy type.</span></span>  <span data-ttu-id="56953-191">Par exemple, cliquez **sur Stratégies de messagerie.**</span><span class="sxs-lookup"><span data-stu-id="56953-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="56953-192">Sélectionnez la stratégie à modifier.</span><span class="sxs-lookup"><span data-stu-id="56953-192">Select the policy you want to edit.</span></span> <span data-ttu-id="56953-193">Les stratégies liées à un package de stratégies ont le même nom que le package de stratégies.</span><span class="sxs-lookup"><span data-stu-id="56953-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="56953-194">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="56953-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="56953-195">Attribuer un package de stratégie</span><span class="sxs-lookup"><span data-stu-id="56953-195">Assign a policy package</span></span>

<span data-ttu-id="56953-196">Vous pouvez attribuer un package de stratégie à un utilisateur, un groupe ou un lot d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="56953-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="56953-197">Pour plus d’informations sur l’attribution de packages de stratégie, voir [Attribuer des packages de stratégie à des utilisateurs et groupes.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="56953-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="56953-198">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="56953-198">Related topics</span></span>

- [<span data-ttu-id="56953-199">Attribuer des packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="56953-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="56953-200">Teams packages de stratégie pour les administrateurs edu</span><span class="sxs-lookup"><span data-stu-id="56953-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="56953-201">Packages de stratégie Teams pour la santé publique</span><span class="sxs-lookup"><span data-stu-id="56953-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="56953-202">Teams packages de stratégies pour le gouvernement</span><span class="sxs-lookup"><span data-stu-id="56953-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
