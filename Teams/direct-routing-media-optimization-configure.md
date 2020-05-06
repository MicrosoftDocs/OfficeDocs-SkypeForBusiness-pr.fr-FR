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
ms.openlocfilehash: 518445e10b757adc9a21c426fb885bb04b7a878b
ms.sourcegitcommit: b143611d14765af054a4f84cca52e2003d35af1a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44047853"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="1a7de-103">Configurer l’optimisation locale des médias pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="1a7de-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="1a7de-104">La configuration de l’optimisation des éléments multimédias locaux est basée sur les paramètres réseau communs aux autres fonctionnalités de voix Cloud, telles que le routage par emplacement et les appels d’urgence dynamiques.</span><span class="sxs-lookup"><span data-stu-id="1a7de-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="1a7de-105">Pour en savoir plus sur les zones du réseau, les sites réseau, les sous-réseaux réseau et les adresses IP de confiance, voir [paramètres réseau pour les fonctionnalités vocales dans le Cloud](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1a7de-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="1a7de-106">Avant de configurer l’optimisation de média locale, voir [optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="1a7de-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="1a7de-107">Pour configurer l’optimisation de média locale, les étapes suivantes sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1a7de-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="1a7de-108">Vous pouvez utiliser le centre d’administration teams ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a7de-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="1a7de-109">Pour plus d’informations, voir [gérer la topologie de votre réseau](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="1a7de-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="1a7de-110">Configurez les sites utilisateur et SBC (comme décrit dans cet article).</span><span class="sxs-lookup"><span data-stu-id="1a7de-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="1a7de-111">Configurez l’application SBCs pour l’optimisation de média locale (en fonction de la spécification de votre fournisseur SBC).</span><span class="sxs-lookup"><span data-stu-id="1a7de-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="1a7de-112">Le diagramme suivant montre la configuration du réseau utilisée dans les exemples de cet article.</span><span class="sxs-lookup"><span data-stu-id="1a7de-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="1a7de-113">![Diagramme illustrant la configuration réseau pour les exemples](media/direct-routing-media-op-9.png "Configuration du réseau pour les exemples")</span><span class="sxs-lookup"><span data-stu-id="1a7de-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="1a7de-114">Configurer l’utilisateur et les sites SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="1a7de-115">Pour configurer l’utilisateur et les sites SBC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="1a7de-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="1a7de-116">[Gérer les adresses IP de confiance externes](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="1a7de-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="1a7de-117">[Définissez la topologie du réseau](#define-the-network-topology) en configurant les zones du réseau, les sites réseau et les sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="1a7de-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="1a7de-118">[Définissez la topologie du réseau virtuel](#define-the-virtual-network-topology) en assignant des SBC (s) aux sites avec des modes pertinents et des valeurs SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="1a7de-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="1a7de-119">Configurer des SBC pour optimiser les médias locaux conformément à la spécification du fournisseur de SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="1a7de-120">Cet article décrit la configuration des composants Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a7de-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="1a7de-121">Pour plus d’informations sur la configuration d’un SBC, voir votre fournisseur de SBC documenation.</span><span class="sxs-lookup"><span data-stu-id="1a7de-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="1a7de-122">L’optimisation des éléments multimédias locaux est prise en charge par les fournisseurs de SBC suivants :</span><span class="sxs-lookup"><span data-stu-id="1a7de-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="1a7de-123">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="1a7de-123">Vendor</span></span> | <span data-ttu-id="1a7de-124">Product</span><span class="sxs-lookup"><span data-stu-id="1a7de-124">Product</span></span> |    <span data-ttu-id="1a7de-125">Version du logiciel</span><span class="sxs-lookup"><span data-stu-id="1a7de-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="1a7de-126">CodesAudio</span><span class="sxs-lookup"><span data-stu-id="1a7de-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="1a7de-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="1a7de-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="1a7de-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="1a7de-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="1a7de-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-135">1000B SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="1a7de-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-137">SBC-9000</span><span class="sxs-lookup"><span data-stu-id="1a7de-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="1a7de-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-139">SBC-édition virtuelle-SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="1a7de-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a7de-141">SBC édition Cloud-SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="1a7de-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="1a7de-142">7.20A.256</span></span> |
| [<span data-ttu-id="1a7de-143">Noyau SBC du ruban</span><span class="sxs-lookup"><span data-stu-id="1a7de-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="1a7de-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="1a7de-144">SBC 5110</span></span>         | <span data-ttu-id="1a7de-145">8,2</span><span class="sxs-lookup"><span data-stu-id="1a7de-145">8.2</span></span>  |
|            |  <span data-ttu-id="1a7de-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="1a7de-146">SBC 5210</span></span>         | <span data-ttu-id="1a7de-147">8,2</span><span class="sxs-lookup"><span data-stu-id="1a7de-147">8.2</span></span>  |
|            |  <span data-ttu-id="1a7de-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="1a7de-148">SBC 5400</span></span>         | <span data-ttu-id="1a7de-149">8,2</span><span class="sxs-lookup"><span data-stu-id="1a7de-149">8.2</span></span>  |
|            |  <span data-ttu-id="1a7de-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="1a7de-150">SBC 7000</span></span>         | <span data-ttu-id="1a7de-151">8,2</span><span class="sxs-lookup"><span data-stu-id="1a7de-151">8.2</span></span>  |
|            |  <span data-ttu-id="1a7de-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="1a7de-152">SBC SWe</span></span>          | <span data-ttu-id="1a7de-153">8,2</span><span class="sxs-lookup"><span data-stu-id="1a7de-153">8.2</span></span>  |
| [<span data-ttu-id="1a7de-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="1a7de-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="1a7de-155">anynode</span><span class="sxs-lookup"><span data-stu-id="1a7de-155">anynode</span></span>          | <span data-ttu-id="1a7de-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="1a7de-156">4.0.1+</span></span> |
| [<span data-ttu-id="1a7de-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="1a7de-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="1a7de-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="1a7de-158">AP 1100</span></span> | <span data-ttu-id="1a7de-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a7de-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="1a7de-160">AP 3900</span></span> | <span data-ttu-id="1a7de-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a7de-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="1a7de-162">AP 4600</span></span> | <span data-ttu-id="1a7de-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1a7de-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="1a7de-164">AP 6300</span></span> | <span data-ttu-id="1a7de-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a7de-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="1a7de-166">AP 6350</span></span> | <span data-ttu-id="1a7de-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1a7de-168">VME</span><span class="sxs-lookup"><span data-stu-id="1a7de-168">VME</span></span>     | <span data-ttu-id="1a7de-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a7de-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="1a7de-170">Gérer les adresses IP de confiance externes</span><span class="sxs-lookup"><span data-stu-id="1a7de-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="1a7de-171">Les adresses IP approuvées externes sont les adresses IP externes Internet du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a7de-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="1a7de-172">Ces adresses IP sont utilisées par les clients Microsoft teams lorsqu’ils se connectent à Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a7de-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="1a7de-173">Vous devez ajouter ces adresses IP externes pour chaque site sur lequel les utilisateurs ont recours à une optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="1a7de-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="1a7de-174">Pour ajouter les adresses IP publiques pour chaque site, utilisez l’applet de nouvelle applet de nouveau-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="1a7de-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="1a7de-175">Vous pouvez définir un nombre illimité d’adresses IP de confiance pour un client.</span><span class="sxs-lookup"><span data-stu-id="1a7de-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="1a7de-176">Si la prévention des intrusions externes observée par Microsoft 365 est une adresse IPv4 et IPv6, vous devez ajouter les deux types d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="1a7de-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="1a7de-177">Pour IPv4, utilisez Mask 32.</span><span class="sxs-lookup"><span data-stu-id="1a7de-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="1a7de-178">Pour IPv6, utilisez Mask 128.</span><span class="sxs-lookup"><span data-stu-id="1a7de-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="1a7de-179">Vous pouvez ajouter des adresses IP externes individuelles et des sous-réseaux IP externes en spécifiant des MaskBits différentes sur l’applet de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a7de-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="1a7de-180">Exemple d’ajout d’adresses IP approuvées.</span><span class="sxs-lookup"><span data-stu-id="1a7de-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="1a7de-181">Définissez la topologie du réseau.</span><span class="sxs-lookup"><span data-stu-id="1a7de-181">Define the network topology</span></span>

<span data-ttu-id="1a7de-182">Cette section décrit comment définir les régions réseau, les sites réseau et les sous-réseaux pour votre topologie réseau.</span><span class="sxs-lookup"><span data-stu-id="1a7de-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="1a7de-183">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="1a7de-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="1a7de-184">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="1a7de-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="1a7de-185">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="1a7de-185">Define network regions</span></span>

<span data-ttu-id="1a7de-186">Pour définir les zones du réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="1a7de-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="1a7de-187">Le paramètre RegionID est un nom logique qui représente la géographie de la région et qui ne possède pas de dépendances ni de restrictions.</span><span class="sxs-lookup"><span data-stu-id="1a7de-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="1a7de-188">Le paramètre <site ID> CentralSite est facultatif.</span><span class="sxs-lookup"><span data-stu-id="1a7de-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="1a7de-189">L’exemple suivant permet de créer une zone de réseau nommée APAC :</span><span class="sxs-lookup"><span data-stu-id="1a7de-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="1a7de-190">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="1a7de-190">Define network sites</span></span>

<span data-ttu-id="1a7de-191">Pour définir des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="1a7de-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="1a7de-192">Chaque site réseau doit être associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="1a7de-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="1a7de-193">L’exemple suivant crée trois nouveaux sites réseau, le Viêt Nam, l’Indonésie et Singapour dans la région APAC :</span><span class="sxs-lookup"><span data-stu-id="1a7de-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="1a7de-194">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="1a7de-194">Define network subnets</span></span>

<span data-ttu-id="1a7de-195">Pour définir des sous-réseaux réseau et les associer à des sites réseau, utilisez l’applet de nouvelle applet de nouveau-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="1a7de-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="1a7de-196">Chaque sous-réseau ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="1a7de-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="1a7de-197">L’exemple suivant définit trois sous-réseaux réseau et les associe aux trois sites réseau : Vietnam, Indonésie et Singapour :</span><span class="sxs-lookup"><span data-stu-id="1a7de-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="1a7de-198">Définir la topologie du réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="1a7de-198">Define the virtual network topology</span></span> 

<span data-ttu-id="1a7de-199">Tout d’abord, l’administrateur client crée une nouvelle configuration SBC pour chaque SBC appropriée à l’aide de l’applet de nouvelle cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="1a7de-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="1a7de-200">L’administrateur client définit la topologie du réseau virtuel en spécifiant les sites réseau pour les objets passerelle PSTN à l’aide de l’applet de connexion Set-CsOnlinePSTNGateway :</span><span class="sxs-lookup"><span data-stu-id="1a7de-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="1a7de-201">Notez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1a7de-201">Note the following:</span></span> 
   - <span data-ttu-id="1a7de-202">Si le client dispose d’un SBC unique, le paramètre-ProxySBC doit être obligatoire $null ou une valeur de nom de domaine complet (SBC) (central SBC avec des troncs centralisés).</span><span class="sxs-lookup"><span data-stu-id="1a7de-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="1a7de-203">Le paramètre-MediaBypass doit être défini sur $true afin de prendre en charge l’optimisation de média locale.</span><span class="sxs-lookup"><span data-stu-id="1a7de-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="1a7de-204">Si le SBC ne dispose pas du jeu de paramètres-BypassMode, les en-têtes X-MS ne seront pas envoyés.</span><span class="sxs-lookup"><span data-stu-id="1a7de-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="1a7de-205">Tous les paramètres respectent la casse, de sorte que vous devez vous assurer que vous utilisez la même casse que celle utilisée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="1a7de-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="1a7de-206">(Par exemple, les valeurs GatewaySiteID "Vietnam" et "Viêt Nam" seront considérées comme des sites différents.)</span><span class="sxs-lookup"><span data-stu-id="1a7de-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="1a7de-207">L’exemple suivant ajoute trois SBCs aux sites réseau Vietnam, Indonésie et Singapour dans la région APAC avec le mode toujours contournement :</span><span class="sxs-lookup"><span data-stu-id="1a7de-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="1a7de-208">Remarque : pour garantir des opérations ininterrompues lors de la configuration de l’optimisation des médias locaux et du routage basé sur l’emplacement (LBR) en même temps, l’option SBCs en aval doit être activée pour LBR en définissant le paramètre GatewaySiteLbrEnabled sur $true pour chaque SBC en aval.</span><span class="sxs-lookup"><span data-stu-id="1a7de-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="1a7de-209">(Ce paramètre n’est pas obligatoire pour l’SBC proxy.)</span><span class="sxs-lookup"><span data-stu-id="1a7de-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="1a7de-210">D’après les informations ci-dessus, le routage direct inclura trois en-têtes SIP propriétaires aux invitations SIP et aux Réinvitations, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1a7de-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="1a7de-211">Les en-têtes X-MS introduites dans le routage direct sur les invitations et les Réinvitations si BypassMode est défini :</span><span class="sxs-lookup"><span data-stu-id="1a7de-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="1a7de-212">Nom de l’en-tête</span><span class="sxs-lookup"><span data-stu-id="1a7de-212">Header name</span></span> | <span data-ttu-id="1a7de-213">Doubl</span><span class="sxs-lookup"><span data-stu-id="1a7de-213">Values</span></span> | <span data-ttu-id="1a7de-214">Commentaires</span><span class="sxs-lookup"><span data-stu-id="1a7de-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="1a7de-215">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="1a7de-215">X-MS-UserLocation</span></span> | <span data-ttu-id="1a7de-216">interne/externe</span><span class="sxs-lookup"><span data-stu-id="1a7de-216">internal/external</span></span> | <span data-ttu-id="1a7de-217">Indique si l’utilisateur est interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="1a7de-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="1a7de-218">Requête-URL d’URL SIP : + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="1a7de-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="1a7de-219">NOM DE DOMAINE COMPLET SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-219">SBC FQDN</span></span> | <span data-ttu-id="1a7de-220">Nom de domaine complet ciblé pour l’appel, même si l’SBC n’est pas directement connecté au routage direct</span><span class="sxs-lookup"><span data-stu-id="1a7de-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="1a7de-221">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="1a7de-221">X-MS-MediaPath</span></span> | <span data-ttu-id="1a7de-222">Par exemple : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="1a7de-223">Ordre de SBCs à utiliser pour le chemin d’accès multimédia entre l’utilisateur et le SBC cible.</span><span class="sxs-lookup"><span data-stu-id="1a7de-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="1a7de-224">Le SBC final est toujours le dernier.</span><span class="sxs-lookup"><span data-stu-id="1a7de-224">The final SBC is always last</span></span> |
| <span data-ttu-id="1a7de-225">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="1a7de-225">X-MS-UserSite</span></span> | <span data-ttu-id="1a7de-226">usersiteID</span><span class="sxs-lookup"><span data-stu-id="1a7de-226">usersiteID</span></span> | <span data-ttu-id="1a7de-227">Chaîne définie par l’administrateur client</span><span class="sxs-lookup"><span data-stu-id="1a7de-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="1a7de-228">Flux d’appels</span><span class="sxs-lookup"><span data-stu-id="1a7de-228">Call flows</span></span> 

<span data-ttu-id="1a7de-229">Le code suivant montre les flux d’appels pour deux modes :</span><span class="sxs-lookup"><span data-stu-id="1a7de-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="1a7de-230">Contournement permanent</span><span class="sxs-lookup"><span data-stu-id="1a7de-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="1a7de-231">Uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="1a7de-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="1a7de-232">Mode de contournement toujours</span><span class="sxs-lookup"><span data-stu-id="1a7de-232">Always Bypass mode</span></span>

<span data-ttu-id="1a7de-233">Le mode de contournement toujours est l’option la plus simple à configurer.</span><span class="sxs-lookup"><span data-stu-id="1a7de-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="1a7de-234">L’administrateur client peut configurer un seul site pour tous les utilisateurs et SBCs s’il est joignable sur n’importe quel site.</span><span class="sxs-lookup"><span data-stu-id="1a7de-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="1a7de-235">Les exemples indiquent toujours le mode de contournement pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="1a7de-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="1a7de-236">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1a7de-237">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1a7de-238">Appels sortants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="1a7de-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="1a7de-239">Appels entrants et l’utilisateur est externe</span><span class="sxs-lookup"><span data-stu-id="1a7de-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="1a7de-240">Le tableau suivant répertorie les adresses de domaine complets et les adresses IP utilisées dans les exemples :</span><span class="sxs-lookup"><span data-stu-id="1a7de-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="1a7de-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="1a7de-241">FQDN</span></span> | <span data-ttu-id="1a7de-242">Adresse IP externe d’une SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-242">SBC external IP address</span></span> | <span data-ttu-id="1a7de-243">Adresse IP interne de SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-243">SBC internal IP Address</span></span> | <span data-ttu-id="1a7de-244">Sous-réseau interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-244">Internal subnet</span></span> | <span data-ttu-id="1a7de-245">Lieu</span><span class="sxs-lookup"><span data-stu-id="1a7de-245">Location</span></span> | <span data-ttu-id="1a7de-246">NAT externe (IP de confiance)</span><span class="sxs-lookup"><span data-stu-id="1a7de-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="1a7de-248">Aucun</span><span class="sxs-lookup"><span data-stu-id="1a7de-248">None</span></span> | <span data-ttu-id="1a7de-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="1a7de-249">192.168.1.5</span></span> | <span data-ttu-id="1a7de-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="1a7de-250">192.168.1.0/24</span></span> | <span data-ttu-id="1a7de-251">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a7de-251">Vietnam</span></span> | <span data-ttu-id="1a7de-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="1a7de-252">172.16.240.110</span></span> |
| <span data-ttu-id="1a7de-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="1a7de-254">Aucun</span><span class="sxs-lookup"><span data-stu-id="1a7de-254">None</span></span> | <span data-ttu-id="1a7de-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="1a7de-255">192.168.2.5</span></span> | <span data-ttu-id="1a7de-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="1a7de-256">192.168.2.0/24</span></span> | <span data-ttu-id="1a7de-257">Indonésie</span><span class="sxs-lookup"><span data-stu-id="1a7de-257">Indonesia</span></span> | <span data-ttu-id="1a7de-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="1a7de-258">172.16.240.120</span></span> |
| <span data-ttu-id="1a7de-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="1a7de-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="1a7de-260">172.16.240.133</span></span> | <span data-ttu-id="1a7de-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="1a7de-261">192.168.3.5</span></span> | <span data-ttu-id="1a7de-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="1a7de-262">192.168.3.0/24</span></span> | <span data-ttu-id="1a7de-263">Singapour</span><span class="sxs-lookup"><span data-stu-id="1a7de-263">Singapore</span></span> | <span data-ttu-id="1a7de-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="1a7de-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1a7de-265">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1a7de-266">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-266">Mode</span></span> |    <span data-ttu-id="1a7de-267">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-267">User</span></span> |  <span data-ttu-id="1a7de-268">Lieu</span><span class="sxs-lookup"><span data-stu-id="1a7de-268">Location</span></span> |  <span data-ttu-id="1a7de-269">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="1a7de-270">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a7de-270">AlwaysBypass</span></span> |    <span data-ttu-id="1a7de-271">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-271">Internal</span></span> |  <span data-ttu-id="1a7de-272">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-272">The same site as SBC</span></span> |  <span data-ttu-id="1a7de-273">Sortant</span><span class="sxs-lookup"><span data-stu-id="1a7de-273">Outbound</span></span> |

<span data-ttu-id="1a7de-274">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="1a7de-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="1a7de-275">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-275">User physical location</span></span>| <span data-ttu-id="1a7de-276">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="1a7de-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="1a7de-277">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-277">User phone number</span></span>  | <span data-ttu-id="1a7de-278">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="1a7de-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="1a7de-279">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-280">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a7de-280">Vietnam</span></span> | <span data-ttu-id="1a7de-281">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1a7de-281">+84 4 3926 3000</span></span> | <span data-ttu-id="1a7de-282">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1a7de-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="1a7de-283">Priorité 1 : ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1a7de-284">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="1a7de-285">VNsbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="1a7de-286">proxysbc.contoso.com : toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="1a7de-287">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode toujours Bypass et l’utilisateur au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="1a7de-288">![Diagramme montrant les appels sortants](media/direct-routing-media-op-10.png "Appels sortants")</span><span class="sxs-lookup"><span data-stu-id="1a7de-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="1a7de-289">Le tableau suivant montre les en-têtes X-MS envoyés par le routage direct :</span><span class="sxs-lookup"><span data-stu-id="1a7de-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="1a7de-290">Paramètre</span><span class="sxs-lookup"><span data-stu-id="1a7de-290">Parameter</span></span> | <span data-ttu-id="1a7de-291">Explication</span><span class="sxs-lookup"><span data-stu-id="1a7de-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="1a7de-292">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1a7de-293">Le nom de la cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête.</span><span class="sxs-lookup"><span data-stu-id="1a7de-293">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="1a7de-294">X-MS-UserLocation : Internal</span><span class="sxs-lookup"><span data-stu-id="1a7de-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="1a7de-295">Le champ indique que cet utilisateur se trouve à l’intérieur du réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="1a7de-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="1a7de-296">X-MS-MediaPath : VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="1a7de-297">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="1a7de-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1a7de-298">Dans le cas présent, il n’existe pas de contournement, et le client est en interne le nom de cible envoyé en tant que nom unique dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="1a7de-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="1a7de-299">X-MS-UserSite : Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a7de-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="1a7de-300">Le champ indiqué dans le site de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a7de-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1a7de-301">Appels entrants et l’utilisateur se trouve dans le même emplacement que l’SBC avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1a7de-302">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-302">Mode</span></span> |    <span data-ttu-id="1a7de-303">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-303">User</span></span> |  <span data-ttu-id="1a7de-304">Lieu</span><span class="sxs-lookup"><span data-stu-id="1a7de-304">Location</span></span> |  <span data-ttu-id="1a7de-305">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-306">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a7de-306">AlwaysBypass</span></span> |    <span data-ttu-id="1a7de-307">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-307">Internal</span></span> | <span data-ttu-id="1a7de-308">Même site qu’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-308">The same site as SBC</span></span> | <span data-ttu-id="1a7de-309">Entrant</span><span class="sxs-lookup"><span data-stu-id="1a7de-309">Inbound</span></span> |


<span data-ttu-id="1a7de-310">Lors d’un appel entrant, l’emplacement de l’utilisateur est inconnu et l’SBC doit deviner l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a7de-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="1a7de-311">Si l’estimation n’est pas correcte, une nouvelle invitation sera requise.</span><span class="sxs-lookup"><span data-stu-id="1a7de-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="1a7de-312">Dans le cas présent, l’utilisateur est interne, le média peut être acheminé directement et aucune action supplémentaire n’est nécessaire (réinvitation).</span><span class="sxs-lookup"><span data-stu-id="1a7de-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="1a7de-313">Le SBC connecté au service de routage direct rapporte l’emplacement de l’SBC d’origine en fournissant des champs d’itinéraire d’enregistrement et de contact.</span><span class="sxs-lookup"><span data-stu-id="1a7de-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="1a7de-314">En fonction de ces champs, le chemin multimédia est calculé par le routage direct.</span><span class="sxs-lookup"><span data-stu-id="1a7de-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="1a7de-315">Remarque : étant donné qu’un utilisateur peut avoir plusieurs points de terminaison, la prise en charge d' 183 n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="1a7de-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="1a7de-316">Dans le cas présent, le routage direct utilise toujours la sonnerie 180.</span><span class="sxs-lookup"><span data-stu-id="1a7de-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="1a7de-317">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1a7de-319">Les appels sortants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1a7de-320">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-320">Mode</span></span> |    <span data-ttu-id="1a7de-321">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-321">User</span></span> |  <span data-ttu-id="1a7de-322">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-322">Site</span></span> |  <span data-ttu-id="1a7de-323">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1a7de-324">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a7de-324">AlwaysBypass</span></span> |  <span data-ttu-id="1a7de-325">Externe</span><span class="sxs-lookup"><span data-stu-id="1a7de-325">External</span></span> |  <span data-ttu-id="1a7de-326">N/A</span><span class="sxs-lookup"><span data-stu-id="1a7de-326">N/A</span></span> | <span data-ttu-id="1a7de-327">Sortant</span><span class="sxs-lookup"><span data-stu-id="1a7de-327">Outbound</span></span> |


<span data-ttu-id="1a7de-328">Le diagramme suivant illustre l’échelle SIP pour un appel sortant avec le mode AlwaysBypass et l’utilisateur est externe :</span><span class="sxs-lookup"><span data-stu-id="1a7de-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="1a7de-330">Le tableau suivant montre les en-têtes X-MS envoyés par le service de routage directe :</span><span class="sxs-lookup"><span data-stu-id="1a7de-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="1a7de-331">Paramètre</span><span class="sxs-lookup"><span data-stu-id="1a7de-331">Parameter</span></span> |   <span data-ttu-id="1a7de-332">Explication</span><span class="sxs-lookup"><span data-stu-id="1a7de-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="1a7de-333">Inviter + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1a7de-334">Le nom de la cible de l’SBC tel qu’il est défini dans la stratégie de routage de la voix en ligne est envoyé dans l’URI de requête.</span><span class="sxs-lookup"><span data-stu-id="1a7de-334">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="1a7de-335">X-MS-UserLocation : externes</span><span class="sxs-lookup"><span data-stu-id="1a7de-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="1a7de-336">Le champ indique que cet utilisateur se trouve en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a7de-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="1a7de-337">X-MS-MediaPath : proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="1a7de-338">Spécifie la SBC que le client doit traverser vers l’SBC cible.</span><span class="sxs-lookup"><span data-stu-id="1a7de-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1a7de-339">Dans le cas présent, il n’existe pas de contournement, et le client est externe.</span><span class="sxs-lookup"><span data-stu-id="1a7de-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1a7de-340">Les appels entrants et l’utilisateur est externe avec toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1a7de-341">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-341">Mode</span></span> | <span data-ttu-id="1a7de-342">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-342">User</span></span> | <span data-ttu-id="1a7de-343">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-343">Site</span></span> |  <span data-ttu-id="1a7de-344">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1a7de-345">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a7de-345">AlwaysBypass</span></span> |  <span data-ttu-id="1a7de-346">Externe</span><span class="sxs-lookup"><span data-stu-id="1a7de-346">External</span></span> |  <span data-ttu-id="1a7de-347">N/A</span><span class="sxs-lookup"><span data-stu-id="1a7de-347">N/A</span></span> |   <span data-ttu-id="1a7de-348">Entrant</span><span class="sxs-lookup"><span data-stu-id="1a7de-348">Inbound</span></span> |

<span data-ttu-id="1a7de-349">Dans le cas d’un appel entrant, l’appel SBC connecté au routage direct doit envoyer une nouvelle invitation (par défaut, les candidats de média local sont toujours proposés) si l’emplacement de l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="1a7de-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="1a7de-350">Le X-MediaPath est calculé en fonction de record-route et de l’utilisateur SBC spécifié.</span><span class="sxs-lookup"><span data-stu-id="1a7de-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="1a7de-351">Le diagramme suivant illustre l’échelle SIP pour un appel entrant avec le mode AlwaysBypass et l’utilisateur est externe.</span><span class="sxs-lookup"><span data-stu-id="1a7de-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="1a7de-353">Uniquement pour le mode utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="1a7de-353">Only for local users mode</span></span>

<span data-ttu-id="1a7de-354">Les médias de médias locaux des SBC cibles seront proposés uniquement si un utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="1a7de-355">Dans tous les autres cas, le contenu multimédia passe par l’intermédiaire d’une adresse IP interne ou externe du proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="1a7de-356">Les scénarios suivants sont décrits :</span><span class="sxs-lookup"><span data-stu-id="1a7de-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="1a7de-357">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1a7de-358">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1a7de-359">L’utilisateur ne se trouve pas au même emplacement que l’SBC mais il se trouve dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a7de-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="1a7de-360">Les appels entrants et l’utilisateur est interne, mais pas au même emplacement que l’SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="1a7de-361">Le tableau suivant montre la configuration et l’action de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="1a7de-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="1a7de-362">Emplacement physique de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-362">User physical location</span></span> |  <span data-ttu-id="1a7de-363">Un utilisateur effectue ou reçoit un appel vers ou à partir du numéro</span><span class="sxs-lookup"><span data-stu-id="1a7de-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="1a7de-364">Numéro de téléphone de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-364">User phone number</span></span> | <span data-ttu-id="1a7de-365">Politique de routage de la voix en ligne</span><span class="sxs-lookup"><span data-stu-id="1a7de-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="1a7de-366">Mode configuré pour SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-367">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a7de-367">Vietnam</span></span> | <span data-ttu-id="1a7de-368">commande + 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1a7de-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="1a7de-369">commande + 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1a7de-369">+84 4 5555 5555</span></span> | <span data-ttu-id="1a7de-370">Priorité 1 : ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1a7de-371">Priorité 2 :. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a7de-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="1a7de-372">VNsbc.contoso.com : OnlyForLocalUsers Proxysbc.contoso.com – toujours contournement</span><span class="sxs-lookup"><span data-stu-id="1a7de-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a7de-373">Les appels sortants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement.</span><span class="sxs-lookup"><span data-stu-id="1a7de-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a7de-374">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-374">Mode</span></span> | <span data-ttu-id="1a7de-375">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-375">User</span></span> | <span data-ttu-id="1a7de-376">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-376">Site</span></span> | <span data-ttu-id="1a7de-377">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a7de-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1a7de-379">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-379">Internal</span></span> |<span data-ttu-id="1a7de-380">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-380">Same as SBC</span></span>   | <span data-ttu-id="1a7de-381">Sortant</span><span class="sxs-lookup"><span data-stu-id="1a7de-381">Outbound</span></span> |

<span data-ttu-id="1a7de-382">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1a7de-383">Ce flux est le même que celui affiché dans les [appels sortants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="1a7de-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a7de-385">Appels entrants et l’utilisateur se trouve au même emplacement que l’SBC pour les utilisateurs locaux uniquement</span><span class="sxs-lookup"><span data-stu-id="1a7de-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a7de-386">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-386">Mode</span></span> | <span data-ttu-id="1a7de-387">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-387">User</span></span> | <span data-ttu-id="1a7de-388">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-388">Site</span></span> | <span data-ttu-id="1a7de-389">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a7de-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1a7de-391">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-391">Internal</span></span> | <span data-ttu-id="1a7de-392">Identique à SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-392">Same as SBC</span></span> | <span data-ttu-id="1a7de-393">Entrant</span><span class="sxs-lookup"><span data-stu-id="1a7de-393">Inbound</span></span> |

<span data-ttu-id="1a7de-394">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et l’utilisateur se trouve au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1a7de-395">Ce flux est le même que celui affiché dans les [appels entrants lorsque l’utilisateur se trouve au même emplacement que l’SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="1a7de-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="1a7de-397">L’utilisateur ne se trouve pas au même emplacement que le SBC mais il se trouve sur le réseau d’entreprise uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="1a7de-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="1a7de-398">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-398">Mode</span></span> | <span data-ttu-id="1a7de-399">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-399">User</span></span> | <span data-ttu-id="1a7de-400">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-400">Site</span></span> |<span data-ttu-id="1a7de-401">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a7de-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="1a7de-403">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-403">Internal</span></span> |   <span data-ttu-id="1a7de-404">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-404">Different from SBC</span></span> | <span data-ttu-id="1a7de-405">Sortant</span><span class="sxs-lookup"><span data-stu-id="1a7de-405">Outbound</span></span> |

<span data-ttu-id="1a7de-406">Le routage direct calcule X-MediaPath en fonction de l’emplacement signalé de l’utilisateur et du mode configurés sur l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="1a7de-407">Le diagramme suivant montre un appel sortant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a7de-409">Les appels entrants et l’utilisateur sont internes, mais ne se trouvent pas dans le même emplacement que l’SBC uniquement pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="1a7de-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a7de-410">Veille</span><span class="sxs-lookup"><span data-stu-id="1a7de-410">Mode</span></span> |    <span data-ttu-id="1a7de-411">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a7de-411">User</span></span> |  <span data-ttu-id="1a7de-412">Site</span><span class="sxs-lookup"><span data-stu-id="1a7de-412">Site</span></span> |  <span data-ttu-id="1a7de-413">Direction de l’appel</span><span class="sxs-lookup"><span data-stu-id="1a7de-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a7de-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a7de-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="1a7de-415">Interne</span><span class="sxs-lookup"><span data-stu-id="1a7de-415">Internal</span></span> |    <span data-ttu-id="1a7de-416">Différent de SBC</span><span class="sxs-lookup"><span data-stu-id="1a7de-416">Different from SBC</span></span> |    <span data-ttu-id="1a7de-417">Entrant</span><span class="sxs-lookup"><span data-stu-id="1a7de-417">Inbound</span></span> |

<span data-ttu-id="1a7de-418">Le diagramme suivant montre un appel entrant avec le mode OnlyForLocalUsers et un utilisateur interne qui n’est pas au même emplacement que l’SBC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramme montrant l’échelle SIP](media/direct-routing-media-op-17.png)









