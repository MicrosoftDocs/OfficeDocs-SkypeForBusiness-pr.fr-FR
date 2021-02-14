---
title: Optimisation directe des médias locaux de routage
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurer l’optimisation des médias locaux pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576986"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="d999d-103">Configurer l’optimisation des médias locaux pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="d999d-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="d999d-104">La configuration de l’optimisation des médias locaux est basée sur des paramètres réseau courants avec d’autres fonctionnalités voix cloud, telles que le routage Location-Based et les appels d’urgence dynamiques.</span><span class="sxs-lookup"><span data-stu-id="d999d-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="d999d-105">Pour en savoir plus sur les régions réseau, les sites réseau, les sous-réseaux et les adresses IP de confiance, voir Paramètres réseau des [fonctionnalités vocales cloud.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d999d-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="d999d-106">Avant de configurer l’optimisation des médias locaux, consultez l’optimisation des médias [locaux pour le routage direct.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="d999d-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="d999d-107">Pour configurer l’optimisation des médias locaux, les étapes suivantes sont requises.</span><span class="sxs-lookup"><span data-stu-id="d999d-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="d999d-108">Vous pouvez utiliser le Centre d’administration Teams ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d999d-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="d999d-109">Pour plus d’informations, [voir Gérer votre topologie de réseau.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="d999d-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="d999d-110">Configurez l’utilisateur et les sites SBC (comme décrit dans cet article).</span><span class="sxs-lookup"><span data-stu-id="d999d-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="d999d-111">Configurez les SBC pour l’optimisation des médias locaux (conformément à la spécification de votre fournisseur SBC).</span><span class="sxs-lookup"><span data-stu-id="d999d-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="d999d-112">Le diagramme suivant illustre la configuration réseau utilisée dans les exemples tout au long de cet article.</span><span class="sxs-lookup"><span data-stu-id="d999d-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="d999d-113">![Diagramme montrant la configuration réseau pour des exemples](media/direct-routing-media-op-9.png "Configuration réseau pour des exemples")</span><span class="sxs-lookup"><span data-stu-id="d999d-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="d999d-114">Configurer l’utilisateur et les sites SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="d999d-115">Pour configurer l’utilisateur et les sites SBC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="d999d-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="d999d-116">[Gérer les adresses IP de confiance externes.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="d999d-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="d999d-117">[Définissez la topologie de](#define-the-network-topology) réseau en configurant les régions réseau, les sites réseau et les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="d999d-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="d999d-118">[Définissez la topologie](#define-the-virtual-network-topology) de réseau virtuel en attribuant un ou plusieurs SBC aux sites avec les modes appropriés et les valeurs SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="d999d-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="d999d-119">Configurez le ou les SBC pour l’optimisation des médias locaux en fonction de la spécification du fournisseur SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="d999d-120">Cet article décrit la configuration des composants Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d999d-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="d999d-121">Pour plus d’informations sur la configuration SBC, consultez la documentation de votre fournisseur SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="d999d-122">L’optimisation des médias locaux est prise en charge par les fournisseurs SBC suivants :</span><span class="sxs-lookup"><span data-stu-id="d999d-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="d999d-123">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="d999d-123">Vendor</span></span> | <span data-ttu-id="d999d-124">Product</span><span class="sxs-lookup"><span data-stu-id="d999d-124">Product</span></span> |    <span data-ttu-id="d999d-125">Version logicielle</span><span class="sxs-lookup"><span data-stu-id="d999d-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="d999d-126">CodesAudio</span><span class="sxs-lookup"><span data-stu-id="d999d-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="d999d-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="d999d-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="d999d-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="d999d-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="d999d-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="d999d-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="d999d-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="d999d-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d999d-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="d999d-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d999d-142">7.20A.256</span></span> |
| [<span data-ttu-id="d999d-143">Core SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="d999d-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="d999d-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="d999d-144">SBC 5110</span></span>         | <span data-ttu-id="d999d-145">8.2</span><span class="sxs-lookup"><span data-stu-id="d999d-145">8.2</span></span>  |
|            |  <span data-ttu-id="d999d-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="d999d-146">SBC 5210</span></span>         | <span data-ttu-id="d999d-147">8.2</span><span class="sxs-lookup"><span data-stu-id="d999d-147">8.2</span></span>  |
|            |  <span data-ttu-id="d999d-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="d999d-148">SBC 5400</span></span>         | <span data-ttu-id="d999d-149">8.2</span><span class="sxs-lookup"><span data-stu-id="d999d-149">8.2</span></span>  |
|            |  <span data-ttu-id="d999d-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="d999d-150">SBC 7000</span></span>         | <span data-ttu-id="d999d-151">8.2</span><span class="sxs-lookup"><span data-stu-id="d999d-151">8.2</span></span>  |
|            |  <span data-ttu-id="d999d-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="d999d-152">SBC SWe</span></span>          | <span data-ttu-id="d999d-153">8.2</span><span class="sxs-lookup"><span data-stu-id="d999d-153">8.2</span></span>  |
| [<span data-ttu-id="d999d-154">Ruban SBC Edge</span><span class="sxs-lookup"><span data-stu-id="d999d-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="d999d-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="d999d-155">SBC SWe Lite</span></span> | <span data-ttu-id="d999d-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d999d-156">8.1.5</span></span> |
|               | <span data-ttu-id="d999d-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="d999d-157">SBC 1000</span></span> | <span data-ttu-id="d999d-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d999d-158">8.1.5</span></span>  |
|               | <span data-ttu-id="d999d-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="d999d-159">SBC 2000</span></span> | <span data-ttu-id="d999d-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d999d-160">8.1.5</span></span>  |
| [<span data-ttu-id="d999d-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="d999d-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="d999d-162">anynode</span><span class="sxs-lookup"><span data-stu-id="d999d-162">anynode</span></span>          | <span data-ttu-id="d999d-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="d999d-163">4.0.1+</span></span> |
| [<span data-ttu-id="d999d-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="d999d-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="d999d-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="d999d-165">AP 1100</span></span> | <span data-ttu-id="d999d-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d999d-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="d999d-167">AP 3900</span></span> | <span data-ttu-id="d999d-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d999d-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="d999d-169">AP 4600</span></span> | <span data-ttu-id="d999d-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d999d-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="d999d-171">AP 6300</span></span> | <span data-ttu-id="d999d-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d999d-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="d999d-173">AP 6350</span></span> | <span data-ttu-id="d999d-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d999d-175">VME</span><span class="sxs-lookup"><span data-stu-id="d999d-175">VME</span></span>     | <span data-ttu-id="d999d-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d999d-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="d999d-177">Gérer les adresses IP de confiance externes</span><span class="sxs-lookup"><span data-stu-id="d999d-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="d999d-178">Les IPS fiables externes sont les IPS externes Internet du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d999d-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="d999d-179">Ces adresses IP sont les adresses IP utilisées par les clients Microsoft Teams lorsqu’ils se connectent à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d999d-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="d999d-180">Vous devez ajouter ces IPS externes pour chaque site où vous avez des utilisateurs utilisant l’optimisation des médias locaux.</span><span class="sxs-lookup"><span data-stu-id="d999d-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="d999d-181">Pour ajouter les adresses IP publiques pour chaque site, utilisez l'New-CsTenantTrustedIPAddress cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="d999d-182">Vous pouvez définir un nombre illimité d’adresses IP fiables pour un client.</span><span class="sxs-lookup"><span data-stu-id="d999d-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="d999d-183">Si les adresses IP externes vues par Microsoft 365 sont des adresses IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="d999d-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="d999d-184">Pour IPv4, utilisez le masque 32.</span><span class="sxs-lookup"><span data-stu-id="d999d-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="d999d-185">Pour IPv6, utilisez le masque 128.</span><span class="sxs-lookup"><span data-stu-id="d999d-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="d999d-186">Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant différents masques sur l’cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="d999d-187">Exemple d’ajout d’adresses IP fiables.</span><span class="sxs-lookup"><span data-stu-id="d999d-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="d999d-188">Définir la topologie de réseau</span><span class="sxs-lookup"><span data-stu-id="d999d-188">Define the network topology</span></span>

<span data-ttu-id="d999d-189">Cette section décrit comment définir les régions réseau, les sites réseau et les sous-réseaux pour votre topologie de réseau.</span><span class="sxs-lookup"><span data-stu-id="d999d-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="d999d-190">Tous les paramètres respectent la cas. Vous devez donc vous assurer d’utiliser le même cas que lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="d999d-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="d999d-191">(Par exemple, les valeurs GatewaySiteID « Vietnam » et « vietnam » seront traitées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="d999d-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="d999d-192">Définir les régions réseau</span><span class="sxs-lookup"><span data-stu-id="d999d-192">Define network regions</span></span>

<span data-ttu-id="d999d-193">Pour définir les régions du réseau, utilisez l'New-CsTenantNetworkRegion de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="d999d-194">Le paramètre RegionID est un nom logique qui représente la géographie de la région et ne présente aucune dépendance ou restriction.</span><span class="sxs-lookup"><span data-stu-id="d999d-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="d999d-195">Le paramètre CentralSite <site ID> est facultatif.</span><span class="sxs-lookup"><span data-stu-id="d999d-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="d999d-196">L’exemple suivant crée une région réseau nommée APAC :</span><span class="sxs-lookup"><span data-stu-id="d999d-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="d999d-197">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="d999d-197">Define network sites</span></span>

<span data-ttu-id="d999d-198">Pour définir des sites réseau, utilisez l'New-CsTenantNetworkSite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="d999d-199">Chaque site réseau doit être associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="d999d-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="d999d-200">L’exemple suivant crée trois nouveaux sites réseau( Vietnam, Indonésie et Singapour) dans la région APAC :</span><span class="sxs-lookup"><span data-stu-id="d999d-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="d999d-201">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="d999d-201">Define network subnets</span></span>

<span data-ttu-id="d999d-202">Pour définir des sous-réseaux et les associer à des sites réseau, utilisez New-CsTenantNetworkSubnet cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d999d-203">Chaque sous-réseau ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="d999d-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="d999d-204">L’exemple suivant définit trois sous-réseaux et les associe aux trois sites réseau : Vietnam, Indonésie et Singapour :</span><span class="sxs-lookup"><span data-stu-id="d999d-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="d999d-205">Définir la topologie de réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="d999d-205">Define the virtual network topology</span></span> 

<span data-ttu-id="d999d-206">Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC pertinent à l’aide de lNew-CsOnlinePSTNGateway dlet.</span><span class="sxs-lookup"><span data-stu-id="d999d-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="d999d-207">L’administrateur client définit la topologie de réseau virtuel en spécifiant les sites réseau pour les objets de passerelle PSTN à l’aide de l'Set-CsOnlinePSTNGateway cmdlet :</span><span class="sxs-lookup"><span data-stu-id="d999d-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="d999d-208">Notez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d999d-208">Note the following:</span></span> 
   - <span data-ttu-id="d999d-209">Si le client n’a qu’un SBC, le paramètre -ProxySBC doit être obligatoire au $null ou au FQDN SBC (SBC central avec scénario de ligne centralisée).</span><span class="sxs-lookup"><span data-stu-id="d999d-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="d999d-210">Le paramètre -MediaBypass doit être réglé sur $true pour prendre en charge l’optimisation des médias locaux.</span><span class="sxs-lookup"><span data-stu-id="d999d-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="d999d-211">Si le paramètre SBC n’a pas de paramètre -BypassMode, les en-têtes X-MS ne seront pas envoyés.</span><span class="sxs-lookup"><span data-stu-id="d999d-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="d999d-212">Tous les paramètres respectent la cas. Vous devez donc vous assurer d’utiliser le même cas que celui utilisé lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="d999d-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="d999d-213">(Par exemple, les valeurs GatewaySiteID « Vietnam » et « vietnam » seront traitées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="d999d-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="d999d-214">L’exemple suivant ajoute trois SBE aux sites réseau vietnam, Indonésie et Singapour dans la région APAC avec le mode Toujours contourner :</span><span class="sxs-lookup"><span data-stu-id="d999d-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="d999d-215">Remarque : pour garantir la interruption des opérations lorsque l’optimisation des médias locaux et le routage Location-Based sont configurés en même temps, les SLB en aval doivent être activés pour LBR en configurant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval.</span><span class="sxs-lookup"><span data-stu-id="d999d-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="d999d-216">(Ce paramètre n’est pas obligatoire pour le SBC proxy.)</span><span class="sxs-lookup"><span data-stu-id="d999d-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="d999d-217">D’après les informations ci-dessus, le routage direct inclura trois en-têtes SIP propriétaires pour les invitations et les invitations siP, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d999d-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="d999d-218">En-têtes X-MS introduits dans le routage direct dans les invitations et les Re-Invites si BypassMode est défini :</span><span class="sxs-lookup"><span data-stu-id="d999d-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="d999d-219">Nom de l’en-tête</span><span class="sxs-lookup"><span data-stu-id="d999d-219">Header name</span></span> | <span data-ttu-id="d999d-220">Valeurs</span><span class="sxs-lookup"><span data-stu-id="d999d-220">Values</span></span> | <span data-ttu-id="d999d-221">Commentaires</span><span class="sxs-lookup"><span data-stu-id="d999d-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="d999d-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="d999d-222">X-MS-UserLocation</span></span> | <span data-ttu-id="d999d-223">interne/externe</span><span class="sxs-lookup"><span data-stu-id="d999d-223">internal/external</span></span> | <span data-ttu-id="d999d-224">Indique si l’utilisateur est interne ou externe</span><span class="sxs-lookup"><span data-stu-id="d999d-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="d999d-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="d999d-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="d999d-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="d999d-226">SBC FQDN</span></span> | <span data-ttu-id="d999d-227">FQDN ciblé pour l’appel même si le SBC n’est pas connecté directement au routage direct</span><span class="sxs-lookup"><span data-stu-id="d999d-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="d999d-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="d999d-228">X-MS-MediaPath</span></span> | <span data-ttu-id="d999d-229">Exemple : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="d999d-230">Ordre des SBC à utiliser pour le chemin de médias entre l’utilisateur et la cible SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="d999d-231">Le SBC final est toujours le dernier</span><span class="sxs-lookup"><span data-stu-id="d999d-231">The final SBC is always last</span></span> |
| <span data-ttu-id="d999d-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="d999d-232">X-MS-UserSite</span></span> | <span data-ttu-id="d999d-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="d999d-233">usersiteID</span></span> | <span data-ttu-id="d999d-234">Chaîne définie par l’administrateur client</span><span class="sxs-lookup"><span data-stu-id="d999d-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="d999d-235">Flux d’appels</span><span class="sxs-lookup"><span data-stu-id="d999d-235">Call flows</span></span> 

<span data-ttu-id="d999d-236">L’exemple suivant illustre les flux d’appels pour deux modes :</span><span class="sxs-lookup"><span data-stu-id="d999d-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="d999d-237">Toujours contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="d999d-238">Uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="d999d-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="d999d-239">Toujours contourner le mode</span><span class="sxs-lookup"><span data-stu-id="d999d-239">Always Bypass mode</span></span>

<span data-ttu-id="d999d-240">Le mode Contournement est l’option la plus simple à configurer.</span><span class="sxs-lookup"><span data-stu-id="d999d-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="d999d-241">L’administrateur client peut configurer un site unique pour tous les utilisateurs et SBCS si tous les SBCs sont accessibles à partir de n’importe quel site.</span><span class="sxs-lookup"><span data-stu-id="d999d-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="d999d-242">Les exemples montrent le mode De contournement toujours pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="d999d-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="d999d-243">Appels sortants et l’utilisateur se trouve au même emplacement que le SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d999d-244">Appels entrants et l’utilisateur se trouve au même emplacement que le SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d999d-245">Appels sortants et utilisateur externe</span><span class="sxs-lookup"><span data-stu-id="d999d-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="d999d-246">Appels entrants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="d999d-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="d999d-247">Le tableau suivant indique le FQDN et les adresses IP utilisés dans les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="d999d-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="d999d-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="d999d-248">FQDN</span></span> | <span data-ttu-id="d999d-249">Adresse IP externe SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-249">SBC external IP address</span></span> | <span data-ttu-id="d999d-250">Adresse IP interne SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-250">SBC internal IP Address</span></span> | <span data-ttu-id="d999d-251">Sous-réseau interne</span><span class="sxs-lookup"><span data-stu-id="d999d-251">Internal subnet</span></span> | <span data-ttu-id="d999d-252">Lieu</span><span class="sxs-lookup"><span data-stu-id="d999d-252">Location</span></span> | <span data-ttu-id="d999d-253">NAT externe (adresse IP fiable)</span><span class="sxs-lookup"><span data-stu-id="d999d-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="d999d-255">Aucun</span><span class="sxs-lookup"><span data-stu-id="d999d-255">None</span></span> | <span data-ttu-id="d999d-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="d999d-256">192.168.1.5</span></span> | <span data-ttu-id="d999d-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="d999d-257">192.168.1.0/24</span></span> | <span data-ttu-id="d999d-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="d999d-258">Vietnam</span></span> | <span data-ttu-id="d999d-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="d999d-259">172.16.240.110</span></span> |
| <span data-ttu-id="d999d-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="d999d-261">Aucun</span><span class="sxs-lookup"><span data-stu-id="d999d-261">None</span></span> | <span data-ttu-id="d999d-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="d999d-262">192.168.2.5</span></span> | <span data-ttu-id="d999d-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="d999d-263">192.168.2.0/24</span></span> | <span data-ttu-id="d999d-264">Indonésie</span><span class="sxs-lookup"><span data-stu-id="d999d-264">Indonesia</span></span> | <span data-ttu-id="d999d-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="d999d-265">172.16.240.120</span></span> |
| <span data-ttu-id="d999d-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="d999d-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="d999d-267">172.16.240.133</span></span> | <span data-ttu-id="d999d-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="d999d-268">192.168.3.5</span></span> | <span data-ttu-id="d999d-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="d999d-269">192.168.3.0/24</span></span> | <span data-ttu-id="d999d-270">Singapour</span><span class="sxs-lookup"><span data-stu-id="d999d-270">Singapore</span></span> | <span data-ttu-id="d999d-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="d999d-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d999d-272">Appels sortants et l’utilisateur se trouve au même emplacement que le SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="d999d-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d999d-273">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-273">Mode</span></span> |    <span data-ttu-id="d999d-274">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-274">User</span></span> |  <span data-ttu-id="d999d-275">Lieu</span><span class="sxs-lookup"><span data-stu-id="d999d-275">Location</span></span> |  <span data-ttu-id="d999d-276">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="d999d-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d999d-277">AlwaysBypass</span></span> |    <span data-ttu-id="d999d-278">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-278">Internal</span></span> |  <span data-ttu-id="d999d-279">Le même site que SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-279">The same site as SBC</span></span> |  <span data-ttu-id="d999d-280">Sortant</span><span class="sxs-lookup"><span data-stu-id="d999d-280">Outbound</span></span> |

<span data-ttu-id="d999d-281">Le tableau suivant indique la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="d999d-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="d999d-282">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-282">User physical location</span></span>| <span data-ttu-id="d999d-283">Un utilisateur effectue ou reçoit un appel vers/depuis un numéro</span><span class="sxs-lookup"><span data-stu-id="d999d-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="d999d-284">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-284">User phone number</span></span>  | <span data-ttu-id="d999d-285">Stratégie de routage vocal en ligne</span><span class="sxs-lookup"><span data-stu-id="d999d-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="d999d-286">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="d999d-287">Vietnam</span></span> | <span data-ttu-id="d999d-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d999d-288">+84 4 3926 3000</span></span> | <span data-ttu-id="d999d-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d999d-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="d999d-290">Priorité 1 : ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d999d-291">Priorité 2 : .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="d999d-292">VNsbc.contoso.com – Toujours contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="d999d-293">proxysbc.contoso.com – Toujours contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="d999d-294">Le diagramme suivant montre l’évolution SIP d’un appel sortant avec le mode de contournement Toujours et l’utilisateur situé au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="d999d-295">![Diagramme montrant les appels sortants](media/direct-routing-media-op-10.png "Appels sortants")</span><span class="sxs-lookup"><span data-stu-id="d999d-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="d999d-296">Le tableau suivant indique les en-têtes X-MS envoyés par routage direct :</span><span class="sxs-lookup"><span data-stu-id="d999d-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="d999d-297">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d999d-297">Parameter</span></span> | <span data-ttu-id="d999d-298">Explication</span><span class="sxs-lookup"><span data-stu-id="d999d-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="d999d-299">Inviter+8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d999d-300">Le nom de sécurité (FQDN) cible du SBC défini dans la stratégie de routage voix en ligne est envoyé dans l’URI de demande</span><span class="sxs-lookup"><span data-stu-id="d999d-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="d999d-301">X-MS-UserLocation : interne</span><span class="sxs-lookup"><span data-stu-id="d999d-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="d999d-302">Le champ indique que l’utilisateur se trouve dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d999d-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="d999d-303">X-MS-MediaPath : VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="d999d-304">Spécifie le SBC que le client doit traverser jusqu’au SBC cible.</span><span class="sxs-lookup"><span data-stu-id="d999d-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d999d-305">Dans ce cas, comme nous avons Toujours contournement, et le client est interne au nom de la cible envoyé en tant que seul nom dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="d999d-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="d999d-306">X-MS-UserSite : Vietnam</span><span class="sxs-lookup"><span data-stu-id="d999d-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="d999d-307">Champ indiqué sur le site où se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d999d-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d999d-308">Appels entrants et l’utilisateur se trouve au même emplacement que le SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="d999d-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d999d-309">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-309">Mode</span></span> |    <span data-ttu-id="d999d-310">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-310">User</span></span> |  <span data-ttu-id="d999d-311">Lieu</span><span class="sxs-lookup"><span data-stu-id="d999d-311">Location</span></span> |  <span data-ttu-id="d999d-312">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d999d-313">AlwaysBypass</span></span> |    <span data-ttu-id="d999d-314">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-314">Internal</span></span> | <span data-ttu-id="d999d-315">Le même site que SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-315">The same site as SBC</span></span> | <span data-ttu-id="d999d-316">Entrant</span><span class="sxs-lookup"><span data-stu-id="d999d-316">Inbound</span></span> |


<span data-ttu-id="d999d-317">Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et le SBC doit deviner où se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d999d-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="d999d-318">Si l’estimation n’est pas correcte, une nouvelle invitation est requise.</span><span class="sxs-lookup"><span data-stu-id="d999d-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="d999d-319">Ce cas suppose que l’utilisateur est interne, que les médias peuvent circuler directement et qu’aucune autre action n’est requise (nouvelle invitation).</span><span class="sxs-lookup"><span data-stu-id="d999d-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="d999d-320">Le SBC connecté au service de routage direct signale l’emplacement SBC d’origine en fournissant des champs Record-Route et Contact.</span><span class="sxs-lookup"><span data-stu-id="d999d-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="d999d-321">Sur la base de ces champs, le chemin de médias est calculé par routage direct.</span><span class="sxs-lookup"><span data-stu-id="d999d-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="d999d-322">Remarque : Étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge de 183 n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="d999d-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="d999d-323">Dans ce cas, le routage direct utilise toujours 180 sonneries.</span><span class="sxs-lookup"><span data-stu-id="d999d-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="d999d-324">Le diagramme suivant montre l’évolution SIP d’un appel entrant avec le mode AlwaysBypass, et l’utilisateur se trouve au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d999d-326">Appels sortants et l’utilisateur est externe avec Toujours contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d999d-327">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-327">Mode</span></span> |    <span data-ttu-id="d999d-328">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-328">User</span></span> |  <span data-ttu-id="d999d-329">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-329">Site</span></span> |  <span data-ttu-id="d999d-330">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d999d-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d999d-331">AlwaysBypass</span></span> |  <span data-ttu-id="d999d-332">Externe</span><span class="sxs-lookup"><span data-stu-id="d999d-332">External</span></span> |  <span data-ttu-id="d999d-333">S/O</span><span class="sxs-lookup"><span data-stu-id="d999d-333">N/A</span></span> | <span data-ttu-id="d999d-334">Sortant</span><span class="sxs-lookup"><span data-stu-id="d999d-334">Outbound</span></span> |


<span data-ttu-id="d999d-335">Le diagramme suivant illustre l’évolution SIP d’un appel sortant avec le mode AlwaysBypass et l’utilisateur est externe :</span><span class="sxs-lookup"><span data-stu-id="d999d-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="d999d-337">Le tableau suivant indique les en-têtes X-MS envoyés par le service de routage direct :</span><span class="sxs-lookup"><span data-stu-id="d999d-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="d999d-338">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d999d-338">Parameter</span></span> |   <span data-ttu-id="d999d-339">Explication</span><span class="sxs-lookup"><span data-stu-id="d999d-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="d999d-340">Inviter+8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d999d-341">Le nom de fQDN cible du SBC défini dans la stratégie de routage voix en ligne est envoyé dans l’URI de demande.</span><span class="sxs-lookup"><span data-stu-id="d999d-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="d999d-342">X-MS-UserLocation : externe</span><span class="sxs-lookup"><span data-stu-id="d999d-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="d999d-343">Le champ indique que l’utilisateur se trouve en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d999d-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="d999d-344">X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="d999d-345">Spécifie le SBC que le client doit traverser jusqu’au SBC cible.</span><span class="sxs-lookup"><span data-stu-id="d999d-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d999d-346">Dans ce cas, nous avons Toujours contourné et le client est externe.</span><span class="sxs-lookup"><span data-stu-id="d999d-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d999d-347">Appels entrants et l’utilisateur est externe avec Toujours contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d999d-348">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-348">Mode</span></span> | <span data-ttu-id="d999d-349">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-349">User</span></span> | <span data-ttu-id="d999d-350">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-350">Site</span></span> |  <span data-ttu-id="d999d-351">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d999d-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d999d-352">AlwaysBypass</span></span> |  <span data-ttu-id="d999d-353">Externe</span><span class="sxs-lookup"><span data-stu-id="d999d-353">External</span></span> |  <span data-ttu-id="d999d-354">S/O</span><span class="sxs-lookup"><span data-stu-id="d999d-354">N/A</span></span> |   <span data-ttu-id="d999d-355">Entrant</span><span class="sxs-lookup"><span data-stu-id="d999d-355">Inbound</span></span> |

<span data-ttu-id="d999d-356">Pour un appel entrant, le SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les supports multimédias locaux sont toujours proposés) si l’emplacement de l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="d999d-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="d999d-357">Le X-MediaPath est calculé sur la base des Record-Route et de l’utilisateur SBC spécifié.</span><span class="sxs-lookup"><span data-stu-id="d999d-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="d999d-358">Le diagramme suivant illustre l’évolution SIP d’un appel entrant avec le mode AlwaysBypass et l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="d999d-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="d999d-360">Uniquement pour le mode utilisateur local</span><span class="sxs-lookup"><span data-stu-id="d999d-360">Only for local users mode</span></span>

<span data-ttu-id="d999d-361">Les supports multimédias locaux du SBC cible ne seront proposés que si un utilisateur se trouve au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="d999d-362">Dans tous les autres cas, les médias circulent via une adresse IP interne ou externe du proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="d999d-363">Les scénarios suivants sont décrits :</span><span class="sxs-lookup"><span data-stu-id="d999d-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="d999d-364">Appels sortants et l’utilisateur se trouve au même emplacement que le SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d999d-365">Appels entrants et l’utilisateur se trouve au même emplacement que le SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d999d-366">L’utilisateur n’est pas au même emplacement que le SBC, mais se trouve dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d999d-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="d999d-367">Appels entrants et l’utilisateur est interne, mais n’est pas au même emplacement que le SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="d999d-368">Le tableau suivant indique la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="d999d-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="d999d-369">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-369">User physical location</span></span> |  <span data-ttu-id="d999d-370">Un utilisateur effectue ou reçoit un appel vers/depuis un numéro</span><span class="sxs-lookup"><span data-stu-id="d999d-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="d999d-371">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-371">User phone number</span></span> | <span data-ttu-id="d999d-372">Stratégie de routage vocal en ligne</span><span class="sxs-lookup"><span data-stu-id="d999d-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="d999d-373">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="d999d-374">Vietnam</span></span> | <span data-ttu-id="d999d-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d999d-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="d999d-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d999d-376">+84 4 5555 5555</span></span> | <span data-ttu-id="d999d-377">Priorité 1 : ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d999d-378">Priorité 2 : .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d999d-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="d999d-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Toujours Contourner</span><span class="sxs-lookup"><span data-stu-id="d999d-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d999d-380">Appels sortants et l’utilisateur se trouve au même emplacement que le SBC avec uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="d999d-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d999d-381">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-381">Mode</span></span> | <span data-ttu-id="d999d-382">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-382">User</span></span> | <span data-ttu-id="d999d-383">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-383">Site</span></span> | <span data-ttu-id="d999d-384">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d999d-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d999d-386">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-386">Internal</span></span> |<span data-ttu-id="d999d-387">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-387">Same as SBC</span></span>   | <span data-ttu-id="d999d-388">Sortant</span><span class="sxs-lookup"><span data-stu-id="d999d-388">Outbound</span></span> |

<span data-ttu-id="d999d-389">Le diagramme suivant illustre un appel sortant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d999d-390">Il s’agit du même flux affiché dans les appels sortants lorsque l’utilisateur se trouve au même emplacement [que le SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="d999d-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d999d-392">Appels entrants et l’utilisateur se trouve au même emplacement que le SBC avec uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="d999d-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d999d-393">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-393">Mode</span></span> | <span data-ttu-id="d999d-394">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-394">User</span></span> | <span data-ttu-id="d999d-395">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-395">Site</span></span> | <span data-ttu-id="d999d-396">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d999d-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d999d-398">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-398">Internal</span></span> | <span data-ttu-id="d999d-399">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-399">Same as SBC</span></span> | <span data-ttu-id="d999d-400">Entrant</span><span class="sxs-lookup"><span data-stu-id="d999d-400">Inbound</span></span> |

<span data-ttu-id="d999d-401">Le diagramme suivant montre un appel entrant en mode OnlyForLocalUsers, et l’utilisateur se trouve au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d999d-402">Il s’agit du même flux que celui affiché dans les appels entrants lorsque l’utilisateur se trouve au même emplacement [que le SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="d999d-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="d999d-404">L’utilisateur n’est pas au même emplacement que le SBC, mais se trouve sur le réseau d’entreprise avec uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="d999d-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="d999d-405">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-405">Mode</span></span> | <span data-ttu-id="d999d-406">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-406">User</span></span> | <span data-ttu-id="d999d-407">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-407">Site</span></span> |<span data-ttu-id="d999d-408">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d999d-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="d999d-410">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-410">Internal</span></span> |   <span data-ttu-id="d999d-411">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-411">Different from SBC</span></span> | <span data-ttu-id="d999d-412">Sortant</span><span class="sxs-lookup"><span data-stu-id="d999d-412">Outbound</span></span> |

<span data-ttu-id="d999d-413">Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configuré sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="d999d-414">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d999d-416">Appel entrant et l’utilisateur est interne, mais n’est pas au même emplacement que le SBC avec uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="d999d-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d999d-417">Mode</span><span class="sxs-lookup"><span data-stu-id="d999d-417">Mode</span></span> |    <span data-ttu-id="d999d-418">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d999d-418">User</span></span> |  <span data-ttu-id="d999d-419">Site</span><span class="sxs-lookup"><span data-stu-id="d999d-419">Site</span></span> |  <span data-ttu-id="d999d-420">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="d999d-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d999d-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d999d-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="d999d-422">Interne</span><span class="sxs-lookup"><span data-stu-id="d999d-422">Internal</span></span> |    <span data-ttu-id="d999d-423">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="d999d-423">Different from SBC</span></span> |    <span data-ttu-id="d999d-424">Entrant</span><span class="sxs-lookup"><span data-stu-id="d999d-424">Inbound</span></span> |

<span data-ttu-id="d999d-425">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que le SBC.</span><span class="sxs-lookup"><span data-stu-id="d999d-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’évolution de SIP](media/direct-routing-media-op-17.png)









