---
title: Utiliser Teams avec les services bureau à distance
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser Microsoft Teams avec les services bureau à distance.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119093"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="adf88-103">Équipes dans les services Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="adf88-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="adf88-104">Cet article décrit les exigences et les limitations relatives à l’utilisation de Microsoft Teams dans un environnement des services Bureau à distance.</span><span class="sxs-lookup"><span data-stu-id="adf88-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="adf88-105">Qu’est-ce que les rds ?</span><span class="sxs-lookup"><span data-stu-id="adf88-105">What is RDS?</span></span>

<span data-ttu-id="adf88-106">Les services Bureau à distance sont la plateforme de choix pour créer des solutions de virtualisation pour chaque client final.</span><span class="sxs-lookup"><span data-stu-id="adf88-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="adf88-107">Les services Bureau à distance vous permettent de fournir des applications virtualisées individuelles, d’accéder au bureau mobile et à distance sécurisés et de fournir aux utilisateurs finaux la possibilité d’exécuter leurs applications et bureaux à partir du cloud.</span><span class="sxs-lookup"><span data-stu-id="adf88-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="adf88-108">Les services RdS offrent une flexibilité, une efficacité de coût et une extensibilité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="adf88-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="adf88-109">Les services Bureau à jour sont disponibles via diverses options de déploiement, notamment Windows Server 2016 pour les déploiements locaux, Microsoft Azure pour les déploiements dans le cloud et un vaste éventail de solutions partenaires.</span><span class="sxs-lookup"><span data-stu-id="adf88-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="adf88-110">En fonction de votre environnement et de vos préférences, vous pouvez configurer la solution rds pour la virtualisation basée sur les sessions, en tant qu’infrastructure VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="adf88-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="adf88-111">Actuellement, Teams dans un environnement de services bureau à distance est disponible avec la prise en charge de la collaboration et de la fonctionnalité de conversation.</span><span class="sxs-lookup"><span data-stu-id="adf88-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="adf88-112">Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.</span><span class="sxs-lookup"><span data-stu-id="adf88-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="adf88-113">Teams sur les rds avec la conversation et la collaboration</span><span class="sxs-lookup"><span data-stu-id="adf88-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="adf88-114">Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.</span><span class="sxs-lookup"><span data-stu-id="adf88-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="adf88-115">Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion</span><span class="sxs-lookup"><span data-stu-id="adf88-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="adf88-116">Vous pouvez définir des stratégies à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adf88-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="adf88-117">La propagation des modifications de stratégie peut prendre un certain temps (quelques heures).</span><span class="sxs-lookup"><span data-stu-id="adf88-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="adf88-118">Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau dans quelques heures.</span><span class="sxs-lookup"><span data-stu-id="adf88-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="adf88-119">[**Polices d’appel**](teams-calling-policy.md): Teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="adf88-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="adf88-120">Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="adf88-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="adf88-121">[**Stratégies de**](meeting-policies-in-teams.md)réunion : Teams inclut la stratégie de réunion AllOff intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="adf88-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="adf88-122">Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="adf88-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="adf88-123">Attribuer des stratégies à l’aide du Centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adf88-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="adf88-124">Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="adf88-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="adf88-125">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="adf88-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="adf88-126">Sélectionnez l’utilisateur en sélectionnant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**</span><span class="sxs-lookup"><span data-stu-id="adf88-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="adf88-127">Pour ce faire, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="adf88-127">Do the following steps:</span></span>

    <span data-ttu-id="adf88-128">a.</span><span class="sxs-lookup"><span data-stu-id="adf88-128">a.</span></span>  <span data-ttu-id="adf88-129">Sous **Stratégie d’appel,** **sélectionnez DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="adf88-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="adf88-130">b.</span><span class="sxs-lookup"><span data-stu-id="adf88-130">b.</span></span>  <span data-ttu-id="adf88-131">Sous **Stratégie de réunion,** **sélectionnez AllOff.**</span><span class="sxs-lookup"><span data-stu-id="adf88-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="adf88-132">Sélectionnez **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="adf88-132">Select **Apply**.</span></span>

<span data-ttu-id="adf88-133">Pour affecter une stratégie à plusieurs utilisateurs à la fois :</span><span class="sxs-lookup"><span data-stu-id="adf88-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="adf88-134">Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="adf88-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="adf88-135">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="adf88-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="adf88-136">Pour sélectionner tous les utilisateurs, sélectionnez la &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="adf88-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="adf88-137">Sélectionnez **Modifier les paramètres,** a apporter les modifications de votre choix, puis **sélectionnez Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="adf88-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="adf88-138">Vous pouvez également suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="adf88-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="adf88-139">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à la stratégie que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="adf88-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="adf88-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="adf88-140">For example:</span></span>

    - <span data-ttu-id="adf88-141">Allez aux  >  **stratégies d’appel** vocal, puis **sélectionnez DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="adf88-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="adf88-142">Allez dans **stratégies**  >  **de réunion Réunions,** puis **sélectionnez AllOff.**</span><span class="sxs-lookup"><span data-stu-id="adf88-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="adf88-143">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="adf88-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="adf88-144">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="adf88-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="adf88-145">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="adf88-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="adf88-146">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="adf88-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="adf88-147">Attribuer des stratégies à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="adf88-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="adf88-148">L’exemple suivant montre comment utiliser [grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adf88-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="adf88-149">Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="adf88-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="adf88-150">L’exemple suivant montre comment utiliser [grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adf88-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="adf88-151">Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="adf88-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>