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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des packages de stratégie d’équipe pour votre organisation de santé.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578200"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="8c6d8-103">Packages de stratégie d’équipe pour la santé</span><span class="sxs-lookup"><span data-stu-id="8c6d8-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="8c6d8-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="8c6d8-104">Overview</span></span>

<span data-ttu-id="8c6d8-105">Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="8c6d8-106">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="8c6d8-107">Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="8c6d8-108">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="8c6d8-109">Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="8c6d8-110">Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :</span><span class="sxs-lookup"><span data-stu-id="8c6d8-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="8c6d8-111">Réunions</span><span class="sxs-lookup"><span data-stu-id="8c6d8-111">Meetings</span></span>
- <span data-ttu-id="8c6d8-112">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="8c6d8-112">Live events</span></span>
- <span data-ttu-id="8c6d8-113">Appel</span><span class="sxs-lookup"><span data-stu-id="8c6d8-113">Calling</span></span>
- <span data-ttu-id="8c6d8-114">Messagerie</span><span class="sxs-lookup"><span data-stu-id="8c6d8-114">Messaging</span></span>
- <span data-ttu-id="8c6d8-115">Équipes</span><span class="sxs-lookup"><span data-stu-id="8c6d8-115">Teams</span></span>
- <span data-ttu-id="8c6d8-116">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="8c6d8-116">App setup</span></span>

<span data-ttu-id="8c6d8-117">Teams inclut actuellement les packages de politique de santé suivants.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="8c6d8-118">Nom du package dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="8c6d8-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="8c6d8-119">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="8c6d8-119">Best used for</span></span>|<span data-ttu-id="8c6d8-120">Description</span><span class="sxs-lookup"><span data-stu-id="8c6d8-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8c6d8-121">Travailleurs cliniques médicaux</span><span class="sxs-lookup"><span data-stu-id="8c6d8-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="8c6d8-122">Travailleurs cliniques de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="8c6d8-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="8c6d8-123">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="8c6d8-124">Travailleurs de l’information sur la santé</span><span class="sxs-lookup"><span data-stu-id="8c6d8-124">Healthcare information worker</span></span>  |<span data-ttu-id="8c6d8-125">Travailleurs de l’information au sein de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="8c6d8-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="8c6d8-126">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="8c6d8-127">Salle de santé du patient</span><span class="sxs-lookup"><span data-stu-id="8c6d8-127">Healthcare patient room</span></span>  |<span data-ttu-id="8c6d8-128">Appareils de salle de patient</span><span class="sxs-lookup"><span data-stu-id="8c6d8-128">Patient room devices</span></span>|<span data-ttu-id="8c6d8-129">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de soins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Capture d’écran des packages de politique de santé](media/policy-packages-healthcare.png)

<span data-ttu-id="8c6d8-131">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="8c6d8-132">Par exemple, lorsque vous attribuez le package de stratégie de travailleur clinique de santé aux médecins au sein de votre organisation, une stratégie nommée Healthcare_ClinicalWorker est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="8c6d8-134">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="8c6d8-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="8c6d8-135">Afficher</span><span class="sxs-lookup"><span data-stu-id="8c6d8-135">View</span></span>

<span data-ttu-id="8c6d8-136">Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="8c6d8-137">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="8c6d8-138">Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="8c6d8-139">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="8c6d8-139">Customize</span></span>

<span data-ttu-id="8c6d8-140">Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="8c6d8-141">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="8c6d8-142">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="8c6d8-143">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="8c6d8-144">Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="8c6d8-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="8c6d8-145">Assignation</span><span class="sxs-lookup"><span data-stu-id="8c6d8-145">Assign</span></span>

<span data-ttu-id="8c6d8-146">Attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-146">Assign the policy package to users.</span></span> <span data-ttu-id="8c6d8-147">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, cliquez sur **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="8c6d8-148">Vous pouvez également utiliser PowerShell pour assigner un package de stratégie aux grands groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="8c6d8-149">Pour connaître la procédure d’affectation d’un package de stratégie, voir [affecter un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="8c6d8-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="8c6d8-151">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="8c6d8-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c6d8-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c6d8-152">Related topics</span></span>

[<span data-ttu-id="8c6d8-153">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="8c6d8-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="8c6d8-154">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="8c6d8-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
