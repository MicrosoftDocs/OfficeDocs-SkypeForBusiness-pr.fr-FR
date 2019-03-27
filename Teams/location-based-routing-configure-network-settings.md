---
title: Configurer les paramètres de réseau pour le routage géodépendant
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer les régions réseau, sites et les sous-réseaux pour le routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876767"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="5d14a-103">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="5d14a-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="5d14a-104">Si vous n’avez pas déjà fait, lisez [Plan_Location-Based de routage pour le routage Direct](location-based-routing-plan.md) pour passer en revue les autres étapes que vous devrez prendre avant de configurer les paramètres réseau pour le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="5d14a-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="5d14a-105">Cet article explique comment configurer les paramètres réseau pour le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="5d14a-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="5d14a-106">Une fois que vous déployez l’acheminement d’un système téléphonique Direct dans votre organisation, les étapes suivantes consistent à créer et configurer des régions réseau, sites réseau et sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="5d14a-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="5d14a-107">Pour effectuer les étapes décrites dans cet article, vous aurez besoin de se familiariser avec les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d14a-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5d14a-108">Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5d14a-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="5d14a-109">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="5d14a-109">Define network regions</span></span>
 <span data-ttu-id="5d14a-110">Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="5d14a-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5d14a-111">Utilisez l’applet de commande [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) pour définir des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="5d14a-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="5d14a-112">Notez que le paramètre RegionID est un nom logique qui représente la zone géographique de la région et n’a pas de dépendances ou les restrictions et le CentralSite &lt;ID de site&gt; paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="5d14a-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5d14a-113">Dans cet exemple, nous créons une zone réseau nommée Inde.</span><span class="sxs-lookup"><span data-stu-id="5d14a-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="5d14a-114">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="5d14a-114">Define network sites</span></span>

<span data-ttu-id="5d14a-115">Utilisez l’applet de commande [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="5d14a-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="5d14a-116">Dans cet exemple, nous créons deux nouveaux sites réseau, Delhi et Hyderabad, dans la zone Inde.</span><span class="sxs-lookup"><span data-stu-id="5d14a-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="5d14a-117">Le tableau suivant indique les sites de réseau définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5d14a-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="5d14a-118">Site 1</span><span class="sxs-lookup"><span data-stu-id="5d14a-118">Site 1</span></span> |<span data-ttu-id="5d14a-119">Site 2</span><span class="sxs-lookup"><span data-stu-id="5d14a-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5d14a-120">ID de site</span><span class="sxs-lookup"><span data-stu-id="5d14a-120">Site ID</span></span>    |    <span data-ttu-id="5d14a-121">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="5d14a-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="5d14a-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5d14a-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="5d14a-123">ID de région</span><span class="sxs-lookup"><span data-stu-id="5d14a-123">Region ID</span></span>  |     <span data-ttu-id="5d14a-124">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="5d14a-124">Region 1 (India)</span></span>    |   <span data-ttu-id="5d14a-125">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="5d14a-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="5d14a-126">Définir les sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="5d14a-126">Define network subnets</span></span>

<span data-ttu-id="5d14a-127">Utilisez l’applet de commande [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir les sous-réseaux et les associer aux sites du réseau.</span><span class="sxs-lookup"><span data-stu-id="5d14a-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="5d14a-128">Chaque sous-réseau interne ne peut être associé à un site.</span><span class="sxs-lookup"><span data-stu-id="5d14a-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="5d14a-129">Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site de réseau Delhi et entre le sous-réseau 192.168.1.0 et le site d’Hyderabad réseau.</span><span class="sxs-lookup"><span data-stu-id="5d14a-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="5d14a-130">Le tableau suivant indique les sous-réseaux définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5d14a-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="5d14a-131">Site 1</span><span class="sxs-lookup"><span data-stu-id="5d14a-131">Site 1</span></span> |<span data-ttu-id="5d14a-132">Site 2</span><span class="sxs-lookup"><span data-stu-id="5d14a-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5d14a-133">ID de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="5d14a-133">Subnet ID</span></span>   |    <span data-ttu-id="5d14a-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="5d14a-134">192.168.0.0</span></span>     |  <span data-ttu-id="5d14a-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="5d14a-135">192.168.1.0</span></span>     |
|<span data-ttu-id="5d14a-136">Masque</span><span class="sxs-lookup"><span data-stu-id="5d14a-136">Mask</span></span>  |     <span data-ttu-id="5d14a-137">24</span><span class="sxs-lookup"><span data-stu-id="5d14a-137">24</span></span>    |   <span data-ttu-id="5d14a-138">24</span><span class="sxs-lookup"><span data-stu-id="5d14a-138">24</span></span>      |
|<span data-ttu-id="5d14a-139">ID de site</span><span class="sxs-lookup"><span data-stu-id="5d14a-139">Site ID</span></span>  | <span data-ttu-id="5d14a-140">Site (Delhi)</span><span class="sxs-lookup"><span data-stu-id="5d14a-140">Site (Delhi)</span></span> | <span data-ttu-id="5d14a-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5d14a-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="5d14a-142">Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script, telles que les suivantes.</span><span class="sxs-lookup"><span data-stu-id="5d14a-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="5d14a-143">Dans cet exemple, le fichier CSV se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="5d14a-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="5d14a-144">Définir les sous-réseaux externes</span><span class="sxs-lookup"><span data-stu-id="5d14a-144">Define external subnets</span></span>
<span data-ttu-id="5d14a-145">Utilisez l’applet de commande [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir les sous-réseaux externes et les assigner au client.</span><span class="sxs-lookup"><span data-stu-id="5d14a-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="5d14a-146">Vous pouvez définir un nombre illimité de sous-réseaux pour un client.</span><span class="sxs-lookup"><span data-stu-id="5d14a-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="5d14a-147">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5d14a-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="5d14a-148">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="5d14a-148">Next steps</span></span>
<span data-ttu-id="5d14a-149">Accédez à [Activer le routage par emplacement pour le routage Direct](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="5d14a-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="5d14a-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5d14a-150">Related topics</span></span>
- [<span data-ttu-id="5d14a-151">Planifier le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="5d14a-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="5d14a-152">Terminologie du routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="5d14a-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
