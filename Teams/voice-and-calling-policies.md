---
title: Gérer les stratégies de voix et d’appel Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Découvrez les stratégies Teams voix et d’appel.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460584"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="65155-103">Gérer les stratégies de voix et d’appel Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65155-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="65155-104">Les stratégies de voix et d’appel sont utilisées pour contrôler la voix et les appels Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65155-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="65155-105">Stratégies d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="65155-105">Emergency calling policies</span></span>

<span data-ttu-id="65155-106">Les stratégies [d’appel d’urgence](manage-emergency-calling-policies.md) vous permet de configurer ce qui se passe lorsqu’un utilisateur de votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="65155-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="65155-107">Ces stratégies sont gérées dans le Centre Teams’administration ou à l’aide Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65155-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Capture d’écran de la stratégie d’appel d’urgence.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="65155-109">Stratégies de routage d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="65155-109">Emergency call routing policies</span></span>

<span data-ttu-id="65155-110">Si votre organisation **Système téléphonique** déployé un routage direct, vous pouvez utiliser des stratégies de [routage](manage-emergency-call-routing-policies.md) des appels d’urgence pour déterminer où les appels d’urgence sont acheminés, si les services d’urgence améliorés sont activés et les numéros utilisés pour les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="65155-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="65155-111">Ces stratégies sont gérées à l’aide de PowerShell ou dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="65155-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Capture d’écran de la stratégie de routage des appels d’urgence.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="65155-113">Stratégies d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="65155-113">Caller ID policies</span></span>

<span data-ttu-id="65155-114">[Les stratégies d’ID d’appelant](caller-id-policies.md) sont utilisées pour modifier ou bloquer l’ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="65155-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Capture d’écran de la stratégie d’ID d’appelant.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="65155-116">Stratégies de routage voix</span><span class="sxs-lookup"><span data-stu-id="65155-116">Voice routing policies</span></span>

<span data-ttu-id="65155-117">Une [stratégie de routage vocal](manage-voice-routing-policies.md) est un conteneur pour les enregistrements d’utilisation de réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="65155-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="65155-118">Vous pouvez utiliser ces stratégies si votre organisation a déployé Système téléphonique **routage direct.**</span><span class="sxs-lookup"><span data-stu-id="65155-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="65155-119">Les stratégies de routage voix peuvent être gérées avec PowerShell ou dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="65155-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Capture d’écran de la stratégie de routage vocal.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="65155-121">Stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="65155-121">Calling policies</span></span>

<span data-ttu-id="65155-122">[](teams-calling-policy.md) Les stratégies d’appel contrôlent les fonctionnalités d’appel et de forwardage disponibles pour les utilisateurs, notamment la décision d’un utilisateur de passer des appels privés, d’envoyer des appels à des groupes d’appels et de router les appels vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="65155-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Capture d’écran de la stratégie d’appel.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="65155-124">Stratégies de parc et de récupération des appels</span><span class="sxs-lookup"><span data-stu-id="65155-124">Call park and retrieve policies</span></span>

<span data-ttu-id="65155-125">[Le parc d’appel et la récupération](call-park-and-retrieve.md) permettent aux utilisateurs de mettre d’autres utilisateurs en attente et de permettre à ce même utilisateur ou à quelqu’un d’autre de continuer l’appel.</span><span class="sxs-lookup"><span data-stu-id="65155-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Capture d’écran de la stratégie de récupération et de parc d’appel.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="65155-127">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="65155-127">Create and manage dial plans</span></span>

<span data-ttu-id="65155-128">[Les plans de numérotation](create-and-manage-dial-plans.md) traduisent les numéros de téléphone à composer pour l’autorisation d’appel et le routage.</span><span class="sxs-lookup"><span data-stu-id="65155-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="65155-129">Vous pouvez créer et gérer des plans de numérotation via PowerShell ou dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="65155-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Capture d’écran du plan de numérotation.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="65155-131">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="65155-131">Related topics</span></span>

* [<span data-ttu-id="65155-132">Gérer les stratégies d’appels d’urgence Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65155-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="65155-133">Gérer les stratégies de routage d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="65155-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="65155-134">Gérer les stratégies d’ID d’appelant dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65155-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="65155-135">Gérer les stratégies de routage vocal</span><span class="sxs-lookup"><span data-stu-id="65155-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="65155-136">Stratégies de conservation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65155-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="65155-137">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65155-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="65155-138">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="65155-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="65155-139">Gérer les Teams des stratégies</span><span class="sxs-lookup"><span data-stu-id="65155-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
