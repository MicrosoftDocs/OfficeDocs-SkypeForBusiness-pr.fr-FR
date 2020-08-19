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
ms.openlocfilehash: dbbc0956f339760bedf1ce9cc2c5012cc317e152
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803969"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="e7491-103">Packages de stratégie d’équipe pour la santé</span><span class="sxs-lookup"><span data-stu-id="e7491-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="e7491-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="e7491-104">Overview</span></span>

<span data-ttu-id="e7491-105">Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7491-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="e7491-106">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="e7491-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="e7491-107">Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e7491-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="e7491-108">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="e7491-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="e7491-109">Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7491-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="e7491-110">Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :</span><span class="sxs-lookup"><span data-stu-id="e7491-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="e7491-111">Messagerie</span><span class="sxs-lookup"><span data-stu-id="e7491-111">Messaging</span></span>
- <span data-ttu-id="e7491-112">Réunions</span><span class="sxs-lookup"><span data-stu-id="e7491-112">Meetings</span></span>
- <span data-ttu-id="e7491-113">Appel</span><span class="sxs-lookup"><span data-stu-id="e7491-113">Calling</span></span>
- <span data-ttu-id="e7491-114">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="e7491-114">App setup</span></span>
- <span data-ttu-id="e7491-115">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="e7491-115">Live events</span></span>

<span data-ttu-id="e7491-116">Teams inclut actuellement les packages de politique de santé suivants.</span><span class="sxs-lookup"><span data-stu-id="e7491-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="e7491-117">Nom du package dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e7491-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="e7491-118">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="e7491-118">Best used for</span></span>|<span data-ttu-id="e7491-119">Description</span><span class="sxs-lookup"><span data-stu-id="e7491-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="e7491-120">Travailleurs cliniques médicaux</span><span class="sxs-lookup"><span data-stu-id="e7491-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="e7491-121">Travailleurs cliniques de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="e7491-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="e7491-122">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs cliniques tels que les infirmières, les infirmières, les médecins et les travailleurs sociaux d’avoir un accès complet aux discussions, aux appels, à la gestion des équipes et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="e7491-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="e7491-123">Travailleurs de l’information sur la santé</span><span class="sxs-lookup"><span data-stu-id="e7491-123">Healthcare information worker</span></span>  |<span data-ttu-id="e7491-124">Travailleurs de l’information au sein de votre organisation de santé</span><span class="sxs-lookup"><span data-stu-id="e7491-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="e7491-125">Crée un ensemble de stratégies et de paramètres de stratégie qui permettent aux travailleurs de l’information, tels que le personnel informatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, un accès complet aux discussions, aux appels et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="e7491-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="e7491-126">Salle de santé du patient</span><span class="sxs-lookup"><span data-stu-id="e7491-126">Healthcare patient room</span></span>  |<span data-ttu-id="e7491-127">Appareils de salle de patient</span><span class="sxs-lookup"><span data-stu-id="e7491-127">Patient room devices</span></span>|<span data-ttu-id="e7491-128">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux salles de soins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7491-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Capture d’écran des packages de politique de santé](media/policy-packages-healthcare.png)

<span data-ttu-id="e7491-130">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7491-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="e7491-131">Par exemple, lorsque vous attribuez le package de stratégie de travailleur clinique de santé aux médecins au sein de votre organisation, une stratégie nommée Healthcare_ClinicalWorker est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="e7491-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="e7491-133">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="e7491-133">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="e7491-134">Afficher</span><span class="sxs-lookup"><span data-stu-id="e7491-134">View</span></span>

<span data-ttu-id="e7491-135">Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="e7491-135">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="e7491-136">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7491-136">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="e7491-137">Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7491-137">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="e7491-138">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="e7491-138">Customize</span></span>

<span data-ttu-id="e7491-139">Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7491-139">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="e7491-140">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="e7491-140">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="e7491-141">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7491-141">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="e7491-142">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e7491-142">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="e7491-143">Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e7491-143">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="e7491-144">Assignation</span><span class="sxs-lookup"><span data-stu-id="e7491-144">Assign</span></span>

<span data-ttu-id="e7491-145">Attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e7491-145">Assign the policy package to users.</span></span> <span data-ttu-id="e7491-146">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, cliquez sur **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e7491-146">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="e7491-147">Vous pouvez également [Utiliser PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour assigner un package de stratégie aux grands groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e7491-147">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="e7491-148">Pour plus d’informations sur l’affectation d’un package de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell, voir [affecter un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e7491-148">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="e7491-150">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="e7491-150">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7491-151">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e7491-151">Related topics</span></span>

[<span data-ttu-id="e7491-152">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="e7491-152">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="e7491-153">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="e7491-153">Assign policies to your users in Teams</span></span>](assign-policies.md)
