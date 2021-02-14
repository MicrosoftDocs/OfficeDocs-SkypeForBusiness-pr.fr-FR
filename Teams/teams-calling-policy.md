---
title: Stratégies de conservation dans Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Découvrez comment créer, modifier et ajouter des utilisateurs à des stratégies d’appel personnalisées dans Microsoft Teams, ainsi que différents paramètres de stratégie d’appel.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581049"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="e904b-103">Stratégies de conservation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e904b-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="e904b-104">Dans Microsoft Teams, les stratégies d’appel contrôlent les fonctionnalités d’appel et de forwardage disponibles pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e904b-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="e904b-105">Les stratégies d’appel déterminent si un utilisateur peut passer des appels privés, utiliser le forwarding d’appel ou une sonnerie simultanée vers d’autres utilisateurs ou des numéros de téléphone externes, router les appels vers la messagerie vocale, envoyer des appels à des groupes d’appels, utiliser la délégation pour les appels entrants et sortants, etc.</span><span class="sxs-lookup"><span data-stu-id="e904b-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="e904b-106">Vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) créée automatiquement, ou créer et attribuer des stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e904b-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="e904b-107">Créer une stratégie d’appel personnalisée</span><span class="sxs-lookup"><span data-stu-id="e904b-107">Create a custom calling policy</span></span>

<span data-ttu-id="e904b-108">Pour créer une stratégie d’appel personnalisée, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="e904b-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="e904b-109">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **Stratégies**  >  **d’appel vocal.**</span><span class="sxs-lookup"><span data-stu-id="e904b-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e904b-110">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e904b-110">Select **Add**.</span></span>
3. <span data-ttu-id="e904b-111">Activer ou désactiver les fonctionnalités que vous souhaitez utiliser dans votre stratégie d’appel.</span><span class="sxs-lookup"><span data-stu-id="e904b-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="e904b-112">Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **Activé** ou **Utilisateur contrôlé.**</span><span class="sxs-lookup"><span data-stu-id="e904b-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="e904b-113">Pour empêcher le routage vers la messagerie vocale, **sélectionnez Désactivé.**</span><span class="sxs-lookup"><span data-stu-id="e904b-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="e904b-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e904b-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="e904b-115">Modifier une stratégie d’appel</span><span class="sxs-lookup"><span data-stu-id="e904b-115">Edit a calling policy</span></span>

<span data-ttu-id="e904b-116">Pour modifier une stratégie d’appel existante, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="e904b-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="e904b-117">Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Stratégies**  >  **d’appel vocal.**</span><span class="sxs-lookup"><span data-stu-id="e904b-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e904b-118">Cliquez en côté de la stratégie à modifier, puis sélectionnez **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="e904b-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="e904b-119">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="e904b-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="e904b-120">Affecter une stratégie d’appel personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e904b-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="e904b-121">Paramètres de stratégie d’appel</span><span class="sxs-lookup"><span data-stu-id="e904b-121">Calling policy settings</span></span>

<span data-ttu-id="e904b-122">Voici les paramètres que vous pouvez configurer pour les stratégies d’appel.</span><span class="sxs-lookup"><span data-stu-id="e904b-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="e904b-123">Passer des appels privés</span><span class="sxs-lookup"><span data-stu-id="e904b-123">Make private calls</span></span>

<span data-ttu-id="e904b-124">Ce paramètre contrôle toutes les fonctionnalités d’appel dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e904b-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="e904b-125">Désactiver cette fonctionnalité pour désactiver toutes les fonctionnalités d’appel dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e904b-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="e904b-126">Call forwarding and simultaneous ringing to people in your organization</span><span class="sxs-lookup"><span data-stu-id="e904b-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="e904b-127">Ce paramètre contrôle si les appels entrants peuvent être transmis à d’autres utilisateurs ou appeler une autre personne en même temps.</span><span class="sxs-lookup"><span data-stu-id="e904b-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="e904b-128">Call forwarding and simultaneous ringing to external phone numbers</span><span class="sxs-lookup"><span data-stu-id="e904b-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="e904b-129">Ce paramètre contrôle si les appels entrants peuvent être transmis à un numéro externe ou faire sonner un numéro externe en même temps.</span><span class="sxs-lookup"><span data-stu-id="e904b-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="e904b-130">La messagerie vocale est disponible pour les appels entrants de routage</span><span class="sxs-lookup"><span data-stu-id="e904b-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="e904b-131">Ce paramètre permet d’envoyer des appels entrants vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="e904b-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="e904b-132">Les options valides sont les :</span><span class="sxs-lookup"><span data-stu-id="e904b-132">Valid options are:</span></span>

- <span data-ttu-id="e904b-133">**Activé** La messagerie vocale est toujours disponible pour les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="e904b-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="e904b-134">**Désactivé**  La messagerie vocale n’est pas disponible pour les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="e904b-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="e904b-135">**Utilisateur contrôlé** Les utilisateurs peuvent déterminer s’ils souhaitent que la messagerie vocale soit disponible.</span><span class="sxs-lookup"><span data-stu-id="e904b-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="e904b-136">Les appels entrants peuvent être acheminés vers des groupes d’appels</span><span class="sxs-lookup"><span data-stu-id="e904b-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="e904b-137">Ce paramètre contrôle si les appels entrants peuvent être transmis à un groupe d’appels.</span><span class="sxs-lookup"><span data-stu-id="e904b-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="e904b-138">Autoriser la délégation pour les appels entrants et sortants</span><span class="sxs-lookup"><span data-stu-id="e904b-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="e904b-139">Ce paramètre permet de router les appels entrants vers des délégués, ce qui permet aux délégués de réaliser des appels sortants pour le compte des utilisateurs pour lesquels ils ont des autorisations de délégué.</span><span class="sxs-lookup"><span data-stu-id="e904b-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="e904b-140">Pour plus d’informations, [voir Partager une ligne téléphonique avec un délégué.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="e904b-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="e904b-141">Empêcher la dérivation et l’envoi d’appels via le PSTN</span><span class="sxs-lookup"><span data-stu-id="e904b-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="e904b-142">La définition de cette fonction sur **Ôter** envoie des appels via le réseau PSTN et incurère des frais au lieu de les envoyer via le réseau sans passer par les frais de téléphone gratuits.</span><span class="sxs-lookup"><span data-stu-id="e904b-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="e904b-143">Occupé(elle) est disponible pendant un appel</span><span class="sxs-lookup"><span data-stu-id="e904b-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="e904b-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span><span class="sxs-lookup"><span data-stu-id="e904b-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="e904b-145">Les appels entrants ou nouveaux peuvent être rejetés avec un signal occupé.</span><span class="sxs-lookup"><span data-stu-id="e904b-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="e904b-146">Vous pouvez activer les options de occupé(ive) au niveau du client ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e904b-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="e904b-147">Quelle que soit la configuration de leurs options de occupé, les utilisateurs d’un appel ou d’une conférence ou ceux avec un appel en attente ne sont pas empêchés de lancer de nouveaux appels ou conférences.</span><span class="sxs-lookup"><span data-stu-id="e904b-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="e904b-148">Ce paramètre est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="e904b-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="e904b-149">Autoriser les appels PSTN Web</span><span class="sxs-lookup"><span data-stu-id="e904b-149">Allow web PSTN calling</span></span>

<span data-ttu-id="e904b-150">Ce paramètre permet aux utilisateurs d’appeler des numéros PSTN à l’aide du client web Teams.</span><span class="sxs-lookup"><span data-stu-id="e904b-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="e904b-151">Autoriser l’attente musicale</span><span class="sxs-lookup"><span data-stu-id="e904b-151">Allow music on hold</span></span>

<span data-ttu-id="e904b-152">Ce paramètre vous permet d’activer ou de désactiver l’attente musicale lorsqu’un appelant PSTN est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="e904b-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="e904b-153">Elle est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e904b-153">It's turned on by default.</span></span> <span data-ttu-id="e904b-154">Ce paramètre ne s’applique pas aux fonctionnalités de parcage d’appel et de délégué de responsable et est actuellement disponible uniquement via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e904b-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e904b-155">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e904b-155">Related topics</span></span>

[<span data-ttu-id="e904b-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="e904b-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="e904b-157">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e904b-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
