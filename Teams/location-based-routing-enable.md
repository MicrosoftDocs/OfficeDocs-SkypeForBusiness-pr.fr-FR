---
title: Activer le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment activer le routage par emplacement pour le routage direct, y compris pour l’activation pour les utilisateurs, les sites réseau, les configurations de passerelle et les stratégies d’appel.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412641"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="1ee0f-103">Activer le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="1ee0f-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1ee0f-104">Avant de suivre les étapes décrites dans cet article, assurez-vous d’avoir lu le [routage de l’emplacement de votre plan pour le routage direct](location-based-routing-plan.md) et effectué les étapes décrites dans [configurer les paramètres réseau pour le routage via emplacement](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="1ee0f-105">Cet article explique comment activer le routage sur la base de l’emplacement pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="1ee0f-106">Après le déploiement du routage direct du système téléphonique et la configuration des zones, des sites et des sous-réseaux, vous pouvez activer le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="1ee0f-107">Pour suivre les étapes décrites dans cet article, vous devez être familiarisé avec les applets de méthode PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1ee0f-108">Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="1ee0f-109">Vous devez activer le routage par emplacement pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1ee0f-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="1ee0f-110">Users</span><span class="sxs-lookup"><span data-stu-id="1ee0f-110">Users</span></span>
- <span data-ttu-id="1ee0f-111">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="1ee0f-111">Network sites</span></span>
- <span data-ttu-id="1ee0f-112">Configurations des passerelles</span><span class="sxs-lookup"><span data-stu-id="1ee0f-112">Gateway configurations</span></span>
- <span data-ttu-id="1ee0f-113">Stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="1ee0f-113">Calling policies</span></span>

<span data-ttu-id="1ee0f-114">Vous pouvez utiliser le [Centre d’administration Microsoft Team](#using-the-microsoft-teams-admin-center) ou [PowerShel](#using-powershell)l pour activer le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1ee0f-115">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee0f-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1ee0f-116">Activer le routage basé sur l’emplacement pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ee0f-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1ee0f-117">Créez une stratégie de routage de la voix et attribuez des utilisations PSTN à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="1ee0f-118">Lorsque vous attribuez des utilisations RTC à une stratégie, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ee0f-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="1ee0f-119">Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="1ee0f-120">Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où les restrictions de routage basées sur les emplacements ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="1ee0f-121">Affectez la stratégie de routage vocale aux utilisateurs qui requièrent l’application de restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="1ee0f-122">Pour en savoir plus sur la création de stratégies de routage de messagerie et leur attribution aux utilisateurs, voir [gérer les stratégies de routage de messagerie vocale dans Microsoft teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1ee0f-123">Activer le routage par emplacement pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="1ee0f-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="1ee0f-124">Activez le routage selon l’emplacement pour vos sites qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="1ee0f-125">Pour ce faire, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **emplacements**  >  **réseau**, sélectionnez un site réseau, cliquez sur **modifier**, puis activez **routage selon l’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="1ee0f-126">Pour en savoir plus, voir [gérer la topologie de votre réseau](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1ee0f-127">Activer le routage basé sur l’emplacement pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="1ee0f-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="1ee0f-128">Activez le routage par emplacement vers des passerelles qui acheminent les appels vers les passerelles RTC qui routent les appels vers le RTC et associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="1ee0f-129">Dans le volet de navigation de gauche **Voice**, sélectionnez  >  **routage direct**de la voix, puis cliquez sur l’onglet **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="1ee0f-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="1ee0f-130">Sélectionnez l’SBC, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="1ee0f-131">Sous **routage d’emplacement et optimisation des éléments multimédias**, activez **activer le routage selon**la localisation.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="1ee0f-132">Spécifiez l’ID du site de la passerelle, puis définissez le mode de contournement.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="1ee0f-133">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1ee0f-134">Activer le routage par emplacement pour les stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="1ee0f-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1ee0f-135">Pour appliquer le routage basé sur l’emplacement pour des utilisateurs spécifiques, configurez la stratégie d’appel de l’utilisateur afin d’éviter le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1ee0f-136">Pour cela, activez le paramètre **empêcher le contournement du numéro** dans la stratégie d’appel.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="1ee0f-137">Pour en savoir plus, voir [stratégies d’appel dans teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="1ee0f-138">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ee0f-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="1ee0f-139">Activer le routage basé sur l’emplacement pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ee0f-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="1ee0f-140">Utilisez l’applet de commande [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) pour définir les utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="1ee0f-141">Pour les utilisations multiples, séparez chaque utilisation par une virgule.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="1ee0f-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1ee0f-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="1ee0f-143">Utilisez l’applet de commande [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) pour créer une stratégie de routage vocal et associer l’utilisateur aux utilisations RTC appropriées.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="1ee0f-144">Lorsque vous attribuez des utilisations RTC à une stratégie de routage vocale, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ee0f-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="1ee0f-145">Utiliser les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site</span><span class="sxs-lookup"><span data-stu-id="1ee0f-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="1ee0f-146">Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où les restrictions de routage basées sur les emplacements ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="1ee0f-147">Dans cet exemple, nous créons deux nouvelles stratégies de routage vocal et affectons des utilisations PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="1ee0f-148">Le tableau suivant répertorie les stratégies de routage vocal définies dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="1ee0f-149">Politique de routage de la voix 1</span><span class="sxs-lookup"><span data-stu-id="1ee0f-149">Voice routing policy 1</span></span>|<span data-ttu-id="1ee0f-150">Politique de routage de la voix 2</span><span class="sxs-lookup"><span data-stu-id="1ee0f-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="1ee0f-151">ID de la stratégie vocale en ligne</span><span class="sxs-lookup"><span data-stu-id="1ee0f-151">Online voice policy ID</span></span>   |<span data-ttu-id="1ee0f-152">Politique de routage vocal de Delhi en ligne</span><span class="sxs-lookup"><span data-stu-id="1ee0f-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="1ee0f-153">Politique de routage de la voix en ligne Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1ee0f-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="1ee0f-154">Utilisations RTC en ligne</span><span class="sxs-lookup"><span data-stu-id="1ee0f-154">Online PSTN usages</span></span>  |<span data-ttu-id="1ee0f-155">Longue distance</span><span class="sxs-lookup"><span data-stu-id="1ee0f-155">Long Distance</span></span>  |<span data-ttu-id="1ee0f-156">Longue distance, local, interne</span><span class="sxs-lookup"><span data-stu-id="1ee0f-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="1ee0f-157">Utilisez l’applet de contrôle [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) pour associer des stratégies de routage vocal en ligne aux utilisateurs qui ont besoin de restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="1ee0f-158">Activer le routage par emplacement pour les sites réseau</span><span class="sxs-lookup"><span data-stu-id="1ee0f-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="1ee0f-159">Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) pour activer le routage par emplacement et associer des stratégies de routage de messagerie à vos sites réseau qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="1ee0f-160">Dans cet exemple, nous activons le routage en fonction de l’emplacement pour le site de Delhi et le site Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="1ee0f-161">Le tableau suivant indique les sites activés pour le routage par emplacement dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="1ee0f-162">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="1ee0f-163">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="1ee0f-164">Nom du site</span><span class="sxs-lookup"><span data-stu-id="1ee0f-164">Site name</span></span>    |<span data-ttu-id="1ee0f-165">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="1ee0f-166">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="1ee0f-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="1ee0f-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="1ee0f-168">Vrai</span><span class="sxs-lookup"><span data-stu-id="1ee0f-168">True</span></span>    |<span data-ttu-id="1ee0f-169">Vrai</span><span class="sxs-lookup"><span data-stu-id="1ee0f-169">True</span></span>    |
    |<span data-ttu-id="1ee0f-170">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="1ee0f-170">Subnets</span></span>     |<span data-ttu-id="1ee0f-171">Sous-réseau 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="1ee0f-172">Sous-réseau 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="1ee0f-173">Activer le routage basé sur l’emplacement pour les passerelles</span><span class="sxs-lookup"><span data-stu-id="1ee0f-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="1ee0f-174">Utilisez l’applet de nouvelle applet de [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) pour créer une configuration de passerelle pour chaque passerelle ou site réseau.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="1ee0f-175">Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer les restrictions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="1ee0f-176">Dans cet exemple, nous créons une configuration de passerelle pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="1ee0f-177">Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="1ee0f-178">Utilisez l’applet de cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) pour activer le routage de géolocalisation des passerelles qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="1ee0f-179">Activez le routage par emplacement vers des passerelles qui acheminent les appels vers les passerelles RTC qui routent les appels vers le RTC et associez le site réseau où se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="1ee0f-180">Dans cet exemple, nous activons le routage en fonction de l’emplacement pour chaque passerelle associée aux passerelles RTC dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="1ee0f-181">N’activez pas le routage basé sur l’emplacement pour les passerelles qui ne routent pas les appels vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="1ee0f-182">Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="1ee0f-183">En effet, les restrictions de routage basées sur l’emplacement doivent être appliquées pour les appels RTC atteignant des points de terminaison qui sont connectés par le biais de cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="1ee0f-184">Dans cet exemple, le routage basé sur l’emplacement n’est pas activé pour chaque passerelle associée aux systèmes PBX dans les sites Delhi et Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="1ee0f-185">Activer le routage par emplacement pour les stratégies d’appel</span><span class="sxs-lookup"><span data-stu-id="1ee0f-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="1ee0f-186">Pour appliquer le routage de géolocalisation pour des utilisateurs spécifiques, configurez la politique vocale des utilisateurs afin d’éviter le contournement des appels PTSN.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="1ee0f-187">Utilisez l’applet de passe [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) pour activer le routage géolocalisation en prévenant le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="1ee0f-188">Dans cet exemple, nous empêcherons le contournement du numéro de téléphone PSTN aux politiques d’appel de la fonction utilisateur1.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="1ee0f-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ee0f-189">Related topics</span></span>

- [<span data-ttu-id="1ee0f-190">Paramètres réseau pour les fonctionnalités vocales de Cloud dans teams</span><span class="sxs-lookup"><span data-stu-id="1ee0f-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
