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
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121604"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="f1126-103">Configurer l’optimisation locale des médias pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="f1126-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="f1126-104">La configuration de l’optimisation des éléments multimédias locaux est basée sur les paramètres réseau communs aux autres fonctionnalités de voix Cloud, telles que le routage par emplacement et les appels d’urgence dynamiques.</span><span class="sxs-lookup"><span data-stu-id="f1126-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="f1126-105">Pour en savoir plus sur les zones du réseau, les sites réseau, les sous-réseaux réseau et les adresses IP de confiance, voir [paramètres réseau pour les fonctionnalités vocales dans le Cloud](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f1126-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f1126-106">Avant de configurer l’optimisation de média locale, voir [optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="f1126-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="f1126-107">Pour configurer l’optimisation de média locale, les étapes suivantes sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="f1126-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="f1126-108">Vous pouvez utiliser le centre d’administration teams ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1126-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="f1126-109">Pour plus d’informations, voir [gérer la topologie de votre réseau](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="f1126-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="f1126-110">Configurez les sites utilisateur et SBC (comme décrit dans cet article).</span><span class="sxs-lookup"><span data-stu-id="f1126-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="f1126-111">Configurez l’application SBCs pour l’optimisation de média locale (en fonction de la spécification de votre fournisseur SBC).</span><span class="sxs-lookup"><span data-stu-id="f1126-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="f1126-112">Le diagramme suivant montre la configuration du réseau utilisée dans les exemples de cet article.</span><span class="sxs-lookup"><span data-stu-id="f1126-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="f1126-113">![Diagramme illustrant la configuration réseau pour les exemples](media/direct-routing-media-op-9.png "Configuration du réseau pour les exemples")</span><span class="sxs-lookup"><span data-stu-id="f1126-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="f1126-114">Configurer l’utilisateur et les sites SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="f1126-115">Pour configurer l’utilisateur et les sites SBC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="f1126-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="f1126-116">[Gérer les adresses IP de confiance externes](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="f1126-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="f1126-117">[Définissez la topologie du réseau](#define-the-network-topology) en configurant les zones du réseau, les sites réseau et les sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="f1126-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="f1126-118">[Définissez la topologie du réseau virtuel](#define-the-virtual-network-topology) en assignant des SBC (s) aux sites avec des modes pertinents et des valeurs SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="f1126-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="f1126-119">Configurer des SBC pour optimiser les médias locaux conformément à la spécification du fournisseur de SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="f1126-120">Cet article décrit la configuration des composants Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1126-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="f1126-121">Pour plus d’informations sur la configuration d’un SBC, consultez la documentation de votre fournisseur SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="f1126-122">L’optimisation des éléments multimédias locaux est prise en charge par les fournisseurs de SBC suivants :</span><span class="sxs-lookup"><span data-stu-id="f1126-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="f1126-123">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="f1126-123">Vendor</span></span> | <span data-ttu-id="f1126-124">Product</span><span class="sxs-lookup"><span data-stu-id="f1126-124">Product</span></span> |    <span data-ttu-id="f1126-125">Version du logiciel</span><span class="sxs-lookup"><span data-stu-id="f1126-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="f1126-126">CodesAudio</span><span class="sxs-lookup"><span data-stu-id="f1126-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="f1126-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="f1126-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="f1126-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="f1126-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="f1126-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-135">1000B SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="f1126-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-137">SBC-9000</span><span class="sxs-lookup"><span data-stu-id="f1126-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="f1126-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-139">SBC-édition virtuelle-SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="f1126-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="f1126-141">SBC édition Cloud-SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="f1126-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="f1126-142">7.20A.256</span></span> |
| [<span data-ttu-id="f1126-143">Noyau SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="f1126-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="f1126-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="f1126-144">SBC 5110</span></span>         | <span data-ttu-id="f1126-145">8,2</span><span class="sxs-lookup"><span data-stu-id="f1126-145">8.2</span></span>  |
|            |  <span data-ttu-id="f1126-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="f1126-146">SBC 5210</span></span>         | <span data-ttu-id="f1126-147">8,2</span><span class="sxs-lookup"><span data-stu-id="f1126-147">8.2</span></span>  |
|            |  <span data-ttu-id="f1126-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="f1126-148">SBC 5400</span></span>         | <span data-ttu-id="f1126-149">8,2</span><span class="sxs-lookup"><span data-stu-id="f1126-149">8.2</span></span>  |
|            |  <span data-ttu-id="f1126-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="f1126-150">SBC 7000</span></span>         | <span data-ttu-id="f1126-151">8,2</span><span class="sxs-lookup"><span data-stu-id="f1126-151">8.2</span></span>  |
|            |  <span data-ttu-id="f1126-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="f1126-152">SBC SWe</span></span>          | <span data-ttu-id="f1126-153">8,2</span><span class="sxs-lookup"><span data-stu-id="f1126-153">8.2</span></span>  |
| [<span data-ttu-id="f1126-154">Ruban SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="f1126-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="f1126-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="f1126-155">SBC SWe Lite</span></span> | <span data-ttu-id="f1126-156">8.1.5 (Build 239)</span><span class="sxs-lookup"><span data-stu-id="f1126-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="f1126-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="f1126-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="f1126-158">anynode</span><span class="sxs-lookup"><span data-stu-id="f1126-158">anynode</span></span>          | <span data-ttu-id="f1126-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="f1126-159">4.0.1+</span></span> |
| [<span data-ttu-id="f1126-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="f1126-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="f1126-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="f1126-161">AP 1100</span></span> | <span data-ttu-id="f1126-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f1126-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="f1126-163">AP 3900</span></span> | <span data-ttu-id="f1126-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f1126-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="f1126-165">AP 4600</span></span> | <span data-ttu-id="f1126-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="f1126-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="f1126-167">AP 6300</span></span> | <span data-ttu-id="f1126-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="f1126-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="f1126-169">AP 6350</span></span> | <span data-ttu-id="f1126-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="f1126-171">VME</span><span class="sxs-lookup"><span data-stu-id="f1126-171">VME</span></span>     | <span data-ttu-id="f1126-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f1126-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="f1126-173">Gérer les adresses IP de confiance externes</span><span class="sxs-lookup"><span data-stu-id="f1126-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="f1126-174">Les adresses IP approuvées externes sont les adresses IP externes Internet du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f1126-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="f1126-175">Ces adresses IP sont utilisées par les clients Microsoft teams lorsqu’ils se connectent à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1126-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="f1126-176">Vous devez ajouter ces adresses IP externes pour chaque site sur lequel les utilisateurs ont recours à une optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="f1126-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="f1126-177">Pour ajouter les adresses IP publiques pour chaque site, utilisez l’applet de nouvelle applet de nouveau-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="f1126-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="f1126-178">Vous pouvez définir un nombre illimité d’adresses IP de confiance pour un client.</span><span class="sxs-lookup"><span data-stu-id="f1126-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="f1126-179">Si la prévention des intrusions externes observée par Microsoft 365 est une adresse IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="f1126-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="f1126-180">Pour IPv4, utilisez Mask 32.</span><span class="sxs-lookup"><span data-stu-id="f1126-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="f1126-181">Pour IPv6, utilisez Mask 128.</span><span class="sxs-lookup"><span data-stu-id="f1126-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="f1126-182">Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant des MaskBits différentes sur l’applet de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1126-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="f1126-183">Exemple d’ajout d’adresses IP approuvées.</span><span class="sxs-lookup"><span data-stu-id="f1126-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="f1126-184">Définissez la topologie du réseau.</span><span class="sxs-lookup"><span data-stu-id="f1126-184">Define the network topology</span></span>

<span data-ttu-id="f1126-185">Cette section décrit comment définir les régions réseau, les sites réseau et les sous-réseaux pour votre topologie réseau.</span><span class="sxs-lookup"><span data-stu-id="f1126-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="f1126-186">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="f1126-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="f1126-187">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="f1126-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="f1126-188">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="f1126-188">Define network regions</span></span>

<span data-ttu-id="f1126-189">Pour définir les zones du réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="f1126-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="f1126-190">Le paramètre RegionID est un nom logique qui représente la géographie de la région et qui ne possède pas de dépendances ni de restrictions.</span><span class="sxs-lookup"><span data-stu-id="f1126-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="f1126-191">Le <site ID> paramètre CentralSite est facultatif.</span><span class="sxs-lookup"><span data-stu-id="f1126-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="f1126-192">L’exemple suivant permet de créer une zone de réseau nommée APAC :</span><span class="sxs-lookup"><span data-stu-id="f1126-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="f1126-193">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="f1126-193">Define network sites</span></span>

<span data-ttu-id="f1126-194">Pour définir des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="f1126-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="f1126-195">Chaque site réseau doit être associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="f1126-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="f1126-196">L’exemple suivant crée trois nouveaux sites réseau, le Viêt Nam, l’Indonésie et Singapour dans la région APAC :</span><span class="sxs-lookup"><span data-stu-id="f1126-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="f1126-197">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="f1126-197">Define network subnets</span></span>

<span data-ttu-id="f1126-198">Pour définir des sous-réseaux réseau et les associer à des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="f1126-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="f1126-199">Chaque sous-réseau ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="f1126-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="f1126-200">L’exemple suivant définit trois sous-réseaux réseau et les associe aux trois sites réseau : Vietnam, Indonésie et Singapour :</span><span class="sxs-lookup"><span data-stu-id="f1126-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="f1126-201">Définir la topologie du réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="f1126-201">Define the virtual network topology</span></span> 

<span data-ttu-id="f1126-202">Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC appropriée à l’aide de l’applet de nouvelle cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="f1126-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="f1126-203">L’administrateur client définit la topologie du réseau virtuel en spécifiant les sites réseau pour les objets passerelle PSTN à l’aide de l’applet de connexion Set-CsOnlinePSTNGateway :</span><span class="sxs-lookup"><span data-stu-id="f1126-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="f1126-204">Notez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f1126-204">Note the following:</span></span> 
   - <span data-ttu-id="f1126-205">Si le client dispose d’un SBC unique, le paramètre-ProxySBC doit être obligatoire $null ou une valeur de nom de domaine complet (SBC) (central SBC avec des troncs centralisés).</span><span class="sxs-lookup"><span data-stu-id="f1126-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="f1126-206">Le paramètre-MediaBypass doit être défini sur $true afin de prendre en charge l’optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="f1126-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="f1126-207">Si le SBC ne dispose pas du jeu de paramètres-BypassMode, les en-têtes X-MS ne seront pas envoyés.</span><span class="sxs-lookup"><span data-stu-id="f1126-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="f1126-208">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="f1126-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="f1126-209">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="f1126-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="f1126-210">L’exemple suivant ajoute trois SBCs aux sites réseau Vietnam, Indonésie et Singapour dans la région APAC avec le mode toujours contournement :</span><span class="sxs-lookup"><span data-stu-id="f1126-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="f1126-211">Remarque : pour garantir des opérations ininterrompues lors de la configuration de l’optimisation des médias locaux et du routage basé sur l’emplacement (LBR) en même temps, l’option SBCs en aval doit être activée pour LBR en définissant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval.</span><span class="sxs-lookup"><span data-stu-id="f1126-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="f1126-212">(Ce paramètre n’est pas obligatoire pour l’SBC proxy.)</span><span class="sxs-lookup"><span data-stu-id="f1126-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="f1126-213">D’après les informations ci-dessus, le routage direct inclura trois en-têtes SIP propriétaires aux invitations SIP et aux Réinvitations, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="f1126-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="f1126-214">Les en-têtes X-MS introduites dans le routage direct sur les invitations et les Réinvitations si BypassMode est défini :</span><span class="sxs-lookup"><span data-stu-id="f1126-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="f1126-215">Nom de l’en-tête</span><span class="sxs-lookup"><span data-stu-id="f1126-215">Header name</span></span> | <span data-ttu-id="f1126-216">Doubl</span><span class="sxs-lookup"><span data-stu-id="f1126-216">Values</span></span> | <span data-ttu-id="f1126-217">Commentaires</span><span class="sxs-lookup"><span data-stu-id="f1126-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="f1126-218">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="f1126-218">X-MS-UserLocation</span></span> | <span data-ttu-id="f1126-219">interne/externe</span><span class="sxs-lookup"><span data-stu-id="f1126-219">internal/external</span></span> | <span data-ttu-id="f1126-220">Indique si l’utilisateur est interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="f1126-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="f1126-221">Requête-URL d’URL SIP : + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="f1126-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="f1126-222">NOM DE DOMAINE COMPLET SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-222">SBC FQDN</span></span> | <span data-ttu-id="f1126-223">Nom de domaine complet ciblé pour l’appel, même si l’SBC n’est pas directement connecté au routage direct</span><span class="sxs-lookup"><span data-stu-id="f1126-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="f1126-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="f1126-224">X-MS-MediaPath</span></span> | <span data-ttu-id="f1126-225">Par exemple : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="f1126-226">Ordre de SBCs à utiliser pour le chemin d’accès multimédia entre l’utilisateur et le SBC cible.</span><span class="sxs-lookup"><span data-stu-id="f1126-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="f1126-227">Le SBC final est toujours le dernier.</span><span class="sxs-lookup"><span data-stu-id="f1126-227">The final SBC is always last</span></span> |
| <span data-ttu-id="f1126-228">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="f1126-228">X-MS-UserSite</span></span> | <span data-ttu-id="f1126-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="f1126-229">usersiteID</span></span> | <span data-ttu-id="f1126-230">Chaîne définie par l’administrateur client</span><span class="sxs-lookup"><span data-stu-id="f1126-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="f1126-231">Flux d’appels</span><span class="sxs-lookup"><span data-stu-id="f1126-231">Call flows</span></span> 

<span data-ttu-id="f1126-232">Le code suivant montre les flux d’appels pour deux modes :</span><span class="sxs-lookup"><span data-stu-id="f1126-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="f1126-233">Contournement permanent</span><span class="sxs-lookup"><span data-stu-id="f1126-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="f1126-234">Uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="f1126-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="f1126-235">Mode de contournement toujours</span><span class="sxs-lookup"><span data-stu-id="f1126-235">Always Bypass mode</span></span>

<span data-ttu-id="f1126-236">Le mode de contournement toujours est l’option la plus simple à configurer.</span><span class="sxs-lookup"><span data-stu-id="f1126-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="f1126-237">L’administrateur client peut configurer un seul site pour tous les utilisateurs et SBCs s’il est joignable sur n’importe quel site.</span><span class="sxs-lookup"><span data-stu-id="f1126-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="f1126-238">Les exemples indiquent toujours le mode de contournement pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="f1126-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="f1126-239">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="f1126-240">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="f1126-241">Appels sortants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="f1126-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="f1126-242">Appels entrants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="f1126-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="f1126-243">Le tableau suivant répertorie les adresses de domaine complets et les adresses IP utilisées dans les exemples :</span><span class="sxs-lookup"><span data-stu-id="f1126-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="f1126-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="f1126-244">FQDN</span></span> | <span data-ttu-id="f1126-245">Adresse IP externe d’une SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-245">SBC external IP address</span></span> | <span data-ttu-id="f1126-246">Adresse IP interne de SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-246">SBC internal IP Address</span></span> | <span data-ttu-id="f1126-247">Sous-réseau interne</span><span class="sxs-lookup"><span data-stu-id="f1126-247">Internal subnet</span></span> | <span data-ttu-id="f1126-248">Lieu</span><span class="sxs-lookup"><span data-stu-id="f1126-248">Location</span></span> | <span data-ttu-id="f1126-249">NAT externe (IP de confiance)</span><span class="sxs-lookup"><span data-stu-id="f1126-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="f1126-251">Aucun</span><span class="sxs-lookup"><span data-stu-id="f1126-251">None</span></span> | <span data-ttu-id="f1126-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="f1126-252">192.168.1.5</span></span> | <span data-ttu-id="f1126-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="f1126-253">192.168.1.0/24</span></span> | <span data-ttu-id="f1126-254">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f1126-254">Vietnam</span></span> | <span data-ttu-id="f1126-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="f1126-255">172.16.240.110</span></span> |
| <span data-ttu-id="f1126-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="f1126-257">Aucun</span><span class="sxs-lookup"><span data-stu-id="f1126-257">None</span></span> | <span data-ttu-id="f1126-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="f1126-258">192.168.2.5</span></span> | <span data-ttu-id="f1126-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="f1126-259">192.168.2.0/24</span></span> | <span data-ttu-id="f1126-260">Indonésie</span><span class="sxs-lookup"><span data-stu-id="f1126-260">Indonesia</span></span> | <span data-ttu-id="f1126-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="f1126-261">172.16.240.120</span></span> |
| <span data-ttu-id="f1126-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="f1126-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="f1126-263">172.16.240.133</span></span> | <span data-ttu-id="f1126-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="f1126-264">192.168.3.5</span></span> | <span data-ttu-id="f1126-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="f1126-265">192.168.3.0/24</span></span> | <span data-ttu-id="f1126-266">Singapour</span><span class="sxs-lookup"><span data-stu-id="f1126-266">Singapore</span></span> | <span data-ttu-id="f1126-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="f1126-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="f1126-268">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="f1126-269">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-269">Mode</span></span> |    <span data-ttu-id="f1126-270">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-270">User</span></span> |  <span data-ttu-id="f1126-271">Lieu</span><span class="sxs-lookup"><span data-stu-id="f1126-271">Location</span></span> |  <span data-ttu-id="f1126-272">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="f1126-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f1126-273">AlwaysBypass</span></span> |    <span data-ttu-id="f1126-274">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-274">Internal</span></span> |  <span data-ttu-id="f1126-275">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-275">The same site as SBC</span></span> |  <span data-ttu-id="f1126-276">Sortant</span><span class="sxs-lookup"><span data-stu-id="f1126-276">Outbound</span></span> |

<span data-ttu-id="f1126-277">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="f1126-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="f1126-278">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-278">User physical location</span></span>| <span data-ttu-id="f1126-279">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="f1126-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="f1126-280">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-280">User phone number</span></span>  | <span data-ttu-id="f1126-281">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="f1126-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="f1126-282">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-283">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f1126-283">Vietnam</span></span> | <span data-ttu-id="f1126-284">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="f1126-284">+84 4 3926 3000</span></span> | <span data-ttu-id="f1126-285">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="f1126-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="f1126-286">Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="f1126-287">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="f1126-288">VNsbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="f1126-289">proxysbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="f1126-290">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode toujours Bypass et l’utilisateur au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="f1126-291">![Diagramme montrant les appels sortants](media/direct-routing-media-op-10.png "Appels sortants")</span><span class="sxs-lookup"><span data-stu-id="f1126-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="f1126-292">Le tableau suivant montre les en-têtes X-MS envoyés par le routage direct :</span><span class="sxs-lookup"><span data-stu-id="f1126-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="f1126-293">Paramètre</span><span class="sxs-lookup"><span data-stu-id="f1126-293">Parameter</span></span> | <span data-ttu-id="f1126-294">Explication</span><span class="sxs-lookup"><span data-stu-id="f1126-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="f1126-295">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="f1126-296">Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête</span><span class="sxs-lookup"><span data-stu-id="f1126-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="f1126-297">X-MS-UserLocation : Internal</span><span class="sxs-lookup"><span data-stu-id="f1126-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="f1126-298">Le champ indique que cet utilisateur se trouve à l’intérieur du réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="f1126-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="f1126-299">X-MS-MediaPath : VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="f1126-300">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="f1126-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="f1126-301">Dans le cas présent, il n’existe pas de contournement, et le client est en interne le nom de cible envoyé en tant que nom unique dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="f1126-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="f1126-302">X-MS-UserSite : Vietnam</span><span class="sxs-lookup"><span data-stu-id="f1126-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="f1126-303">Le champ indiqué dans le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f1126-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="f1126-304">Appels entrants et l’utilisateur se trouve dans le même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="f1126-305">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-305">Mode</span></span> |    <span data-ttu-id="f1126-306">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-306">User</span></span> |  <span data-ttu-id="f1126-307">Lieu</span><span class="sxs-lookup"><span data-stu-id="f1126-307">Location</span></span> |  <span data-ttu-id="f1126-308">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f1126-309">AlwaysBypass</span></span> |    <span data-ttu-id="f1126-310">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-310">Internal</span></span> | <span data-ttu-id="f1126-311">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-311">The same site as SBC</span></span> | <span data-ttu-id="f1126-312">Entrant</span><span class="sxs-lookup"><span data-stu-id="f1126-312">Inbound</span></span> |


<span data-ttu-id="f1126-313">Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et l’SBC doit deviner l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f1126-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="f1126-314">Si l’estimation n’est pas correcte, une nouvelle invitation sera requise.</span><span class="sxs-lookup"><span data-stu-id="f1126-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="f1126-315">Dans le cas présent, l’utilisateur est interne, le média peut être acheminé directement et aucune action supplémentaire n’est nécessaire (réinvitation).</span><span class="sxs-lookup"><span data-stu-id="f1126-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="f1126-316">Le SBC connecté au service de routage direct rapporte l’emplacement de l’SBC d’origine en fournissant des champs d’itinéraire d’enregistrement et de contact.</span><span class="sxs-lookup"><span data-stu-id="f1126-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="f1126-317">En fonction de ces champs, le chemin multimédia est calculé par le routage direct.</span><span class="sxs-lookup"><span data-stu-id="f1126-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="f1126-318">Remarque : étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge d' 183 n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="f1126-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="f1126-319">Dans le cas présent, le routage direct utilise toujours la sonnerie 180.</span><span class="sxs-lookup"><span data-stu-id="f1126-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="f1126-320">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="f1126-322">Les appels sortants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="f1126-323">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-323">Mode</span></span> |    <span data-ttu-id="f1126-324">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-324">User</span></span> |  <span data-ttu-id="f1126-325">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-325">Site</span></span> |  <span data-ttu-id="f1126-326">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="f1126-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f1126-327">AlwaysBypass</span></span> |  <span data-ttu-id="f1126-328">Externe</span><span class="sxs-lookup"><span data-stu-id="f1126-328">External</span></span> |  <span data-ttu-id="f1126-329">N/A</span><span class="sxs-lookup"><span data-stu-id="f1126-329">N/A</span></span> | <span data-ttu-id="f1126-330">Sortant</span><span class="sxs-lookup"><span data-stu-id="f1126-330">Outbound</span></span> |


<span data-ttu-id="f1126-331">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode AlwaysBypass et l’utilisateur est externe :</span><span class="sxs-lookup"><span data-stu-id="f1126-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="f1126-333">Le tableau suivant montre les en-têtes X-MS envoyés par le service de routage directe :</span><span class="sxs-lookup"><span data-stu-id="f1126-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="f1126-334">Paramètre</span><span class="sxs-lookup"><span data-stu-id="f1126-334">Parameter</span></span> |   <span data-ttu-id="f1126-335">Explication</span><span class="sxs-lookup"><span data-stu-id="f1126-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="f1126-336">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="f1126-337">Le FQDN cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête.</span><span class="sxs-lookup"><span data-stu-id="f1126-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="f1126-338">X-MS-UserLocation : externes</span><span class="sxs-lookup"><span data-stu-id="f1126-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="f1126-339">Le champ indique que cet utilisateur se trouve en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f1126-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="f1126-340">X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="f1126-341">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="f1126-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="f1126-342">Dans le cas présent, il n’existe pas de contournement, et le client est externe.</span><span class="sxs-lookup"><span data-stu-id="f1126-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="f1126-343">Les appels entrants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="f1126-344">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-344">Mode</span></span> | <span data-ttu-id="f1126-345">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-345">User</span></span> | <span data-ttu-id="f1126-346">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-346">Site</span></span> |  <span data-ttu-id="f1126-347">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="f1126-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="f1126-348">AlwaysBypass</span></span> |  <span data-ttu-id="f1126-349">Externe</span><span class="sxs-lookup"><span data-stu-id="f1126-349">External</span></span> |  <span data-ttu-id="f1126-350">N/A</span><span class="sxs-lookup"><span data-stu-id="f1126-350">N/A</span></span> |   <span data-ttu-id="f1126-351">Entrant</span><span class="sxs-lookup"><span data-stu-id="f1126-351">Inbound</span></span> |

<span data-ttu-id="f1126-352">Dans le cas d’un appel entrant, l’appel SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les candidats de média local sont toujours proposés) si l’emplacement de l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="f1126-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="f1126-353">Le X-MediaPath est calculé en fonction de record-route et de l’utilisateur SBC spécifié.</span><span class="sxs-lookup"><span data-stu-id="f1126-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="f1126-354">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="f1126-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="f1126-356">Uniquement pour le mode utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="f1126-356">Only for local users mode</span></span>

<span data-ttu-id="f1126-357">Les médias de médias locaux des SBC cibles seront proposés uniquement si un utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="f1126-358">Dans tous les autres cas, le contenu multimédia passe par l’intermédiaire d’une adresse IP interne ou externe du proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="f1126-359">Les scénarios suivants sont décrits :</span><span class="sxs-lookup"><span data-stu-id="f1126-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="f1126-360">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="f1126-361">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="f1126-362">L’utilisateur ne se trouve pas au même emplacement que l’SBC mais il se trouve dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f1126-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="f1126-363">Les appels entrants et l’utilisateur est interne, mais pas au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="f1126-364">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="f1126-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="f1126-365">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-365">User physical location</span></span> |  <span data-ttu-id="f1126-366">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="f1126-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="f1126-367">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-367">User phone number</span></span> | <span data-ttu-id="f1126-368">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="f1126-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="f1126-369">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-370">Vietnam</span><span class="sxs-lookup"><span data-stu-id="f1126-370">Vietnam</span></span> | <span data-ttu-id="f1126-371">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="f1126-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="f1126-372">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="f1126-372">+84 4 5555 5555</span></span> | <span data-ttu-id="f1126-373">Priorité 1 : ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="f1126-374">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1126-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="f1126-375">VNsbc.contoso.com : OnlyForLocalUsers Proxysbc.contoso.com – toujours contournement</span><span class="sxs-lookup"><span data-stu-id="f1126-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f1126-376">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement.</span><span class="sxs-lookup"><span data-stu-id="f1126-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f1126-377">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-377">Mode</span></span> | <span data-ttu-id="f1126-378">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-378">User</span></span> | <span data-ttu-id="f1126-379">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-379">Site</span></span> | <span data-ttu-id="f1126-380">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f1126-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="f1126-382">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-382">Internal</span></span> |<span data-ttu-id="f1126-383">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-383">Same as SBC</span></span>   | <span data-ttu-id="f1126-384">Sortant</span><span class="sxs-lookup"><span data-stu-id="f1126-384">Outbound</span></span> |

<span data-ttu-id="f1126-385">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="f1126-386">Ce flux est le même que celui affiché dans les [appels sortants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="f1126-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f1126-388">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement</span><span class="sxs-lookup"><span data-stu-id="f1126-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f1126-389">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-389">Mode</span></span> | <span data-ttu-id="f1126-390">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-390">User</span></span> | <span data-ttu-id="f1126-391">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-391">Site</span></span> | <span data-ttu-id="f1126-392">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f1126-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="f1126-394">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-394">Internal</span></span> | <span data-ttu-id="f1126-395">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-395">Same as SBC</span></span> | <span data-ttu-id="f1126-396">Entrant</span><span class="sxs-lookup"><span data-stu-id="f1126-396">Inbound</span></span> |

<span data-ttu-id="f1126-397">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="f1126-398">Ce flux est le même que celui affiché dans les [appels entrants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="f1126-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="f1126-400">L’utilisateur ne se trouve pas au même emplacement que le SBC mais il se trouve sur le réseau d’entreprise uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="f1126-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="f1126-401">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-401">Mode</span></span> | <span data-ttu-id="f1126-402">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-402">User</span></span> | <span data-ttu-id="f1126-403">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-403">Site</span></span> |<span data-ttu-id="f1126-404">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f1126-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="f1126-406">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-406">Internal</span></span> |   <span data-ttu-id="f1126-407">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-407">Different from SBC</span></span> | <span data-ttu-id="f1126-408">Sortant</span><span class="sxs-lookup"><span data-stu-id="f1126-408">Outbound</span></span> |

<span data-ttu-id="f1126-409">Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configurés sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="f1126-410">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="f1126-412">Les appels entrants et l’utilisateur sont internes, mais ne se trouvent pas dans le même emplacement que l’SBC uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="f1126-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="f1126-413">Veille</span><span class="sxs-lookup"><span data-stu-id="f1126-413">Mode</span></span> |    <span data-ttu-id="f1126-414">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1126-414">User</span></span> |  <span data-ttu-id="f1126-415">Site</span><span class="sxs-lookup"><span data-stu-id="f1126-415">Site</span></span> |  <span data-ttu-id="f1126-416">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="f1126-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="f1126-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="f1126-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="f1126-418">Interne</span><span class="sxs-lookup"><span data-stu-id="f1126-418">Internal</span></span> |    <span data-ttu-id="f1126-419">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="f1126-419">Different from SBC</span></span> |    <span data-ttu-id="f1126-420">Entrant</span><span class="sxs-lookup"><span data-stu-id="f1126-420">Inbound</span></span> |

<span data-ttu-id="f1126-421">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f1126-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-17.png)









