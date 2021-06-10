---
title: Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment configurer les paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams.
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101060"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="5342a-103">Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5342a-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="5342a-104">Si votre organisation déploie le routage basé sur l’emplacement pour le [routage](location-based-routing-plan.md) direct ou les appels d’urgence [dynamiques,](configure-dynamic-emergency-calling.md)vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités vocales cloud dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5342a-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="5342a-105">Les paramètres réseau servent à déterminer l’emplacement d’un client Teams et incluent des régions réseau, des sites réseau, des sous-réseaux et des adresses IP fiables.</span><span class="sxs-lookup"><span data-stu-id="5342a-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="5342a-106">En fonction de la fonctionnalité voix cloud et des fonctionnalités que vous déployez, vous configurez tout ou partie de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="5342a-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="5342a-107">Pour en savoir plus sur ces termes, consultez [les paramètres réseau pour les fonctionnalités vocales cloud.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5342a-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="5342a-108">Vous configurez les paramètres réseau sur **la** page Topologie de réseau du Centre d’administration Microsoft Teams ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5342a-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5342a-109">Configurer les paramètres réseau dans le Centre Microsoft Teams’administration</span><span class="sxs-lookup"><span data-stu-id="5342a-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="5342a-110">Vous définissez les régions réseau, les sites réseau et les sous-réseaux sous l’onglet **Sites réseau** de la page **Topologie de** réseau.</span><span class="sxs-lookup"><span data-stu-id="5342a-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="5342a-111">Dans cette zone, vous pouvez créer ou modifier un site réseau, associer un site à une région réseau, associer un sous-réseau au site, activer le routage en fonction de l’emplacement et affecter des stratégies d’urgence au site.</span><span class="sxs-lookup"><span data-stu-id="5342a-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="5342a-112">Vous pouvez également ajouter des régions réseau qui peuvent être utilisées globalement pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="5342a-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="5342a-113">Ajouter et configurer un site réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-113">Add and configure a network site</span></span>

1. <span data-ttu-id="5342a-114">Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur   >   **l’onglet Sites réseau.**</span><span class="sxs-lookup"><span data-stu-id="5342a-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="5342a-115">Cliquez **sur** Ajouter, puis entrez un nom et une description pour le site.</span><span class="sxs-lookup"><span data-stu-id="5342a-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Capture d’écran de la page Ajouter un site réseau](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="5342a-117">Pour associer le site à une région réseau, cliquez sur  Ajouter une région **réseau,** sélectionnez une région existante ou cliquez sur Ajouter pour ajouter une région, puis cliquez sur **Lien.**</span><span class="sxs-lookup"><span data-stu-id="5342a-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="5342a-118">Pour activer Location-Based routage pour le site, activez le **routage basé sur l’emplacement.**</span><span class="sxs-lookup"><span data-stu-id="5342a-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="5342a-119">Pour affecter des stratégies de services d’urgence au site, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="5342a-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="5342a-120">Si votre organisation utilise des plans d’appel ou Système téléphonique routage direct, sous Stratégie d’appels d’urgence, sélectionnez la stratégie de votre choix.</span><span class="sxs-lookup"><span data-stu-id="5342a-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="5342a-121">Si votre organisation a déployé Système téléphonique routage direct, dans le cadre de la stratégie de **routage** des appels d’urgence, sélectionnez la stratégie de votre choix.</span><span class="sxs-lookup"><span data-stu-id="5342a-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="5342a-122">Pour associer un sous-réseau au site, sous **Sous-réseaux,** cliquez **sur Ajouter des sous-réseaux.**</span><span class="sxs-lookup"><span data-stu-id="5342a-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="5342a-123">Spécifiez la version IP, l’adresse IP, la plage réseau, ajoutez une description, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="5342a-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="5342a-124">Chaque sous-réseau doit être associé à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="5342a-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="5342a-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5342a-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="5342a-126">Modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-126">Modify a network site</span></span>

1. <span data-ttu-id="5342a-127">Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur   >   **l’onglet Sites réseau.**</span><span class="sxs-lookup"><span data-stu-id="5342a-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="5342a-128">Sélectionnez le site en cliquant à gauche du nom du site, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="5342a-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5342a-129">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="5342a-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="5342a-130">Gérer les adresses IP de confiance externes</span><span class="sxs-lookup"><span data-stu-id="5342a-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="5342a-131">Vous gérez les adresses IP fiables externes sous l’onglet Adresses **IP** de confiance sur la page **topologie** de réseau du Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="5342a-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="5342a-132">Vous pouvez ajouter un nombre illimité d’adresses IP de confiance externes.</span><span class="sxs-lookup"><span data-stu-id="5342a-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="5342a-133">Ajouter une adresse IP fiable</span><span class="sxs-lookup"><span data-stu-id="5342a-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="5342a-134">Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur l’onglet Adresses  >   **IPS** de confiance.</span><span class="sxs-lookup"><span data-stu-id="5342a-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="5342a-135">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5342a-135">Click **New**.</span></span>
3. <span data-ttu-id="5342a-136">Dans le **volet Ajouter des adresses IP** fiables, spécifiez la version IP, l’adresse IP et la plage réseau, ajoutez une description, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="5342a-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Capture d’écran du volet Ajouter des adresses IP fiables](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="5342a-138">Modifier une adresse IP fiable</span><span class="sxs-lookup"><span data-stu-id="5342a-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="5342a-139">Dans le navigation gauche du centre Microsoft Teams d’administration, allez à la topologie du réseau Emplacements, puis cliquez sur l’onglet Adresses  >   **IPS** de confiance.</span><span class="sxs-lookup"><span data-stu-id="5342a-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="5342a-140">Sélectionnez l’adresse IP en cliquant à gauche de cette adresse, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="5342a-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="5342a-141">Dans le **volet Modifier les adresses IP** fiables, a apporter les modifications de votre souhaitez, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="5342a-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="5342a-142">Configurer les paramètres réseau à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="5342a-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="5342a-143">Pour suivre les étapes de cette section, vous devez être familiarisé avec les cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5342a-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5342a-144">Pour en savoir plus, voir [Teams vue d’ensemble de PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5342a-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="5342a-145">Définir les régions réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-145">Define network regions</span></span>

 <span data-ttu-id="5342a-146">Utilisez [l’cmdlet New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) pour définir les régions réseau.</span><span class="sxs-lookup"><span data-stu-id="5342a-146">Use the [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="5342a-147">Notez que le paramètre RegionID est un nom logique qui représente la géographie de la région et ne présente aucune dépendance ou restriction et que le paramètre ID de site central est &lt; &gt; facultatif.</span><span class="sxs-lookup"><span data-stu-id="5342a-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5342a-148">Dans cet exemple, nous créons une région réseau nommée Inde.</span><span class="sxs-lookup"><span data-stu-id="5342a-148">In this example, we create a network region named India.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="5342a-149">Voir également [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworkregion)</span><span class="sxs-lookup"><span data-stu-id="5342a-149">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="5342a-150">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-150">Define network sites</span></span>

<span data-ttu-id="5342a-151">Utilisez [l’cmdlet New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) pour définir des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="5342a-151">Use the [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="5342a-152">Chaque site réseau doit être associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="5342a-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="5342a-153">Dans cet exemple, nous créons deux sites réseau, Tous les deux dans la région Inde.</span><span class="sxs-lookup"><span data-stu-id="5342a-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="5342a-154">Le tableau suivant indique les sites réseau définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5342a-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="5342a-155">Site 1</span><span class="sxs-lookup"><span data-stu-id="5342a-155">Site 1</span></span> |<span data-ttu-id="5342a-156">Site 2</span><span class="sxs-lookup"><span data-stu-id="5342a-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5342a-157">Site ID</span><span class="sxs-lookup"><span data-stu-id="5342a-157">Site ID</span></span>    |    <span data-ttu-id="5342a-158">Site 1 (Syz)</span><span class="sxs-lookup"><span data-stu-id="5342a-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="5342a-159">Site 2 (Syz)</span><span class="sxs-lookup"><span data-stu-id="5342a-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="5342a-160">ID de région</span><span class="sxs-lookup"><span data-stu-id="5342a-160">Region ID</span></span>  |     <span data-ttu-id="5342a-161">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="5342a-161">Region 1 (India)</span></span>    |   <span data-ttu-id="5342a-162">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="5342a-162">Region 1 (India)</span></span>      |

<span data-ttu-id="5342a-163">Voir également [Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworksite)</span><span class="sxs-lookup"><span data-stu-id="5342a-163">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="5342a-164">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-164">Define network subnets</span></span>

<span data-ttu-id="5342a-165">Utilisez la [cmdlet New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) pour définir des sous-réseaux et les associer à des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="5342a-165">Use the [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="5342a-166">Chaque sous-réseau ne peut être associé qu’à un seul site.</span><span class="sxs-lookup"><span data-stu-id="5342a-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="5342a-167">Dans cet exemple, nous créons une association entre le sous-réseau 192.168.0.0 et le site du réseau Premièrement, ainsi qu’entre le sous-réseau 2001:4898:e8:25:844e:926f:85ad:dd8e et le site réseau Centrer network.</span><span class="sxs-lookup"><span data-stu-id="5342a-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="5342a-168">Le tableau suivant montre les sous-réseaux définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5342a-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="5342a-169">Site 1</span><span class="sxs-lookup"><span data-stu-id="5342a-169">Site 1</span></span> |<span data-ttu-id="5342a-170">Site 2</span><span class="sxs-lookup"><span data-stu-id="5342a-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5342a-171">ID de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="5342a-171">Subnet ID</span></span>   |    <span data-ttu-id="5342a-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="5342a-172">192.168.0.0</span></span>     |  <span data-ttu-id="5342a-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="5342a-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="5342a-174">Masque</span><span class="sxs-lookup"><span data-stu-id="5342a-174">Mask</span></span>  |     <span data-ttu-id="5342a-175">24</span><span class="sxs-lookup"><span data-stu-id="5342a-175">24</span></span>    |   <span data-ttu-id="5342a-176">120</span><span class="sxs-lookup"><span data-stu-id="5342a-176">120</span></span>      |
|<span data-ttu-id="5342a-177">Site ID</span><span class="sxs-lookup"><span data-stu-id="5342a-177">Site ID</span></span>  | <span data-ttu-id="5342a-178">Site (Syz)</span><span class="sxs-lookup"><span data-stu-id="5342a-178">Site (Delhi)</span></span> | <span data-ttu-id="5342a-179">Site 2 (Syz)</span><span class="sxs-lookup"><span data-stu-id="5342a-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="5342a-180">Pour plusieurs sous-réseaux, vous pouvez importer un fichier CSV à l’aide d’un script tel que le suivant.</span><span class="sxs-lookup"><span data-stu-id="5342a-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="5342a-181">Dans cet exemple, le fichier CSV ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="5342a-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


<span data-ttu-id="5342a-182">Voir également [Set-CsTenantNetworkSubnet.](/powershell/module/skype/set-cstenantnetworksubnet)</span><span class="sxs-lookup"><span data-stu-id="5342a-182">See also [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).</span></span>


### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="5342a-183">Définir des sous-réseaux externes (adresses IP de confiance externes)</span><span class="sxs-lookup"><span data-stu-id="5342a-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="5342a-184">Utilisez la [cmdlet New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) pour définir des sous-réseaux externes et les affecter au client.</span><span class="sxs-lookup"><span data-stu-id="5342a-184">Use the [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="5342a-185">Vous pouvez définir un nombre illimité de sous-réseaux externes pour un client.</span><span class="sxs-lookup"><span data-stu-id="5342a-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="5342a-186">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5342a-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="5342a-187">Voir également [Set-CsTenantTrustedIPAddress.](/powershell/module/skype/set-cstenanttrustedipaddress)</span><span class="sxs-lookup"><span data-stu-id="5342a-187">See also [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5342a-188">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="5342a-188">Related topics</span></span>

- [<span data-ttu-id="5342a-189">Paramètres réseau pour les fonctionnalités vocales cloud dans Teams</span><span class="sxs-lookup"><span data-stu-id="5342a-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
