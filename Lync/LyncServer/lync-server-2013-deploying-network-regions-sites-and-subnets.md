---
title: 'Lync Server 2013 : déploiement de zones, de sites et de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="62369-102">Déploiement de zones, sites et sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62369-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62369-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="62369-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="62369-104">Après le déploiement d’Enterprise Voice, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="62369-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="62369-105">Régions réseau</span><span class="sxs-lookup"><span data-stu-id="62369-105">Network regions</span></span>

  - <span data-ttu-id="62369-106">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="62369-106">Network sites</span></span>

  - <span data-ttu-id="62369-107">Sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="62369-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="62369-108">Définir des régions réseau</span><span class="sxs-lookup"><span data-stu-id="62369-108">Define Network Regions</span></span>

<span data-ttu-id="62369-109">Pour définir les zones du réseau, utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkRegion ou le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62369-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="62369-110">Pour plus d’informations, reportez-vous à [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="62369-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="62369-111">Pour cet exemple, la commande Windows PowerShell suivante illustre la région du réseau, région 1 (Inde), définie dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="62369-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="62369-112">Définir des sites réseau</span><span class="sxs-lookup"><span data-stu-id="62369-112">Define Network Sites</span></span>

<span data-ttu-id="62369-113">Utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkSite ou le panneau de configuration de Lync Server pour définir les sites réseau.</span><span class="sxs-lookup"><span data-stu-id="62369-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="62369-114">Pour plus d’informations, reportez-vous à [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="62369-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="62369-115">Pour cet exemple, le tableau suivant et la commande Windows PowerShell Lync Server illustrent les sites réseau définis dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="62369-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="62369-116">Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="62369-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="62369-117">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="62369-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="62369-118">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="62369-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62369-119">ID de site</span><span class="sxs-lookup"><span data-stu-id="62369-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="62369-120">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="62369-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="62369-121">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="62369-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62369-122">ID de région</span><span class="sxs-lookup"><span data-stu-id="62369-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="62369-123">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="62369-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="62369-124">Région 1 (Inde)</span><span class="sxs-lookup"><span data-stu-id="62369-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="62369-125">Définir des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="62369-125">Define Network Subnets</span></span>

<span data-ttu-id="62369-126">Utilisez la commande Windows PowerShell de Lync Server, le nouveau-CsNetworkSubnet ou le panneau de configuration de Lync Server pour définir des sous-réseaux réseau et les affecter à des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="62369-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="62369-127">Pour plus d’informations, reportez-vous à [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="62369-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="62369-128">Pour cet exemple, les commandes de tableau et Windows PowerShell suivantes montrent l’affectation de sous-réseaux réseau aux sites réseau, Delhi et Hyderabad définis dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="62369-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="62369-129">Seuls les paramètres spécifiques au routage de géolocalisation sont inclus dans la table à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="62369-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="62369-130">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="62369-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="62369-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="62369-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62369-132">ID de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="62369-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="62369-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="62369-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="62369-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="62369-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62369-135">Réseau</span><span class="sxs-lookup"><span data-stu-id="62369-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="62369-136">24</span><span class="sxs-lookup"><span data-stu-id="62369-136">24</span></span></p></td>
<td><p><span data-ttu-id="62369-137">24</span><span class="sxs-lookup"><span data-stu-id="62369-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62369-138">ID de site</span><span class="sxs-lookup"><span data-stu-id="62369-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="62369-139">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="62369-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="62369-140">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="62369-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62369-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62369-141">See Also</span></span>


[<span data-ttu-id="62369-142">Configuration du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62369-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

