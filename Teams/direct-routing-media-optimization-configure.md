---
title: Optimisation des éléments multimédias locaux du routage direct
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
description: Configurer l’optimisation locale des médias pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576986"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="cfdd1-103">Configurer l’optimisation locale des médias pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="cfdd1-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="cfdd1-104">La configuration de l’optimisation des éléments multimédias locaux est basée sur les paramètres réseau communs aux autres fonctionnalités de voix Cloud, telles que le routage par emplacement et les appels d’urgence dynamiques.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="cfdd1-105">Pour en savoir plus sur les zones du réseau, les sites réseau, les sous-réseaux réseau et les adresses IP de confiance, voir [paramètres réseau pour les fonctionnalités vocales dans le Cloud](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="cfdd1-106">Avant de configurer l’optimisation de média locale, voir [optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="cfdd1-107">Pour configurer l’optimisation de média locale, les étapes suivantes sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="cfdd1-108">Vous pouvez utiliser le centre d’administration teams ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="cfdd1-109">Pour plus d’informations, voir [gérer la topologie de votre réseau](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="cfdd1-110">Configurez les sites utilisateur et SBC (comme décrit dans cet article).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="cfdd1-111">Configurez l’application SBCs pour l’optimisation de média locale (en fonction de la spécification de votre fournisseur SBC).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="cfdd1-112">Le diagramme suivant montre la configuration du réseau utilisée dans les exemples de cet article.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="cfdd1-113">![Diagramme illustrant la configuration réseau pour les exemples](media/direct-routing-media-op-9.png "Configuration du réseau pour les exemples")</span><span class="sxs-lookup"><span data-stu-id="cfdd1-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="cfdd1-114">Configurer l’utilisateur et les sites SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="cfdd1-115">Pour configurer l’utilisateur et les sites SBC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="cfdd1-116">[Gérer les adresses IP de confiance externes](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="cfdd1-117">[Définissez la topologie du réseau](#define-the-network-topology) en configurant les zones du réseau, les sites réseau et les sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="cfdd1-118">[Définissez la topologie du réseau virtuel](#define-the-virtual-network-topology) en assignant des SBC (s) aux sites avec des modes pertinents et des valeurs SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="cfdd1-119">Configurer des SBC pour optimiser les médias locaux conformément à la spécification du fournisseur de SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="cfdd1-120">Cet article décrit la configuration des composants Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="cfdd1-121">Pour plus d’informations sur la configuration d’un SBC, consultez la documentation de votre fournisseur SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="cfdd1-122">L’optimisation des éléments multimédias locaux est prise en charge par les fournisseurs de SBC suivants :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="cfdd1-123">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-123">Vendor</span></span> | <span data-ttu-id="cfdd1-124">Product</span><span class="sxs-lookup"><span data-stu-id="cfdd1-124">Product</span></span> |    <span data-ttu-id="cfdd1-125">Version du logiciel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="cfdd1-126">CodesAudio</span><span class="sxs-lookup"><span data-stu-id="cfdd1-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="cfdd1-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="cfdd1-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="cfdd1-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="cfdd1-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="cfdd1-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-135">1000B SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="cfdd1-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-137">SBC-9000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="cfdd1-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-139">SBC-édition virtuelle-SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="cfdd1-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="cfdd1-141">SBC édition Cloud-SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="cfdd1-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="cfdd1-142">7.20A.256</span></span> |
| [<span data-ttu-id="cfdd1-143">Noyau SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="cfdd1-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="cfdd1-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="cfdd1-144">SBC 5110</span></span>         | <span data-ttu-id="cfdd1-145">8,2</span><span class="sxs-lookup"><span data-stu-id="cfdd1-145">8.2</span></span>  |
|            |  <span data-ttu-id="cfdd1-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="cfdd1-146">SBC 5210</span></span>         | <span data-ttu-id="cfdd1-147">8,2</span><span class="sxs-lookup"><span data-stu-id="cfdd1-147">8.2</span></span>  |
|            |  <span data-ttu-id="cfdd1-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="cfdd1-148">SBC 5400</span></span>         | <span data-ttu-id="cfdd1-149">8,2</span><span class="sxs-lookup"><span data-stu-id="cfdd1-149">8.2</span></span>  |
|            |  <span data-ttu-id="cfdd1-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-150">SBC 7000</span></span>         | <span data-ttu-id="cfdd1-151">8,2</span><span class="sxs-lookup"><span data-stu-id="cfdd1-151">8.2</span></span>  |
|            |  <span data-ttu-id="cfdd1-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-152">SBC SWe</span></span>          | <span data-ttu-id="cfdd1-153">8,2</span><span class="sxs-lookup"><span data-stu-id="cfdd1-153">8.2</span></span>  |
| [<span data-ttu-id="cfdd1-154">Ruban SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="cfdd1-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="cfdd1-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="cfdd1-155">SBC SWe Lite</span></span> | <span data-ttu-id="cfdd1-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-156">8.1.5</span></span> |
|               | <span data-ttu-id="cfdd1-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-157">SBC 1000</span></span> | <span data-ttu-id="cfdd1-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-158">8.1.5</span></span>  |
|               | <span data-ttu-id="cfdd1-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-159">SBC 2000</span></span> | <span data-ttu-id="cfdd1-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-160">8.1.5</span></span>  |
| [<span data-ttu-id="cfdd1-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="cfdd1-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="cfdd1-162">anynode</span><span class="sxs-lookup"><span data-stu-id="cfdd1-162">anynode</span></span>          | <span data-ttu-id="cfdd1-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="cfdd1-163">4.0.1+</span></span> |
| [<span data-ttu-id="cfdd1-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="cfdd1-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="cfdd1-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="cfdd1-165">AP 1100</span></span> | <span data-ttu-id="cfdd1-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="cfdd1-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="cfdd1-167">AP 3900</span></span> | <span data-ttu-id="cfdd1-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="cfdd1-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="cfdd1-169">AP 4600</span></span> | <span data-ttu-id="cfdd1-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="cfdd1-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="cfdd1-171">AP 6300</span></span> | <span data-ttu-id="cfdd1-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="cfdd1-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="cfdd1-173">AP 6350</span></span> | <span data-ttu-id="cfdd1-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="cfdd1-175">VME</span><span class="sxs-lookup"><span data-stu-id="cfdd1-175">VME</span></span>     | <span data-ttu-id="cfdd1-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="cfdd1-177">Gérer les adresses IP de confiance externes</span><span class="sxs-lookup"><span data-stu-id="cfdd1-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="cfdd1-178">Les adresses IP approuvées externes sont les adresses IP externes Internet du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="cfdd1-179">Ces adresses IP sont utilisées par les clients Microsoft teams lorsqu’ils se connectent à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="cfdd1-180">Vous devez ajouter ces adresses IP externes pour chaque site sur lequel les utilisateurs ont recours à une optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="cfdd1-181">Pour ajouter les adresses IP publiques pour chaque site, utilisez l’applet de nouvelle applet de nouveau-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="cfdd1-182">Vous pouvez définir un nombre illimité d’adresses IP de confiance pour un client.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="cfdd1-183">Si la prévention des intrusions externes observée par Microsoft 365 est une adresse IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="cfdd1-184">Pour IPv4, utilisez Mask 32.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="cfdd1-185">Pour IPv6, utilisez Mask 128.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="cfdd1-186">Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant des MaskBits différentes sur l’applet de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="cfdd1-187">Exemple d’ajout d’adresses IP approuvées.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="cfdd1-188">Définissez la topologie du réseau.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-188">Define the network topology</span></span>

<span data-ttu-id="cfdd1-189">Cette section décrit comment définir les régions réseau, les sites réseau et les sous-réseaux pour votre topologie réseau.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="cfdd1-190">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="cfdd1-191">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="cfdd1-192">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="cfdd1-192">Define network regions</span></span>

<span data-ttu-id="cfdd1-193">Pour définir les zones du réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="cfdd1-194">Le paramètre RegionID est un nom logique qui représente la géographie de la région et qui ne possède pas de dépendances ni de restrictions.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="cfdd1-195">Le <site ID> paramètre CentralSite est facultatif.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="cfdd1-196">L’exemple suivant permet de créer une zone de réseau nommée APAC :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="cfdd1-197">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="cfdd1-197">Define network sites</span></span>

<span data-ttu-id="cfdd1-198">Pour définir des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="cfdd1-199">Chaque site réseau doit être associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="cfdd1-200">L’exemple suivant crée trois nouveaux sites réseau, le Viêt Nam, l’Indonésie et Singapour dans la région APAC :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="cfdd1-201">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="cfdd1-201">Define network subnets</span></span>

<span data-ttu-id="cfdd1-202">Pour définir des sous-réseaux réseau et les associer à des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="cfdd1-203">Chaque sous-réseau ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="cfdd1-204">L’exemple suivant définit trois sous-réseaux réseau et les associe aux trois sites réseau : Vietnam, Indonésie et Singapour :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="cfdd1-205">Définir la topologie du réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-205">Define the virtual network topology</span></span> 

<span data-ttu-id="cfdd1-206">Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC appropriée à l’aide de l’applet de nouvelle cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="cfdd1-207">L’administrateur client définit la topologie du réseau virtuel en spécifiant les sites réseau pour les objets passerelle PSTN à l’aide de l’applet de connexion Set-CsOnlinePSTNGateway :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="cfdd1-208">Notez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-208">Note the following:</span></span> 
   - <span data-ttu-id="cfdd1-209">Si le client dispose d’un SBC unique, le paramètre-ProxySBC doit être obligatoire $null ou une valeur de nom de domaine complet (SBC) (central SBC avec des troncs centralisés).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="cfdd1-210">Le paramètre-MediaBypass doit être défini sur $true afin de prendre en charge l’optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="cfdd1-211">Si le SBC ne dispose pas du jeu de paramètres-BypassMode, les en-têtes X-MS ne seront pas envoyés.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="cfdd1-212">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="cfdd1-213">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="cfdd1-214">L’exemple suivant ajoute trois SBCs aux sites réseau Vietnam, Indonésie et Singapour dans la région APAC avec le mode toujours contournement :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="cfdd1-215">Remarque : pour garantir des opérations ininterrompues lors de la configuration de l’optimisation des médias locaux et du routage basé sur l’emplacement (LBR) en même temps, l’option SBCs en aval doit être activée pour LBR en définissant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="cfdd1-216">(Ce paramètre n’est pas obligatoire pour l’SBC proxy.)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="cfdd1-217">D’après les informations ci-dessus, le routage direct inclura trois en-têtes SIP propriétaires aux invitations SIP et aux Réinvitations, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="cfdd1-218">Les en-têtes X-MS introduites dans le routage direct sur les invitations et les Réinvitations si BypassMode est défini :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="cfdd1-219">Nom de l’en-tête</span><span class="sxs-lookup"><span data-stu-id="cfdd1-219">Header name</span></span> | <span data-ttu-id="cfdd1-220">Doubl</span><span class="sxs-lookup"><span data-stu-id="cfdd1-220">Values</span></span> | <span data-ttu-id="cfdd1-221">Commentaires</span><span class="sxs-lookup"><span data-stu-id="cfdd1-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="cfdd1-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="cfdd1-222">X-MS-UserLocation</span></span> | <span data-ttu-id="cfdd1-223">interne/externe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-223">internal/external</span></span> | <span data-ttu-id="cfdd1-224">Indique si l’utilisateur est interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="cfdd1-225">Requête-URL d’URL SIP : + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="cfdd1-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="cfdd1-226">NOM DE DOMAINE COMPLET SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-226">SBC FQDN</span></span> | <span data-ttu-id="cfdd1-227">Nom de domaine complet ciblé pour l’appel, même si l’SBC n’est pas directement connecté au routage direct</span><span class="sxs-lookup"><span data-stu-id="cfdd1-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="cfdd1-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="cfdd1-228">X-MS-MediaPath</span></span> | <span data-ttu-id="cfdd1-229">Par exemple : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-230">Ordre de SBCs à utiliser pour le chemin d’accès multimédia entre l’utilisateur et le SBC cible.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="cfdd1-231">Le SBC final est toujours le dernier.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-231">The final SBC is always last</span></span> |
| <span data-ttu-id="cfdd1-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="cfdd1-232">X-MS-UserSite</span></span> | <span data-ttu-id="cfdd1-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="cfdd1-233">usersiteID</span></span> | <span data-ttu-id="cfdd1-234">Chaîne définie par l’administrateur client</span><span class="sxs-lookup"><span data-stu-id="cfdd1-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="cfdd1-235">Flux d’appels</span><span class="sxs-lookup"><span data-stu-id="cfdd1-235">Call flows</span></span> 

<span data-ttu-id="cfdd1-236">Le code suivant montre les flux d’appels pour deux modes :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="cfdd1-237">Contournement permanent</span><span class="sxs-lookup"><span data-stu-id="cfdd1-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="cfdd1-238">Uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="cfdd1-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="cfdd1-239">Mode de contournement toujours</span><span class="sxs-lookup"><span data-stu-id="cfdd1-239">Always Bypass mode</span></span>

<span data-ttu-id="cfdd1-240">Le mode de contournement toujours est l’option la plus simple à configurer.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="cfdd1-241">L’administrateur client peut configurer un seul site pour tous les utilisateurs et SBCs s’il est joignable sur n’importe quel site.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="cfdd1-242">Les exemples indiquent toujours le mode de contournement pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="cfdd1-243">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="cfdd1-244">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="cfdd1-245">Appels sortants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="cfdd1-246">Appels entrants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="cfdd1-247">Le tableau suivant répertorie les adresses de domaine complets et les adresses IP utilisées dans les exemples :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="cfdd1-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="cfdd1-248">FQDN</span></span> | <span data-ttu-id="cfdd1-249">Adresse IP externe d’une SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-249">SBC external IP address</span></span> | <span data-ttu-id="cfdd1-250">Adresse IP interne de SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-250">SBC internal IP Address</span></span> | <span data-ttu-id="cfdd1-251">Sous-réseau interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-251">Internal subnet</span></span> | <span data-ttu-id="cfdd1-252">Lieu</span><span class="sxs-lookup"><span data-stu-id="cfdd1-252">Location</span></span> | <span data-ttu-id="cfdd1-253">NAT externe (IP de confiance)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-255">Aucun</span><span class="sxs-lookup"><span data-stu-id="cfdd1-255">None</span></span> | <span data-ttu-id="cfdd1-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-256">192.168.1.5</span></span> | <span data-ttu-id="cfdd1-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="cfdd1-257">192.168.1.0/24</span></span> | <span data-ttu-id="cfdd1-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="cfdd1-258">Vietnam</span></span> | <span data-ttu-id="cfdd1-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="cfdd1-259">172.16.240.110</span></span> |
| <span data-ttu-id="cfdd1-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-261">Aucun</span><span class="sxs-lookup"><span data-stu-id="cfdd1-261">None</span></span> | <span data-ttu-id="cfdd1-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-262">192.168.2.5</span></span> | <span data-ttu-id="cfdd1-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="cfdd1-263">192.168.2.0/24</span></span> | <span data-ttu-id="cfdd1-264">Indonésie</span><span class="sxs-lookup"><span data-stu-id="cfdd1-264">Indonesia</span></span> | <span data-ttu-id="cfdd1-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="cfdd1-265">172.16.240.120</span></span> |
| <span data-ttu-id="cfdd1-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="cfdd1-267">172.16.240.133</span></span> | <span data-ttu-id="cfdd1-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="cfdd1-268">192.168.3.5</span></span> | <span data-ttu-id="cfdd1-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="cfdd1-269">192.168.3.0/24</span></span> | <span data-ttu-id="cfdd1-270">Singapour</span><span class="sxs-lookup"><span data-stu-id="cfdd1-270">Singapore</span></span> | <span data-ttu-id="cfdd1-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="cfdd1-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="cfdd1-272">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="cfdd1-273">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-273">Mode</span></span> |    <span data-ttu-id="cfdd1-274">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-274">User</span></span> |  <span data-ttu-id="cfdd1-275">Lieu</span><span class="sxs-lookup"><span data-stu-id="cfdd1-275">Location</span></span> |  <span data-ttu-id="cfdd1-276">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="cfdd1-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="cfdd1-277">AlwaysBypass</span></span> |    <span data-ttu-id="cfdd1-278">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-278">Internal</span></span> |  <span data-ttu-id="cfdd1-279">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-279">The same site as SBC</span></span> |  <span data-ttu-id="cfdd1-280">Sortant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-280">Outbound</span></span> |

<span data-ttu-id="cfdd1-281">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="cfdd1-282">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-282">User physical location</span></span>| <span data-ttu-id="cfdd1-283">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="cfdd1-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="cfdd1-284">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-284">User phone number</span></span>  | <span data-ttu-id="cfdd1-285">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="cfdd1-286">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="cfdd1-287">Vietnam</span></span> | <span data-ttu-id="cfdd1-288">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-288">+84 4 3926 3000</span></span> | <span data-ttu-id="cfdd1-289">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="cfdd1-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="cfdd1-290">Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="cfdd1-291">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="cfdd1-292">VNsbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="cfdd1-293">proxysbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="cfdd1-294">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode toujours Bypass et l’utilisateur au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="cfdd1-295">![Diagramme montrant les appels sortants](media/direct-routing-media-op-10.png "Appels sortants")</span><span class="sxs-lookup"><span data-stu-id="cfdd1-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="cfdd1-296">Le tableau suivant montre les en-têtes X-MS envoyés par le routage direct :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="cfdd1-297">Paramètre</span><span class="sxs-lookup"><span data-stu-id="cfdd1-297">Parameter</span></span> | <span data-ttu-id="cfdd1-298">Explication</span><span class="sxs-lookup"><span data-stu-id="cfdd1-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="cfdd1-299">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-300">Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête</span><span class="sxs-lookup"><span data-stu-id="cfdd1-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="cfdd1-301">X-MS-UserLocation : Internal</span><span class="sxs-lookup"><span data-stu-id="cfdd1-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="cfdd1-302">Le champ indique que cet utilisateur se trouve à l’intérieur du réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="cfdd1-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="cfdd1-303">X-MS-MediaPath : VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="cfdd1-304">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="cfdd1-305">Dans le cas présent, il n’existe pas de contournement, et le client est en interne le nom de cible envoyé en tant que nom unique dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="cfdd1-306">X-MS-UserSite : Vietnam</span><span class="sxs-lookup"><span data-stu-id="cfdd1-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="cfdd1-307">Le champ indiqué dans le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="cfdd1-308">Appels entrants et l’utilisateur se trouve dans le même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="cfdd1-309">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-309">Mode</span></span> |    <span data-ttu-id="cfdd1-310">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-310">User</span></span> |  <span data-ttu-id="cfdd1-311">Lieu</span><span class="sxs-lookup"><span data-stu-id="cfdd1-311">Location</span></span> |  <span data-ttu-id="cfdd1-312">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="cfdd1-313">AlwaysBypass</span></span> |    <span data-ttu-id="cfdd1-314">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-314">Internal</span></span> | <span data-ttu-id="cfdd1-315">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-315">The same site as SBC</span></span> | <span data-ttu-id="cfdd1-316">Entrant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-316">Inbound</span></span> |


<span data-ttu-id="cfdd1-317">Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et l’SBC doit deviner l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="cfdd1-318">Si l’estimation n’est pas correcte, une nouvelle invitation sera requise.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="cfdd1-319">Dans le cas présent, l’utilisateur est interne, le média peut être acheminé directement et aucune action supplémentaire n’est nécessaire (réinvitation).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="cfdd1-320">Le SBC connecté au service de routage direct rapporte l’emplacement de l’SBC d’origine en fournissant des champs d’itinéraire d’enregistrement et de contact.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="cfdd1-321">En fonction de ces champs, le chemin multimédia est calculé par le routage direct.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="cfdd1-322">Remarque : étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge d' 183 n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="cfdd1-323">Dans le cas présent, le routage direct utilise toujours la sonnerie 180.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="cfdd1-324">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="cfdd1-326">Les appels sortants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="cfdd1-327">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-327">Mode</span></span> |    <span data-ttu-id="cfdd1-328">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-328">User</span></span> |  <span data-ttu-id="cfdd1-329">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-329">Site</span></span> |  <span data-ttu-id="cfdd1-330">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="cfdd1-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="cfdd1-331">AlwaysBypass</span></span> |  <span data-ttu-id="cfdd1-332">Externe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-332">External</span></span> |  <span data-ttu-id="cfdd1-333">N/A</span><span class="sxs-lookup"><span data-stu-id="cfdd1-333">N/A</span></span> | <span data-ttu-id="cfdd1-334">Sortant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-334">Outbound</span></span> |


<span data-ttu-id="cfdd1-335">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode AlwaysBypass et l’utilisateur est externe :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="cfdd1-337">Le tableau suivant montre les en-têtes X-MS envoyés par le service de routage directe :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="cfdd1-338">Paramètre</span><span class="sxs-lookup"><span data-stu-id="cfdd1-338">Parameter</span></span> |   <span data-ttu-id="cfdd1-339">Explication</span><span class="sxs-lookup"><span data-stu-id="cfdd1-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="cfdd1-340">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-341">Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="cfdd1-342">X-MS-UserLocation : externes</span><span class="sxs-lookup"><span data-stu-id="cfdd1-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="cfdd1-343">Le champ indique que cet utilisateur se trouve en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="cfdd1-344">X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="cfdd1-345">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="cfdd1-346">Dans le cas présent, il n’existe pas de contournement, et le client est externe.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="cfdd1-347">Les appels entrants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="cfdd1-348">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-348">Mode</span></span> | <span data-ttu-id="cfdd1-349">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-349">User</span></span> | <span data-ttu-id="cfdd1-350">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-350">Site</span></span> |  <span data-ttu-id="cfdd1-351">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="cfdd1-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="cfdd1-352">AlwaysBypass</span></span> |  <span data-ttu-id="cfdd1-353">Externe</span><span class="sxs-lookup"><span data-stu-id="cfdd1-353">External</span></span> |  <span data-ttu-id="cfdd1-354">N/A</span><span class="sxs-lookup"><span data-stu-id="cfdd1-354">N/A</span></span> |   <span data-ttu-id="cfdd1-355">Entrant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-355">Inbound</span></span> |

<span data-ttu-id="cfdd1-356">Dans le cas d’un appel entrant, l’appel SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les candidats de média local sont toujours proposés) si l’emplacement de l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="cfdd1-357">Le X-MediaPath est calculé en fonction de record-route et de l’utilisateur SBC spécifié.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="cfdd1-358">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="cfdd1-360">Uniquement pour le mode utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="cfdd1-360">Only for local users mode</span></span>

<span data-ttu-id="cfdd1-361">Les médias de médias locaux des SBC cibles seront proposés uniquement si un utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="cfdd1-362">Dans tous les autres cas, le contenu multimédia passe par l’intermédiaire d’une adresse IP interne ou externe du proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="cfdd1-363">Les scénarios suivants sont décrits :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="cfdd1-364">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="cfdd1-365">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="cfdd1-366">L’utilisateur ne se trouve pas au même emplacement que l’SBC mais il se trouve dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="cfdd1-367">Les appels entrants et l’utilisateur est interne, mais pas au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="cfdd1-368">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="cfdd1-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="cfdd1-369">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-369">User physical location</span></span> |  <span data-ttu-id="cfdd1-370">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="cfdd1-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="cfdd1-371">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-371">User phone number</span></span> | <span data-ttu-id="cfdd1-372">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="cfdd1-373">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="cfdd1-374">Vietnam</span></span> | <span data-ttu-id="cfdd1-375">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="cfdd1-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="cfdd1-376">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="cfdd1-376">+84 4 5555 5555</span></span> | <span data-ttu-id="cfdd1-377">Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="cfdd1-378">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cfdd1-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="cfdd1-379">VNsbc.contoso.com : OnlyForLocalUsers Proxysbc.contoso.com – toujours contournement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="cfdd1-380">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="cfdd1-381">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-381">Mode</span></span> | <span data-ttu-id="cfdd1-382">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-382">User</span></span> | <span data-ttu-id="cfdd1-383">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-383">Site</span></span> | <span data-ttu-id="cfdd1-384">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="cfdd1-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="cfdd1-386">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-386">Internal</span></span> |<span data-ttu-id="cfdd1-387">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-387">Same as SBC</span></span>   | <span data-ttu-id="cfdd1-388">Sortant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-388">Outbound</span></span> |

<span data-ttu-id="cfdd1-389">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="cfdd1-390">Ce flux est le même que celui affiché dans les [appels sortants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="cfdd1-392">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement</span><span class="sxs-lookup"><span data-stu-id="cfdd1-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="cfdd1-393">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-393">Mode</span></span> | <span data-ttu-id="cfdd1-394">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-394">User</span></span> | <span data-ttu-id="cfdd1-395">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-395">Site</span></span> | <span data-ttu-id="cfdd1-396">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="cfdd1-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="cfdd1-398">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-398">Internal</span></span> | <span data-ttu-id="cfdd1-399">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-399">Same as SBC</span></span> | <span data-ttu-id="cfdd1-400">Entrant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-400">Inbound</span></span> |

<span data-ttu-id="cfdd1-401">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="cfdd1-402">Ce flux est le même que celui affiché dans les [appels entrants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="cfdd1-404">L’utilisateur ne se trouve pas au même emplacement que le SBC mais il se trouve sur le réseau d’entreprise uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="cfdd1-405">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-405">Mode</span></span> | <span data-ttu-id="cfdd1-406">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-406">User</span></span> | <span data-ttu-id="cfdd1-407">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-407">Site</span></span> |<span data-ttu-id="cfdd1-408">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="cfdd1-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="cfdd1-410">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-410">Internal</span></span> |   <span data-ttu-id="cfdd1-411">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-411">Different from SBC</span></span> | <span data-ttu-id="cfdd1-412">Sortant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-412">Outbound</span></span> |

<span data-ttu-id="cfdd1-413">Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configurés sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="cfdd1-414">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="cfdd1-416">Les appels entrants et l’utilisateur sont internes, mais ne se trouvent pas dans le même emplacement que l’SBC uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="cfdd1-417">Veille</span><span class="sxs-lookup"><span data-stu-id="cfdd1-417">Mode</span></span> |    <span data-ttu-id="cfdd1-418">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfdd1-418">User</span></span> |  <span data-ttu-id="cfdd1-419">Site</span><span class="sxs-lookup"><span data-stu-id="cfdd1-419">Site</span></span> |  <span data-ttu-id="cfdd1-420">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="cfdd1-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="cfdd1-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="cfdd1-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="cfdd1-422">Interne</span><span class="sxs-lookup"><span data-stu-id="cfdd1-422">Internal</span></span> |    <span data-ttu-id="cfdd1-423">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="cfdd1-423">Different from SBC</span></span> |    <span data-ttu-id="cfdd1-424">Entrant</span><span class="sxs-lookup"><span data-stu-id="cfdd1-424">Inbound</span></span> |

<span data-ttu-id="cfdd1-425">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-17.png)









