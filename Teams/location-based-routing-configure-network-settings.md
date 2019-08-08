---
title: Configurer les paramètres de réseau pour le routage géodépendant
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des zones, des sites et des sous-réseaux réseau pour le routage direct.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245105"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="b48c8-103">Configurer les paramètres de réseau pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="b48c8-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="b48c8-104">Si vous ne l’avez pas encore fait, lisez [la section routage en fonction de l’emplacement pour le routage direct](location-based-routing-plan.md) pour réviser les autres étapes que vous devez effectuer avant de configurer les paramètres réseau pour le routage en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="b48c8-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="b48c8-105">Cet article décrit comment configurer les paramètres réseau pour le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="b48c8-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="b48c8-106">Après avoir déployé le routage direct du système téléphonique au sein de votre organisation, les étapes suivantes permettent de créer et de configurer les zones du réseau, les sites réseau et les sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="b48c8-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="b48c8-107">Pour suivre les étapes décrites dans cet article, vous devez être familiarisé avec les applets de méthode PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b48c8-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b48c8-108">Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b48c8-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="b48c8-109">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="b48c8-109">Define network regions</span></span>
 <span data-ttu-id="b48c8-110">Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="b48c8-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="b48c8-111">Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) pour définir des régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="b48c8-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="b48c8-112">Notez que le paramètre RegionID est un nom logique qui représente la géographie de la région et qu’il n’y a pas de dépendances ni&gt; de restrictions et que le paramètre d’ID de site CentralSite &lt;est facultatif.</span><span class="sxs-lookup"><span data-stu-id="b48c8-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="b48c8-113">Dans cet exemple, nous créons une région réseau nommée Inde.</span><span class="sxs-lookup"><span data-stu-id="b48c8-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="b48c8-114">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="b48c8-114">Define network sites</span></span>

<span data-ttu-id="b48c8-115">Utilisez l’applet de nouvelle applet de [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="b48c8-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="b48c8-116">Dans cet exemple, nous créons deux nouveaux sites réseau, Delhi et Hyderabad, dans la région Inde.</span><span class="sxs-lookup"><span data-stu-id="b48c8-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="b48c8-117">Le tableau suivant indique les sites réseau définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="b48c8-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="b48c8-118">Site 1</span><span class="sxs-lookup"><span data-stu-id="b48c8-118">Site 1</span></span> |<span data-ttu-id="b48c8-119">Site 2</span><span class="sxs-lookup"><span data-stu-id="b48c8-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b48c8-120">ID de site</span><span class="sxs-lookup"><span data-stu-id="b48c8-120">Site ID</span></span>    |    <span data-ttu-id="b48c8-121">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b48c8-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="b48c8-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b48c8-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="b48c8-123">ID de région</span><span class="sxs-lookup"><span data-stu-id="b48c8-123">Region ID</span></span>  |     <span data-ttu-id="b48c8-124">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="b48c8-124">Region 1 (India)</span></span>    |   <span data-ttu-id="b48c8-125">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="b48c8-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="b48c8-126">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="b48c8-126">Define network subnets</span></span>

<span data-ttu-id="b48c8-127">Utilisez l’applet de nouvelle applet de [nouveau-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux réseau et les associer aux sites du réseau.</span><span class="sxs-lookup"><span data-stu-id="b48c8-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="b48c8-128">Chaque sous-réseau interne ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="b48c8-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="b48c8-129">Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site réseau de Delhi et entre le sous-réseau 2001:4898: E8:25:844e: 926f: 85AD: DD8E et le site du réseau Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b48c8-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="b48c8-130">Le tableau suivant montre les sous-réseaux définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="b48c8-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="b48c8-131">Site 1</span><span class="sxs-lookup"><span data-stu-id="b48c8-131">Site 1</span></span> |<span data-ttu-id="b48c8-132">Site 2</span><span class="sxs-lookup"><span data-stu-id="b48c8-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b48c8-133">ID de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="b48c8-133">Subnet ID</span></span>   |    <span data-ttu-id="b48c8-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="b48c8-134">192.168.0.0</span></span>     |  <span data-ttu-id="b48c8-135">2001:4898: E8:25:844e: 926f: 85AD: DD8E</span><span class="sxs-lookup"><span data-stu-id="b48c8-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="b48c8-136">Réseau</span><span class="sxs-lookup"><span data-stu-id="b48c8-136">Mask</span></span>  |     <span data-ttu-id="b48c8-137">24</span><span class="sxs-lookup"><span data-stu-id="b48c8-137">24</span></span>    |   <span data-ttu-id="b48c8-138">120</span><span class="sxs-lookup"><span data-stu-id="b48c8-138">120</span></span>      |
|<span data-ttu-id="b48c8-139">ID de site</span><span class="sxs-lookup"><span data-stu-id="b48c8-139">Site ID</span></span>  | <span data-ttu-id="b48c8-140">Site (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b48c8-140">Site (Delhi)</span></span> | <span data-ttu-id="b48c8-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b48c8-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="b48c8-142">Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script comme celui-ci.</span><span class="sxs-lookup"><span data-stu-id="b48c8-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="b48c8-143">Dans cet exemple, le fichier CSV ressemble à ceci:</span><span class="sxs-lookup"><span data-stu-id="b48c8-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="b48c8-144">Définir des sous-réseaux externes</span><span class="sxs-lookup"><span data-stu-id="b48c8-144">Define external subnets</span></span>
<span data-ttu-id="b48c8-145">Utilisez l’applet de nouvelle applet de [nouveau-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au client.</span><span class="sxs-lookup"><span data-stu-id="b48c8-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="b48c8-146">Vous pouvez définir un nombre illimité de sous-réseaux pour un client.</span><span class="sxs-lookup"><span data-stu-id="b48c8-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="b48c8-147">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b48c8-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="b48c8-148">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b48c8-148">Next steps</span></span>
<span data-ttu-id="b48c8-149">Accédez à [activer le routage en fonction de l’emplacement pour le routage direct](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="b48c8-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="b48c8-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b48c8-150">Related topics</span></span>
- [<span data-ttu-id="b48c8-151">Planifier le routage géodépendant pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="b48c8-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="b48c8-152">Terminologie du routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="b48c8-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
