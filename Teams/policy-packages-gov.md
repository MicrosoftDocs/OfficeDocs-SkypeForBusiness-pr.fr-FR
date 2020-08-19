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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804018"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="a077b-103">Packages de stratégie d’équipes pour le secteur public</span><span class="sxs-lookup"><span data-stu-id="a077b-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="a077b-104">Pour le moment, les packages de stratégie ne sont pas disponibles dans les déploiements Microsoft 365 Government High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="a077b-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="a077b-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="a077b-105">Overview</span></span>

<span data-ttu-id="a077b-106">Un [package de stratégie](manage-policy-packages.md) dans Microsoft teams est un ensemble de stratégies et de paramètres de stratégie prédéfinis que vous pouvez affecter aux utilisateurs ayant des rôles similaires au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a077b-107">Les packages de stratégie simplifient, rationalisent et garantissent la cohérence lors de la gestion des stratégies.</span><span class="sxs-lookup"><span data-stu-id="a077b-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="a077b-108">Vous pouvez personnaliser les paramètres des stratégies du package selon les besoins de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a077b-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="a077b-109">Lorsque vous modifiez les paramètres des stratégies dans un package de stratégie, tous les utilisateurs assignés à ce package obtiennent les paramètres mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a077b-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="a077b-110">Vous pouvez gérer des packages de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a077b-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="a077b-111">Les packages de stratégie prédéfinis pour les éléments suivants, en fonction du package :</span><span class="sxs-lookup"><span data-stu-id="a077b-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="a077b-112">Messagerie</span><span class="sxs-lookup"><span data-stu-id="a077b-112">Messaging</span></span>
- <span data-ttu-id="a077b-113">Réunions</span><span class="sxs-lookup"><span data-stu-id="a077b-113">Meetings</span></span>
- <span data-ttu-id="a077b-114">Appel</span><span class="sxs-lookup"><span data-stu-id="a077b-114">Calling</span></span>
- <span data-ttu-id="a077b-115">Configuration de l’application</span><span class="sxs-lookup"><span data-stu-id="a077b-115">App setup</span></span>
- <span data-ttu-id="a077b-116">Événements en direct</span><span class="sxs-lookup"><span data-stu-id="a077b-116">Live events</span></span>

<span data-ttu-id="a077b-117">Teams inclut actuellement les packages de stratégie suivants pour le gouvernement.</span><span class="sxs-lookup"><span data-stu-id="a077b-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="a077b-118">Nom du package dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a077b-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="a077b-119">Idéal pour</span><span class="sxs-lookup"><span data-stu-id="a077b-119">Best used for</span></span>|<span data-ttu-id="a077b-120">Description</span><span class="sxs-lookup"><span data-stu-id="a077b-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a077b-121">Officier de sûreté public</span><span class="sxs-lookup"><span data-stu-id="a077b-121">Public safety officer</span></span>  |<span data-ttu-id="a077b-122">Fonctionnaires de la sécurité publique au sein de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="a077b-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="a077b-123">Crée un ensemble de stratégies et de paramètres de stratégie qui s’appliquent aux responsables de la sécurité publique au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="a077b-124">Gestionnaire de terrain</span><span class="sxs-lookup"><span data-stu-id="a077b-124">Firstline manager</span></span>  |<span data-ttu-id="a077b-125">Responsables terrain au sein de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="a077b-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="a077b-126">Crée un ensemble de stratégies et applique ces paramètres aux responsables terrain de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="a077b-127">Collaborateur terrain</span><span class="sxs-lookup"><span data-stu-id="a077b-127">Firstline worker</span></span>  |<span data-ttu-id="a077b-128">Terrain travailleurs de votre organisation gouvernementale</span><span class="sxs-lookup"><span data-stu-id="a077b-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="a077b-129">Crée un ensemble de stratégies et applique ces paramètres aux travailleurs terrain au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Capture d’écran des packages de politique de santé](media/policy-packages-gov.png)

<span data-ttu-id="a077b-131">Chaque stratégie individuelle dispose du nom du package de stratégie, ce qui vous permet d’identifier facilement les stratégies liées à un package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="a077b-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="a077b-132">Par exemple, lorsque vous attribuez le package de stratégie de l’officier de sécurité public aux utilisateurs de votre organisation, une stratégie nommée PublicSafety_Officer est créée pour chaque stratégie dans le package.</span><span class="sxs-lookup"><span data-stu-id="a077b-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Capture d’écran des politiques dans l’offre pour le travail clinique de santé](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="a077b-134">Gérer vos packages de stratégie</span><span class="sxs-lookup"><span data-stu-id="a077b-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="a077b-135">Afficher</span><span class="sxs-lookup"><span data-stu-id="a077b-135">View</span></span>

<span data-ttu-id="a077b-136">Affichez les paramètres de chaque stratégie d’un package de stratégie avant d’assigner un package.</span><span class="sxs-lookup"><span data-stu-id="a077b-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a077b-137">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **packages de stratégie**, sélectionnez le nom du package, puis sélectionnez le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a077b-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="a077b-138">Déterminez si les valeurs prédéfinies conviennent à votre organisation, ou si vous avez besoin de les personnaliser en fonction de vos besoins en matière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="a077b-139">Personnaliser</span><span class="sxs-lookup"><span data-stu-id="a077b-139">Customize</span></span>

<span data-ttu-id="a077b-140">Personnalisez les paramètres des stratégies dans le package de stratégie, si nécessaire, pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a077b-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="a077b-141">Les modifications que vous apportez aux paramètres de stratégie s’appliquent automatiquement aux utilisateurs qui ont reçu le package.</span><span class="sxs-lookup"><span data-stu-id="a077b-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="a077b-142">Pour modifier les paramètres d’une stratégie dans un package de stratégie, dans le centre d’administration de Microsoft Teams, sélectionnez le package de stratégie, sélectionnez le nom de la stratégie que vous voulez modifier, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="a077b-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="a077b-143">Gardez à l’esprit que vous pouvez également modifier les paramètres des stratégies d’un package après avoir affecté le package de stratégie.</span><span class="sxs-lookup"><span data-stu-id="a077b-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="a077b-144">Pour en savoir plus, voir [personnaliser des stratégies dans un package de stratégie](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="a077b-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="a077b-145">Assignation</span><span class="sxs-lookup"><span data-stu-id="a077b-145">Assign</span></span>

<span data-ttu-id="a077b-146">Attribuez le package de stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a077b-146">Assign the policy package to users.</span></span> <span data-ttu-id="a077b-147">Pour attribuer un package de stratégie à un ou plusieurs utilisateurs, cliquez sur **gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a077b-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="a077b-148">Vous pouvez également [Utiliser PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) pour assigner un package de stratégie aux grands groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a077b-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="a077b-149">Pour plus d’informations sur l’affectation d’un package de stratégie à l’aide du centre d’administration Microsoft teams ou de PowerShell, voir [affecter un package de stratégie](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="a077b-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Capture d’écran de l’affectation d’un package de stratégie dans le centre d’administration](media/policy-packages-gov-assign.png)

<span data-ttu-id="a077b-151">Si une stratégie est affectée à un utilisateur et que vous affectez une autre stratégie, l’affectation la plus récente est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="a077b-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a077b-152">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a077b-152">Related topics</span></span>

[<span data-ttu-id="a077b-153">Gérer les packages de stratégie dans Teams</span><span class="sxs-lookup"><span data-stu-id="a077b-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="a077b-154">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="a077b-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
