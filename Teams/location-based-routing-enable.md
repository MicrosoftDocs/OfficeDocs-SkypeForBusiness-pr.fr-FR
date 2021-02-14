---
title: Activer le routage géodépendant pour le routage direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment activer Location-Based routage direct, notamment l’activer pour les utilisateurs, les sites réseau, les configurations de passerelle et les stratégies d’appel.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822914"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="ca8a1-103">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="ca8a1-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="ca8a1-104">Avant de suivre les étapes de cet article, assurez-vous que vous avez lu Plan [de routage Location-Based](location-based-routing-plan.md) pour le routage direct et que vous avez suivi les étapes de la procédure Configurer les paramètres réseau pour le [Location-Based routage.](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="ca8a1-105">Cet article décrit comment activer Location-Based routage pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="ca8a1-106">Une fois que vous avez déployé le routage direct du système téléphonique et que vous avez installé les régions, sites et sous-réseaux réseau, vous êtes prêt à activer Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="ca8a1-107">Pour suivre les étapes de cet article, vous devez être familiarisé avec les cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ca8a1-108">Pour en savoir plus, voir [Vue d’ensemble de Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="ca8a1-109">Vous devez activer Location-Based routage pour les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca8a1-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="ca8a1-110">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ca8a1-110">Users</span></span>
- <span data-ttu-id="ca8a1-111">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="ca8a1-111">Network sites</span></span>
- <span data-ttu-id="ca8a1-112">Configurations de la passerelle</span><span class="sxs-lookup"><span data-stu-id="ca8a1-112">Gateway configurations</span></span>
- <span data-ttu-id="ca8a1-113">Stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="ca8a1-113">Calling policies</span></span>

<span data-ttu-id="ca8a1-114">Vous pouvez utiliser le [Centre d’administration de Microsoft Team](#using-the-microsoft-teams-admin-center) ou [PowerShel](#using-powershell)l pour activer Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ca8a1-115">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca8a1-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="ca8a1-116">Activer Location-Based routage pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ca8a1-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="ca8a1-117">Créez une stratégie de routage vocal et attribuez des utilisations PSTN à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="ca8a1-118">Lorsque vous attribuez des utilisations PSTN à une stratégie, assurez-vous d’effectuer l’une des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca8a1-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="ca8a1-119">Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale vers le site.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="ca8a1-120">Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="ca8a1-121">Affectez la stratégie de routage voix aux utilisateurs qui ont besoin d’appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="ca8a1-122">Pour en savoir plus sur la création de stratégies de routage voix et leur attribution aux utilisateurs, voir Gérer les stratégies de routage vocal [dans Microsoft Teams.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="ca8a1-123">Activer Location-Based routage pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="ca8a1-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="ca8a1-124">Activez Location-Based routage pour vos sites qui ont besoin d’appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="ca8a1-125">Pour ce faire, dans le navigation gauche du Centre d’administration Microsoft Teams, allez à la topologie du réseau Emplacements, sélectionnez un site réseau, cliquez sur Modifier, puis activer le routage basé sur  >   **l’emplacement.** </span><span class="sxs-lookup"><span data-stu-id="ca8a1-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="ca8a1-126">Pour plus d’informations, [voir Gérer votre topologie de réseau.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="ca8a1-127">Activer Location-Based routage pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="ca8a1-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="ca8a1-128">Activez Location-Based routage vers des passerelles qui routent des appels vers des passerelles PSTN qui routent des appels vers le réseau PSTN et associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="ca8a1-129">Dans le groupe de navigation de gauche, cliquez sur **l’onglet**  >   **SBCs.**</span><span class="sxs-lookup"><span data-stu-id="ca8a1-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="ca8a1-130">Sélectionnez le SBC, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="ca8a1-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="ca8a1-131">Sous **Routage basé sur l’emplacement et optimisation des médias,** **activez Activer le routage basé sur l’emplacement.**</span><span class="sxs-lookup"><span data-stu-id="ca8a1-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="ca8a1-132">Spécifiez l’ID de site de la passerelle, puis définissez le mode de dérivation.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="ca8a1-133">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="ca8a1-134">Activer Location-Based routage des appels</span><span class="sxs-lookup"><span data-stu-id="ca8a1-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="ca8a1-135">Pour appliquer Location-Based routage pour des utilisateurs spécifiques, définissez la stratégie d’appel de l’utilisateur afin d’empêcher la dérivation PSTN toll.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="ca8a1-136">Pour ce faire, vous pouvez activer le **paramètre** Prévenir le contournement toll dans la stratégie d’appel.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="ca8a1-137">Pour en savoir plus, consultez [les stratégies d’appel dans Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="ca8a1-138">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca8a1-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="ca8a1-139">Activer Location-Based routage pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ca8a1-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="ca8a1-140">Utilisez [l’cmdlet Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) pour définir les utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="ca8a1-141">Pour plusieurs utilisations, séparez chaque utilisation par une virgule.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="ca8a1-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ca8a1-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="ca8a1-143">Utilisez [l’cmdlet New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) pour créer une stratégie de routage voix afin d’associer l’utilisateur aux utilisations PSTN appropriées.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="ca8a1-144">Lorsque vous affectez des utilisations PSTN à une stratégie de routage vocale, assurez-vous d’effectuer l’une des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca8a1-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="ca8a1-145">Utiliser les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle RSTN locale vers le site</span><span class="sxs-lookup"><span data-stu-id="ca8a1-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="ca8a1-146">Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="ca8a1-147">Dans cet exemple, nous créons deux stratégies de routage voix et leur affectons des utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="ca8a1-148">Le tableau suivant indique les stratégies de routage voix définies dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="ca8a1-149">Stratégie de routage voix 1</span><span class="sxs-lookup"><span data-stu-id="ca8a1-149">Voice routing policy 1</span></span>|<span data-ttu-id="ca8a1-150">Stratégie de routage voix 2</span><span class="sxs-lookup"><span data-stu-id="ca8a1-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="ca8a1-151">ID de stratégie vocale en ligne</span><span class="sxs-lookup"><span data-stu-id="ca8a1-151">Online voice policy ID</span></span>   |<span data-ttu-id="ca8a1-152">Politique de routage vocal en ligne d’Online</span><span class="sxs-lookup"><span data-stu-id="ca8a1-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="ca8a1-153">Politique de routage vocal en ligne du Service vos achats en ligne</span><span class="sxs-lookup"><span data-stu-id="ca8a1-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="ca8a1-154">Utilisations PSTN en ligne</span><span class="sxs-lookup"><span data-stu-id="ca8a1-154">Online PSTN usages</span></span>  |<span data-ttu-id="ca8a1-155">Longue distance</span><span class="sxs-lookup"><span data-stu-id="ca8a1-155">Long Distance</span></span>  |<span data-ttu-id="ca8a1-156">Longue distance, local, interne</span><span class="sxs-lookup"><span data-stu-id="ca8a1-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="ca8a1-157">Utilisez l’cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) pour associer des stratégies de routage voix en ligne aux utilisateurs qui demandent l’application de restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="ca8a1-158">Activer Location-Based routage pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="ca8a1-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="ca8a1-159">Utilisez l’cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) pour activer le routage Location-Based et associer des stratégies de routage voix à vos sites réseau qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="ca8a1-160">Dans cet exemple, nous avons activé Location-Based routage pour le site Densoin et le site Densoin.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="ca8a1-161">Le tableau suivant indique les sites activés pour le Location-Based routage des sites dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="ca8a1-162">Site 1 (Syz)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="ca8a1-163">Site 2 (Sod)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="ca8a1-164">Nom du site</span><span class="sxs-lookup"><span data-stu-id="ca8a1-164">Site name</span></span>    |<span data-ttu-id="ca8a1-165">Site 1 (Syz)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="ca8a1-166">Site 2 (Sod)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="ca8a1-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="ca8a1-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="ca8a1-168">Vrai</span><span class="sxs-lookup"><span data-stu-id="ca8a1-168">True</span></span>    |<span data-ttu-id="ca8a1-169">Vrai</span><span class="sxs-lookup"><span data-stu-id="ca8a1-169">True</span></span>    |
    |<span data-ttu-id="ca8a1-170">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="ca8a1-170">Subnets</span></span>     |<span data-ttu-id="ca8a1-171">Sous-réseau 1 (Syz)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="ca8a1-172">Sous-réseau 2 (Syz)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="ca8a1-173">Activer Location-Based routage pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="ca8a1-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="ca8a1-174">Utilisez la [cmdlet New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) pour créer une configuration de passerelle pour chaque passerelle ou site réseau.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="ca8a1-175">Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer les Location-Based de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="ca8a1-176">Dans cet exemple, nous créons une configuration de passerelle pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="ca8a1-177">Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ca8a1-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="ca8a1-178">Utilisez la cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) pour activer Location-Based routage pour vos passerelles qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="ca8a1-179">Activez Location-Based routage vers des passerelles qui routent des appels vers des passerelles PSTN qui routent des appels vers le réseau PSTN et associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="ca8a1-180">Dans cet exemple, nous avons activé Location-Based routage des utilisateurs pour chaque passerelle associée aux passerelles RSTN dans les sites des centres d’information et des entreprises.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="ca8a1-181">N’activez pas Location-Based routage pour les passerelles qui ne routent pas les appels vers le RSTN.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="ca8a1-182">Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="ca8a1-183">En effet, Location-Based restrictions de routage doivent être appliquées pour les appels RSTN qui atteignent des points de terminaison connectés via cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="ca8a1-184">Dans cet exemple, le Location-Based routage des données n’est pas activé pour chaque passerelle associée aux systèmes PBX dans les sites Voséraux.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="ca8a1-185">Activer Location-Based routage des appels</span><span class="sxs-lookup"><span data-stu-id="ca8a1-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="ca8a1-186">Pour appliquer Location-Based routage pour des utilisateurs spécifiques, définissez la stratégie vocale des utilisateurs afin d’empêcher la dérivation toll pour PTSN.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="ca8a1-187">Utilisez [l’cmdlet Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) pour activer Location-Based routage en empêchant la dérivation PSTN toll.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="ca8a1-188">Dans cet exemple, nous empêchons la dérivation PSTN contre les stratégies d’appel de l’utilisateur 1.</span><span class="sxs-lookup"><span data-stu-id="ca8a1-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="ca8a1-189">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ca8a1-189">Related topics</span></span>

- [<span data-ttu-id="ca8a1-190">Paramètres réseau pour les fonctionnalités vocales cloud dans Teams</span><span class="sxs-lookup"><span data-stu-id="ca8a1-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
