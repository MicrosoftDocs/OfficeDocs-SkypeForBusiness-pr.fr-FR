---
title: Appel de stratégie dans Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Découvrez les paramètres de stratégie d’appel dans Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860260"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="442de-103">Appel de stratégie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="442de-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="442de-104">Dans Microsoft Teams, appel de contrôle des stratégies les appels et les fonctionnalités de transfert d’appel sont disponibles pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="442de-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="442de-105">Les stratégies d’appel déterminent si un utilisateur peut effectuer des appels privées, utilisez le transfert d’appel ou acheminer les appels vers la messagerie vocale, envoyer les appels aux groupes d’appel, sonnerie simultanée à d’autres utilisateurs ou les numéros de téléphone externe, utilisent la délégation pour les appels entrants et sortants, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="442de-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="442de-106">Une stratégie globale par défaut est créée automatiquement, mais les administrateurs peuvent également créer et affecter des stratégies appel personnalisés.</span><span class="sxs-lookup"><span data-stu-id="442de-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="442de-107">Paramètres de stratégie de l’appel</span><span class="sxs-lookup"><span data-stu-id="442de-107">Calling policy settings</span></span>

|<span data-ttu-id="442de-108">Paramètre de stratégie de l’appel</span><span class="sxs-lookup"><span data-stu-id="442de-108">Calling policy setting</span></span> | <span data-ttu-id="442de-109">Description</span><span class="sxs-lookup"><span data-stu-id="442de-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="442de-110">Utilisateur peut passer des appels privées</span><span class="sxs-lookup"><span data-stu-id="442de-110">User can make private calls</span></span> | <span data-ttu-id="442de-111">Contrôle de toutes les fonctionnalités d’appel dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="442de-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="442de-112">Désactivation de cette désactiver toutes les fonctionnalités d’appel dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="442de-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="442de-113">Le transfert d’appel et la sonnerie simultanée à d’autres utilisateurs</span><span class="sxs-lookup"><span data-stu-id="442de-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="442de-114">Contrôle si les appels entrants peuvent être transférés à d’autres utilisateurs ou une autre personne peut faire sonner en même temps.</span><span class="sxs-lookup"><span data-stu-id="442de-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="442de-115">Le transfert d’appel et la sonnerie simultanée aux numéros de téléphone externe</span><span class="sxs-lookup"><span data-stu-id="442de-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="442de-116">Contrôle si les appels entrants peuvent être transférés vers un numéro externe ou un numéro externe peut faire sonner en même temps.</span><span class="sxs-lookup"><span data-stu-id="442de-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="442de-117">Messagerie vocale est disponible pour acheminer les appels entrants vers les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="442de-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="442de-118">Permet les appels entrants soient envoyées à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="442de-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="442de-119">Les options valides sont **toujours activés**, **toujours désactivés**ou **définis par les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="442de-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="442de-120">Les appels entrants peuvent être acheminés pour appeler des groupes</span><span class="sxs-lookup"><span data-stu-id="442de-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="442de-121">Contrôle si les appels entrants peuvent être transférés vers un groupe d’appel.</span><span class="sxs-lookup"><span data-stu-id="442de-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="442de-122">Autoriser la délégation pour les appels entrants et sortants</span><span class="sxs-lookup"><span data-stu-id="442de-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="442de-123">Permet aux appels entrants destinés à être acheminés vers les délégués ; permet de délégués pour émettre des appels sortants part les utilisateurs pour lesquels ils ont délégué des autorisations.</span><span class="sxs-lookup"><span data-stu-id="442de-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="442de-124">Empêcher le contournement de média payant et envoyer les appels par le biais de la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="442de-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="442de-125">La valeur **sur** pour envoyer les appels via RTC et provoquer des frais plutôt qu’à passer par le réseau et en contournant le cas.</span><span class="sxs-lookup"><span data-stu-id="442de-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="442de-126">Occupé (e) sur occupé (e) est disponible dans un appel.</span><span class="sxs-lookup"><span data-stu-id="442de-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="442de-127">Configure les appels entrants comment sont traités lorsqu’un utilisateur est déjà dans un appel ou une conférence.</span><span class="sxs-lookup"><span data-stu-id="442de-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="442de-128">Nouveaux appels entrants peuvent être rejetées avec un signal occupé (e).</span><span class="sxs-lookup"><span data-stu-id="442de-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="442de-129">Créer une stratégie personnalisée appelante</span><span class="sxs-lookup"><span data-stu-id="442de-129">Create a custom calling policy</span></span>

<span data-ttu-id="442de-130">Suivez ces étapes pour créer une nouvelle stratégie appelante personnalisée.</span><span class="sxs-lookup"><span data-stu-id="442de-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="442de-131">Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.</span><span class="sxs-lookup"><span data-stu-id="442de-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="442de-132">Sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="442de-132">Select **New policy**.</span></span>
3. <span data-ttu-id="442de-133">Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel.</span><span class="sxs-lookup"><span data-stu-id="442de-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="442de-134">Toutes les sélections sont **désactivées** par défaut.</span><span class="sxs-lookup"><span data-stu-id="442de-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="442de-135">Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="442de-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="442de-136">Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.</span><span class="sxs-lookup"><span data-stu-id="442de-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="442de-137">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="442de-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="442de-138">Modifier un appel de stratégie existant</span><span class="sxs-lookup"><span data-stu-id="442de-138">Modify an existing calling policy</span></span>

<span data-ttu-id="442de-139">Suivez ces étapes pour modifier une stratégie de l’appel.</span><span class="sxs-lookup"><span data-stu-id="442de-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="442de-140">Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.</span><span class="sxs-lookup"><span data-stu-id="442de-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="442de-141">Cliquez sur en regard de la stratégie que vous souhaitez modifier, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="442de-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="442de-142">Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel.</span><span class="sxs-lookup"><span data-stu-id="442de-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="442de-143">Toutes les sélections sont **désactivées** par défaut.</span><span class="sxs-lookup"><span data-stu-id="442de-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="442de-144">Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="442de-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="442de-145">Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.</span><span class="sxs-lookup"><span data-stu-id="442de-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="442de-146">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="442de-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="442de-147">Affecter une stratégie appelante à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="442de-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="442de-148">Suivez ces étapes pour attribuer une stratégie personnalisée appelante à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="442de-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="442de-149">Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.</span><span class="sxs-lookup"><span data-stu-id="442de-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="442de-150">Cliquez sur en regard du nom de la stratégie pour le sélectionner, puis sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="442de-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="442de-151">Dans le volet **Gérer les utilisateurs** , recherchez le nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="442de-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="442de-152">(Vous devez entrer au moins trois caractères).</span><span class="sxs-lookup"><span data-stu-id="442de-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="442de-153">Sélectionnez le nom d’utilisateur, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="442de-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="442de-154">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="442de-154">Select **Save**.</span></span>
