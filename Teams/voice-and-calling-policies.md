---
title: Gérer les stratégies de voix et d’appel dans Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347999"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="f58a6-102">Gérer les stratégies de voix et d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f58a6-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="f58a6-103">Les stratégies de voix et d’appel sont utilisées pour contrôler la voix et les appels dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f58a6-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="f58a6-104">Stratégies d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="f58a6-104">Emergency calling policies</span></span>

<span data-ttu-id="f58a6-105">Les stratégies [d’appel d’urgence](manage-emergency-calling-policies.md) vous permet de configurer ce qui se passe lorsqu’un utilisateur de votre organisation effectue un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f58a6-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="f58a6-106">Ces stratégies sont gérées dans le Centre d’administration Teams ou à l’aide Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f58a6-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Capture d’écran de la stratégie d’appel d’urgence.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="f58a6-108">Stratégies de routage d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="f58a6-108">Emergency call routing policies</span></span>

<span data-ttu-id="f58a6-109">Si votre organisation a déployé le routage direct du système **téléphonique,** vous pouvez utiliser des stratégies de [routage](manage-emergency-call-routing-policies.md) des appels d’urgence pour déterminer où les appels d’urgence sont acheminés, si les services d’urgence améliorés sont activés et les numéros utilisés pour les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f58a6-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="f58a6-110">Ces stratégies sont gérées à l’aide de PowerShell ou dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f58a6-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Capture d’écran de la stratégie de routage des appels d’urgence.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="f58a6-112">Stratégies d’ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="f58a6-112">Caller ID policies</span></span>

<span data-ttu-id="f58a6-113">[Les stratégies d’ID d’appelant](caller-id-policies.md) sont utilisées pour modifier ou bloquer l’ID d’appelant.</span><span class="sxs-lookup"><span data-stu-id="f58a6-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Capture d’écran de la stratégie d’ID d’appelant.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="f58a6-115">Stratégies de routage voix</span><span class="sxs-lookup"><span data-stu-id="f58a6-115">Voice routing policies</span></span>

<span data-ttu-id="f58a6-116">Une [stratégie de routage vocal](manage-voice-routing-policies.md) est un conteneur pour les enregistrements d’utilisation de réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="f58a6-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="f58a6-117">Vous pouvez utiliser ces stratégies si votre organisation a déployé le routage direct du système **téléphonique.**</span><span class="sxs-lookup"><span data-stu-id="f58a6-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="f58a6-118">Les stratégies de routage vocal peuvent être gérées avec PowerShell ou dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="f58a6-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Capture d’écran de la stratégie de routage vocal.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="f58a6-120">Stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="f58a6-120">Calling policies</span></span>

<span data-ttu-id="f58a6-121">[](teams-calling-policy.md) Les stratégies d’appel contrôlent les fonctionnalités d’appel et de forwardage disponibles pour les utilisateurs, notamment la décision d’un utilisateur de passer des appels privés, d’envoyer des appels à des groupes d’appels et de router les appels vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f58a6-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Capture d’écran de la stratégie d’appel.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="f58a6-123">Stratégies de parc et de récupération des appels</span><span class="sxs-lookup"><span data-stu-id="f58a6-123">Call park and retrieve policies</span></span>

<span data-ttu-id="f58a6-124">[Le parc d’appel et la récupération](call-park-and-retrieve.md) permettent aux utilisateurs de mettre d’autres utilisateurs en attente et de permettre à ce même utilisateur ou à quelqu’un d’autre de continuer l’appel.</span><span class="sxs-lookup"><span data-stu-id="f58a6-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Capture d’écran de la stratégie de récupération et de parc d’appel.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="f58a6-126">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="f58a6-126">Create and manage dial plans</span></span>

<span data-ttu-id="f58a6-127">[Les plans de numérotation](create-and-manage-dial-plans.md) traduisent les numéros de téléphone à composer pour l’autorisation d’appel et le routage.</span><span class="sxs-lookup"><span data-stu-id="f58a6-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="f58a6-128">Vous pouvez créer et gérer des plans de numérotation via PowerShell ou dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f58a6-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Capture d’écran du plan de numérotation.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="f58a6-130">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f58a6-130">Related topics</span></span>

* [<span data-ttu-id="f58a6-131">Gérer les stratégies d’appel d’urgence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f58a6-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="f58a6-132">Gérer les stratégies de routage d’appel d’urgence</span><span class="sxs-lookup"><span data-stu-id="f58a6-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="f58a6-133">Gérer les stratégies d’ID d’appelant dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f58a6-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="f58a6-134">Gérer les stratégies de routage vocal</span><span class="sxs-lookup"><span data-stu-id="f58a6-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="f58a6-135">Stratégies de conservation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f58a6-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="f58a6-136">Parcage et récupération d’appel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f58a6-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="f58a6-137">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="f58a6-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="f58a6-138">Gérer Teams avec des stratégies</span><span class="sxs-lookup"><span data-stu-id="f58a6-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
