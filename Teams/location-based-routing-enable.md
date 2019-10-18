---
title: Activer le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Apprenez à activer le routage en fonction de l’emplacement pour le routage direct.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4acd03dfff78d5aae329492014b24e55b2f92ec9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572021"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="07501-103">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="07501-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="07501-104">Avant de suivre les étapes décrites dans cet article, assurez-vous d’avoir lu le [routage de l’emplacement de votre plan pour le routage direct](location-based-routing-plan.md) et effectué les étapes décrites dans [configurer les paramètres réseau pour le routage via emplacement](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="07501-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="07501-105">Cet article explique comment activer le routage sur la base de l’emplacement pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="07501-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="07501-106">Après le déploiement du routage direct du système téléphonique et la configuration des zones, des sites et des sous-réseaux, vous pouvez activer le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="07501-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="07501-107">Pour suivre les étapes décrites dans cet article, vous devez être familiarisé avec les applets de méthode PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07501-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="07501-108">Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="07501-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="07501-109">Vous devez activer le routage par emplacement pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="07501-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="07501-110">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="07501-110">Users</span></span>
- <span data-ttu-id="07501-111">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="07501-111">Network sites</span></span>
- <span data-ttu-id="07501-112">Configurations des passerelles</span><span class="sxs-lookup"><span data-stu-id="07501-112">Gateway configurations</span></span>
- <span data-ttu-id="07501-113">Politiques d’appel</span><span class="sxs-lookup"><span data-stu-id="07501-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="07501-114">Activer le routage basé sur l’emplacement pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="07501-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="07501-115">Utilisez l’applet de commande [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) pour définir les utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="07501-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="07501-116">Pour les utilisations multiples, séparez chaque utilisation par une virgule.</span><span class="sxs-lookup"><span data-stu-id="07501-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="07501-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07501-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="07501-118">Utilisez l’applet de commande [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) pour créer une stratégie de routage vocal et associer l’utilisateur aux utilisations RTC appropriées.</span><span class="sxs-lookup"><span data-stu-id="07501-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="07501-119">Lorsque vous attribuez des utilisations RTC à une stratégie de routage vocale, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="07501-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="07501-120">Utiliser les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site</span><span class="sxs-lookup"><span data-stu-id="07501-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="07501-121">Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où les restrictions de routage basées sur les emplacements ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="07501-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="07501-122">Dans cet exemple, nous créons deux nouvelles stratégies de routage vocal et affectons des utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="07501-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="07501-123">Le tableau suivant répertorie les stratégies de routage vocal définies dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="07501-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="07501-124">Politique de routage de la voix 1</span><span class="sxs-lookup"><span data-stu-id="07501-124">Voice routing policy 1</span></span>|<span data-ttu-id="07501-125">Politique de routage de la voix 2</span><span class="sxs-lookup"><span data-stu-id="07501-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="07501-126">ID de la stratégie vocale en ligne</span><span class="sxs-lookup"><span data-stu-id="07501-126">Online voice policy ID</span></span>   |<span data-ttu-id="07501-127">Politique de routage vocal de Delhi en ligne</span><span class="sxs-lookup"><span data-stu-id="07501-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="07501-128">Politique de routage de la voix en ligne Hyderabad</span><span class="sxs-lookup"><span data-stu-id="07501-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="07501-129">Utilisations RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="07501-129">Online PSTN usages</span></span>  |<span data-ttu-id="07501-130">Longue distance</span><span class="sxs-lookup"><span data-stu-id="07501-130">Long Distance</span></span>  |<span data-ttu-id="07501-131">Longue distance, local, interne</span><span class="sxs-lookup"><span data-stu-id="07501-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="07501-132">Utilisez l’applet de contrôle [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) pour associer des stratégies de routage vocal en ligne aux utilisateurs qui ont besoin de restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="07501-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="07501-133">Activer le routage par emplacement pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="07501-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="07501-134">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) pour activer le routage par emplacement et associer des stratégies de routage de messagerie à vos sites réseau qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="07501-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="07501-135">Dans cet exemple, nous activons le routage en fonction de l’emplacement pour le site de Delhi et le site Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="07501-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="07501-136">Le tableau suivant indique les sites activés pour le routage par emplacement dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="07501-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="07501-137">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="07501-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="07501-138">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="07501-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="07501-139">Nom du site</span><span class="sxs-lookup"><span data-stu-id="07501-139">Site name</span></span>    |<span data-ttu-id="07501-140">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="07501-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="07501-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="07501-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="07501-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="07501-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="07501-143">Vrai</span><span class="sxs-lookup"><span data-stu-id="07501-143">True</span></span>    |<span data-ttu-id="07501-144">Vrai</span><span class="sxs-lookup"><span data-stu-id="07501-144">True</span></span>    |
    |<span data-ttu-id="07501-145">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="07501-145">Subnets</span></span>     |<span data-ttu-id="07501-146">Sous-réseau 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="07501-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="07501-147">Sous-réseau 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="07501-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="07501-148">Activer le routage basé sur l’emplacement pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="07501-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="07501-149">Utilisez l’applet de nouvelle applet de [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) pour créer une configuration de passerelle pour chaque passerelle ou site réseau.</span><span class="sxs-lookup"><span data-stu-id="07501-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="07501-150">Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer les restrictions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="07501-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="07501-151">Dans cet exemple, nous créons une configuration de passerelle pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="07501-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="07501-152">Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="07501-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="07501-153">Utilisez l’applet de cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) pour activer le routage de géolocalisation des passerelles qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="07501-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="07501-154">Activez le routage par emplacement vers des passerelles qui acheminent les appels vers les passerelles RTC qui routent les appels vers le RTC et associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="07501-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="07501-155">Dans cet exemple, nous activons le routage en fonction de l’emplacement pour chaque passerelle associée aux passerelles RTC dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="07501-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="07501-156">N’activez pas le routage basé sur l’emplacement pour les passerelles qui ne routent pas les appels vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="07501-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="07501-157">Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système.</span><span class="sxs-lookup"><span data-stu-id="07501-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="07501-158">En effet, les restrictions de routage basées sur l’emplacement doivent être appliquées pour les appels RTC atteignant des points de terminaison qui sont connectés par le biais de cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="07501-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="07501-159">Dans cet exemple, le routage basé sur l’emplacement n’est pas activé pour chaque passerelle associée aux systèmes PBX dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="07501-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="07501-160">Les points de terminaison connectés à des systèmes qui ne routent pas les appels vers le RTC (par exemple, un PBX) présentent des restrictions similaires pour le routage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="07501-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="07501-161">Cela signifie que ces utilisateurs peuvent passer et recevoir des appels vers et depuis les utilisateurs Teams, quel que soit l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="07501-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="07501-162">Ils peuvent également passer et recevoir des appels vers et à partir d’autres systèmes qui ne routent pas les appels vers le réseau PSTN (par exemple, un point de terminaison connecté à un autre système PBX), quel que soit le site du réseau auquel le système est associé.</span><span class="sxs-lookup"><span data-stu-id="07501-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="07501-163">Tous les appels entrants, les appels sortants, les transferts d’appel et le transfert d’appel qui impliquent des points de terminaison RTC sont soumis à des conditions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="07501-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="07501-164">Ces appels doivent uniquement utiliser des passerelles RTC définies comme locales pour de tels systèmes.</span><span class="sxs-lookup"><span data-stu-id="07501-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="07501-165">Le tableau suivant montre la configuration de la passerelle de quatre passerelles sur deux sites réseau différents : deux connectés à des passerelles RTC et deux connectés aux systèmes PBX.</span><span class="sxs-lookup"><span data-stu-id="07501-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="07501-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="07501-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="07501-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="07501-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="07501-168">PstnGateway : passerelle 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="07501-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="07501-169">Vrai</span><span class="sxs-lookup"><span data-stu-id="07501-169">True</span></span>     |   <span data-ttu-id="07501-170">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="07501-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="07501-171">PstnGateway : passerelle 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="07501-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="07501-172">Vrai</span><span class="sxs-lookup"><span data-stu-id="07501-172">True</span></span>      |      <span data-ttu-id="07501-173">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="07501-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="07501-174">PstnGateway : passerelle 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="07501-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="07501-175">False</span><span class="sxs-lookup"><span data-stu-id="07501-175">False</span></span>     |     <span data-ttu-id="07501-176">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="07501-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="07501-177">PstnGateway : passerelle 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="07501-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="07501-178">False</span><span class="sxs-lookup"><span data-stu-id="07501-178">False</span></span>     |    <span data-ttu-id="07501-179">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="07501-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="07501-180">Activer le routage par emplacement pour les stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="07501-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="07501-181">Pour appliquer le routage de géolocalisation pour des utilisateurs spécifiques, configurez la politique vocale des utilisateurs afin d’éviter le contournement des appels PTSN.</span><span class="sxs-lookup"><span data-stu-id="07501-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="07501-182">Utilisez l’applet de passe [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) pour activer le routage géolocalisation en prévenant le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="07501-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="07501-183">Dans cet exemple, nous empêcherons le contournement du numéro de téléphone PSTN aux politiques d’appel de la fonction utilisateur1.</span><span class="sxs-lookup"><span data-stu-id="07501-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="07501-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07501-184">Related topics</span></span>
- [<span data-ttu-id="07501-185">Planifier le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="07501-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="07501-186">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="07501-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="07501-187">Terminologie du routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="07501-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
