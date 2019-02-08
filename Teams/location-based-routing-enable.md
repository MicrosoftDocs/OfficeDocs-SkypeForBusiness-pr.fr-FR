---
title: Activer le routage par emplacement pour le routage Direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Découvrez comment activer le routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8437eba299cb42415d224017ca7d0e888fffa684
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771007"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="2f030-103">Activer le routage par emplacement pour le routage Direct</span><span class="sxs-lookup"><span data-stu-id="2f030-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="2f030-104">Avant de suivre les étapes décrites dans cet article, assurez-vous que vous avez lu [Plan Location-Based de routage pour le routage Direct](location-based-routing-plan.md) et effectué les étapes dans [configurer les paramètres réseau pour le routage basé sur l’emplacement](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2f030-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="2f030-105">Cet article décrit comment activer le routage basé sur un emplacement pour le routage Direct.</span><span class="sxs-lookup"><span data-stu-id="2f030-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="2f030-106">Une fois que vous déployez l’acheminement d’un système téléphonique Direct et configurer des sous-réseaux, les sites et régions de réseau, vous êtes prêt à activer le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="2f030-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="2f030-107">Pour effectuer les étapes décrites dans cet article, vous aurez besoin de se familiariser avec les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f030-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2f030-108">Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f030-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="2f030-109">Vous devez activer la fonction de routage pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2f030-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="2f030-110">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2f030-110">Users</span></span>
- <span data-ttu-id="2f030-111">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="2f030-111">Network sites</span></span>
- <span data-ttu-id="2f030-112">Configurations de passerelle</span><span class="sxs-lookup"><span data-stu-id="2f030-112">Gateway configurations</span></span>
- <span data-ttu-id="2f030-113">Stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="2f030-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="2f030-114">Activer le routage emplacement pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2f030-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="2f030-115">Utiliser le ``Set-CsOnlinePstnUsages`` applet de commande pour définir les utilisations RTC.</span><span class="sxs-lookup"><span data-stu-id="2f030-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="2f030-116">Pour plusieurs utilisations, séparez chaque d’utilisation par une virgule.</span><span class="sxs-lookup"><span data-stu-id="2f030-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="2f030-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f030-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="2f030-118">Utiliser le ``New-CsOnlineVoiceRoutingPolicy`` applet de commande pour créer une stratégie de routage voix pour associer l’utilisateur avec les utilisations PSTN appropriées.</span><span class="sxs-lookup"><span data-stu-id="2f030-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="2f030-119">Lorsque vous attribuez des utilisations PSTN à une stratégie de routage des communications vocales, assurez-vous que vous effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f030-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="2f030-120">Utiliser des utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale vers le site</span><span class="sxs-lookup"><span data-stu-id="2f030-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="2f030-121">Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une zone où des restrictions de routage basé sur l’emplacement ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="2f030-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="2f030-122">Dans cet exemple, nous créer deux nouvelles stratégies routage des communications vocales et leur attribuer des utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="2f030-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="2f030-123">Le tableau suivant présente les stratégies de routage voix définies dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="2f030-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="2f030-124">1 stratégie de routage voix</span><span class="sxs-lookup"><span data-stu-id="2f030-124">Voice routing policy 1</span></span>|<span data-ttu-id="2f030-125">Stratégie de routage 2 voix</span><span class="sxs-lookup"><span data-stu-id="2f030-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="2f030-126">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="2f030-126">Voice policy ID</span></span>   |<span data-ttu-id="2f030-127">Stratégie de routage voix Delhi</span><span class="sxs-lookup"><span data-stu-id="2f030-127">Delhi voice routing policy</span></span>   |<span data-ttu-id="2f030-128">Stratégie de routage voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="2f030-128">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="2f030-129">Utilisations PSTN en ligne</span><span class="sxs-lookup"><span data-stu-id="2f030-129">Online PSTN usages</span></span>  |<span data-ttu-id="2f030-130">Appel longue Distance</span><span class="sxs-lookup"><span data-stu-id="2f030-130">Long Distance</span></span>  |<span data-ttu-id="2f030-131">Longue Distance internes, locales</span><span class="sxs-lookup"><span data-stu-id="2f030-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="2f030-132">Pour plus d’informations, voir [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="2f030-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="2f030-133">Utiliser le ``Grant-CsOnlineVoiceRoutingPolicy`` applet de commande pour associer en ligne vocale des stratégies de routage pour les utilisateurs qui ont besoin d’appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="2f030-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="2f030-134">Activer le routage emplacement pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="2f030-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="2f030-135">Utiliser le ``Set-CsTenantNetworkSite`` applet de commande pour activer le routage basé sur l’emplacement et associer les stratégies de routage pour vos sites réseau qui doivent appliquer des restrictions de routage vocale.</span><span class="sxs-lookup"><span data-stu-id="2f030-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    <span data-ttu-id="2f030-136">Dans cet exemple, nous activer en fonction de routage pour le site Delhi et le site d’Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="2f030-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    <span data-ttu-id="2f030-137">Le tableau suivant indique les sites activés pour le routage de fonction dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="2f030-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="2f030-138">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2f030-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="2f030-139">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2f030-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="2f030-140">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="2f030-140">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="2f030-141">True</span><span class="sxs-lookup"><span data-stu-id="2f030-141">True</span></span>    |<span data-ttu-id="2f030-142">True</span><span class="sxs-lookup"><span data-stu-id="2f030-142">True</span></span>    |
    |<span data-ttu-id="2f030-143">Stratégie de routage voix</span><span class="sxs-lookup"><span data-stu-id="2f030-143">Voice routing policy</span></span>    | <span data-ttu-id="2f030-144">Stratégie de routage voix Delhi</span><span class="sxs-lookup"><span data-stu-id="2f030-144">Delhi voice routing policy</span></span>       |<span data-ttu-id="2f030-145">Stratégie de routage voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="2f030-145">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="2f030-146">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="2f030-146">Subnets</span></span>     |<span data-ttu-id="2f030-147">Sous-réseau 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2f030-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="2f030-148">Sous-réseau 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2f030-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="2f030-149">Activer le routage emplacement pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="2f030-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="2f030-150">Utiliser le ``New-CsOnlinePstnGateway`` applet de commande pour créer une configuration de passerelle pour chaque site de la passerelle ou le réseau.</span><span class="sxs-lookup"><span data-stu-id="2f030-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="2f030-151">Si plusieurs passerelles sont associés à un système (par exemple, la passerelle ou le PBX), modifiez chaque passerelle pour activer les restrictions de routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="2f030-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="2f030-152">Dans cet exemple, nous créons une configuration de la passerelle pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="2f030-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="2f030-153">Pour plus d’informations, voir [Configurer le routage Direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="2f030-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="2f030-154">Utiliser le ``Set-CSOnlinePSTNGateway`` applet de commande pour activer le routage emplacement pour vos passerelles qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="2f030-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="2f030-155">Activer le routage emplacement aux passerelles qui routent les appels vers les passerelles PSTN qui acheminer les appels vers la passerelle PSTN, puis associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="2f030-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="2f030-156">Dans cet exemple, nous activer en fonction de routage pour chaque passerelle qui est associé à des passerelles PSTN dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="2f030-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="2f030-157">N’activez pas basée sur l’emplacement de routage pour les passerelles qui ne routent les appels RTC.</span><span class="sxs-lookup"><span data-stu-id="2f030-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="2f030-158">Toutefois, vous devez associer la passerelle au site réseau où se trouve le système.</span><span class="sxs-lookup"><span data-stu-id="2f030-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="2f030-159">Il s’agit, car les restrictions de routage basé sur l’emplacement doivent être appliqués pour les appels PSTN atteindre les points de terminaison connectés via cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="2f030-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="2f030-160">Dans cet exemple, en fonction de routage n’est pas activé pour chaque passerelle est associée à des systèmes PBX dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="2f030-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="2f030-161">Points de terminaison connectés aux systèmes qui ne routent les appels RTC (par exemple, un PBX) auront des restrictions similaires comme points de terminaison d’utilisateurs équipes activés pour le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="2f030-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="2f030-162">Cela signifie que ces utilisateurs peuvent passer et recevoir des appels vers et depuis les utilisateurs équipes quel que soit emplacement son.</span><span class="sxs-lookup"><span data-stu-id="2f030-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="2f030-163">Ils peuvent également émettre et recevoir des appels vers et depuis d’autres systèmes qui ne routent les appels vers le réseau téléphonique commuté (par exemple, un point de terminaison connecté à un système PBX différents) quel que soit le site réseau auquel le système est associé.</span><span class="sxs-lookup"><span data-stu-id="2f030-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="2f030-164">Tous les appels entrants, les appels sortants, les transferts d’appel et le transfert d’appel qui impliquent des points de terminaison RTC seront soumis aux applications de routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="2f030-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="2f030-165">Ces appels doivent utiliser uniquement les passerelles PSTN qui sont définis en tant que local à ces systèmes.</span><span class="sxs-lookup"><span data-stu-id="2f030-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="2f030-166">Le tableau suivant présente la configuration de la passerelle de quatre passerelles dans deux sites différents réseau : deux connectés à des passerelles PSTN et deux connectés à des systèmes PBX.</span><span class="sxs-lookup"><span data-stu-id="2f030-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="2f030-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="2f030-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="2f030-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="2f030-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="2f030-169">DEL PstnGateway:Gateway 1-EG</span><span class="sxs-lookup"><span data-stu-id="2f030-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="2f030-170">True</span><span class="sxs-lookup"><span data-stu-id="2f030-170">True</span></span>     |   <span data-ttu-id="2f030-171">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2f030-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="2f030-172">PstnGateway:Gateway 2 HYD-EG</span><span class="sxs-lookup"><span data-stu-id="2f030-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="2f030-173">True</span><span class="sxs-lookup"><span data-stu-id="2f030-173">True</span></span>      |      <span data-ttu-id="2f030-174">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2f030-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="2f030-175">DEL PstnGateway:Gateway 3-PBX</span><span class="sxs-lookup"><span data-stu-id="2f030-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="2f030-176">True</span><span class="sxs-lookup"><span data-stu-id="2f030-176">True</span></span>     |     <span data-ttu-id="2f030-177">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="2f030-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="2f030-178">HYD PstnGateway:Gateway 4-PBX</span><span class="sxs-lookup"><span data-stu-id="2f030-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="2f030-179">True</span><span class="sxs-lookup"><span data-stu-id="2f030-179">True</span></span>     |    <span data-ttu-id="2f030-180">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2f030-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="2f030-181">Activer le routage basé sur l’emplacement pour l’appel de stratégies</span><span class="sxs-lookup"><span data-stu-id="2f030-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="2f030-182">Pour appliquer un emplacement de routage pour des utilisateurs spécifiques, configurer la stratégie de voix des utilisateurs afin d’empêcher le numéro payant PTSN contournement de média.</span><span class="sxs-lookup"><span data-stu-id="2f030-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="2f030-183">Utiliser le ``Grant-TeamsCallingPolicy`` applet de commande pour activer le routage basé sur l’emplacement en empêchant payant PSTN de contournement.</span><span class="sxs-lookup"><span data-stu-id="2f030-183">Use the ``Grant-TeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="2f030-184">Dans cet exemple, nous empêcher PSTN payant contournement de média à l’utilisateur1 stratégies de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2f030-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="2f030-185">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2f030-185">Related topics</span></span>
- [<span data-ttu-id="2f030-186">Planifier le routage par emplacement pour le routage Direct</span><span class="sxs-lookup"><span data-stu-id="2f030-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="2f030-187">Configurer les paramètres réseau pour le routage basé sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="2f030-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="2f030-188">Terminologie de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="2f030-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
