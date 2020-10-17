---
title: 'Lync Server 2013 : activation du routage des Location-Based'
description: 'Lync Server 2013 : activation du routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557620"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0f110-103">Activation du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f110-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f110-104">_**Dernière modification de la rubrique :** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="0f110-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="0f110-105">Une fois que Enterprise Voice est déployé et que des régions réseau, des sites et des sous-réseaux sont définis, vous pouvez activer le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0f110-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="0f110-106">Le routage des Location-Based doit être activé pour les éléments voix entreprise suivants :</span><span class="sxs-lookup"><span data-stu-id="0f110-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="0f110-107">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="0f110-107">Network sites</span></span>

  - <span data-ttu-id="0f110-108">Configurations de jonctions</span><span class="sxs-lookup"><span data-stu-id="0f110-108">Trunk configurations</span></span>

  - <span data-ttu-id="0f110-109">Stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="0f110-109">Voice policies</span></span>

  - <span data-ttu-id="0f110-110">Configuration du routage</span><span class="sxs-lookup"><span data-stu-id="0f110-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="0f110-111">Activer le routage des Location-Based vers les sites réseau</span><span class="sxs-lookup"><span data-stu-id="0f110-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="0f110-112">Une fois que vous avez déployé voix entreprise, et configuré les sites réseau, vous êtes prêt à configurer le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0f110-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="0f110-113">Tout d’abord, vous créez une stratégie de routage des communications vocales pour associer le site réseau aux utilisations RTC appropriées.</span><span class="sxs-lookup"><span data-stu-id="0f110-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="0f110-114">Lorsque vous affectez des utilisations PSTN à une stratégie de routage des communications vocales, veillez à n’utiliser que les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site ou à une passerelle PSTN située dans une région où Location-Based des restrictions de routage ne sont pas nécessaires. Utilisez la commande Lync Server Windows PowerShell, le panneau de configuration New-CsVoiceRoutingPolicy ou Lync Server pour créer des stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="0f110-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="0f110-115">Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="0f110-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="0f110-116">Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent deux stratégies de routage des communications vocales et les utilisations RTC associées définies dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0f110-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="0f110-117">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="0f110-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0f110-118">Stratégie de routage des communications vocales 1</span><span class="sxs-lookup"><span data-stu-id="0f110-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="0f110-119">Stratégie de routage des communications vocales 2</span><span class="sxs-lookup"><span data-stu-id="0f110-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f110-120">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="0f110-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0f110-121">Stratégie de routage des communications vocales de Delhi</span><span class="sxs-lookup"><span data-stu-id="0f110-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0f110-122">Stratégie de routage des communications vocales Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0f110-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-123">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="0f110-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0f110-124">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="0f110-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0f110-125">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="0f110-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="0f110-126">Ensuite, configurez le routage des Location-Based pour les sites réseau applicables et associez-leur des stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="0f110-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="0f110-127">Utilisez la commande Lync Server Windows PowerShell, New-applet csnetworksite, pour activer le routage des Location-Based et associer des stratégies de routage des communications vocales à vos sites réseau qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="0f110-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="0f110-128">Dans cet exemple, le tableau suivant illustre le Location-Based routage de deux sites réseau différents, Delhi et Hyderabad, défini dans ce scénario à l’aide de Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f110-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="0f110-129">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="0f110-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0f110-130">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0f110-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="0f110-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0f110-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f110-132">Nom du site</span><span class="sxs-lookup"><span data-stu-id="0f110-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="0f110-133">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0f110-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0f110-134">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0f110-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-135">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="0f110-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="0f110-136">True</span><span class="sxs-lookup"><span data-stu-id="0f110-136">True</span></span></p></td>
<td><p><span data-ttu-id="0f110-137">True</span><span class="sxs-lookup"><span data-stu-id="0f110-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f110-138">Stratégie de routage vocale</span><span class="sxs-lookup"><span data-stu-id="0f110-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0f110-139">Stratégie de routage des communications vocales de Delhi</span><span class="sxs-lookup"><span data-stu-id="0f110-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0f110-140">Stratégie de routage des communications vocales Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0f110-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-141">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="0f110-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="0f110-142">Sous-réseau 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0f110-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0f110-143">Sous-réseau 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0f110-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="0f110-144">Activer le routage des Location-Based vers les jonctions</span><span class="sxs-lookup"><span data-stu-id="0f110-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="0f110-145">Avant de pouvoir activer une configuration de jonction pour le routage de Location-Based, vous devez créer une configuration de jonction pour chaque jonction ou chaque site réseau.</span><span class="sxs-lookup"><span data-stu-id="0f110-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="0f110-146">Utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration, pour créer une configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="0f110-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="0f110-147">Si plusieurs jonctions sont associées à un système donné (par exemple, passerelle ou PBX), chaque configuration de tronçon doit être modifiée afin d’activer les restrictions de routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0f110-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="0f110-148">Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0f110-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0f110-149">Pour cet exemple, les commandes Windows PowerShell suivantes illustrent la création d’une configuration de jonction pour chaque jonction dans le déploiement défini dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0f110-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="0f110-150">Une fois qu’une configuration de jonction est configurée par jonction, vous pouvez utiliser la commande Lync Server Windows PowerShell, Set-applet cstrunkconfiguration, pour activer le routage des Location-Based vers vos jonctions qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="0f110-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="0f110-151">Activez le routage des Location-Based vers des jonctions qui acheminent les appels vers des passerelles PSTN qui acheminent les appels vers le RTC, et associez le site réseau sur lequel se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="0f110-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="0f110-152">Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0f110-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0f110-153">Dans cet exemple, Location-Based routage est activé pour chaque jonction associée aux passerelles RTC dans Delhi et Hyderabad :</span><span class="sxs-lookup"><span data-stu-id="0f110-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="0f110-154">N’activez pas le routage des Location-Based pour les jonctions qui n’acheminent pas les appels vers le réseau téléphonique commuté (RTC). Toutefois, vous devez toujours associer la jonction au site réseau où se trouve le système comme Location-Based les restrictions de routage doivent être appliquées pour que les appels PSTN atteignent les points de terminaison connectés via cette jonction.</span><span class="sxs-lookup"><span data-stu-id="0f110-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="0f110-155">Pour cet exemple, Location-Based routage n’est pas activé pour chaque jonction associée aux systèmes PBX dans Delhi et Hyderabad :</span><span class="sxs-lookup"><span data-stu-id="0f110-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="0f110-156">Les points de terminaison connectés aux systèmes qui n’acheminent pas les appels vers le réseau téléphonique commuté (PBX) auront des restrictions similaires à celles des points de terminaison Lync des utilisateurs activés pour le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0f110-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="0f110-157">Cela signifie que ces utilisateurs pourront passer et recevoir des appels vers et à partir de l’utilisateur de Lync indépendamment de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f110-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="0f110-158">Ils peuvent également passer des appels reçus vers et à partir d’autres systèmes qui n’acheminent pas les appels vers le réseau PSTN (c’est-à-dire un point de terminaison connecté à un autre PBX), quel que soit le site réseau auquel le système est associé.</span><span class="sxs-lookup"><span data-stu-id="0f110-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="0f110-159">Tous les appels entrants, sortants, de transfert d’appel et de transfert d’appel impliquant des points de terminaison PSTN seront soumis à des Location-Based de routage.</span><span class="sxs-lookup"><span data-stu-id="0f110-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="0f110-160">Ces appels doivent utiliser uniquement des passerelles PSTN définies comme locales à ces systèmes.</span><span class="sxs-lookup"><span data-stu-id="0f110-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="0f110-161">Le tableau suivant illustre la configuration de jonction de quatre tronçons dans deux sites réseau différents : deux connectés à des passerelles PSTN et deux connectés à des systèmes PBX.</span><span class="sxs-lookup"><span data-stu-id="0f110-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f110-162">Nom</span><span class="sxs-lookup"><span data-stu-id="0f110-162">Name</span></span></th>
<th><span data-ttu-id="0f110-163">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="0f110-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="0f110-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="0f110-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f110-165">PstnGateway : jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="0f110-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="0f110-166">Vrai</span><span class="sxs-lookup"><span data-stu-id="0f110-166">True</span></span></p></td>
<td><p><span data-ttu-id="0f110-167">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0f110-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-168">PstnGateway : jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="0f110-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="0f110-169">Vrai</span><span class="sxs-lookup"><span data-stu-id="0f110-169">True</span></span></p></td>
<td><p><span data-ttu-id="0f110-170">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0f110-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f110-171">PstnGateway : jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="0f110-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="0f110-172">False</span><span class="sxs-lookup"><span data-stu-id="0f110-172">False</span></span></p></td>
<td><p><span data-ttu-id="0f110-173">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="0f110-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-174">PstnGateway : jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="0f110-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="0f110-175">False</span><span class="sxs-lookup"><span data-stu-id="0f110-175">False</span></span></p></td>
<td><p><span data-ttu-id="0f110-176">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0f110-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="0f110-177">Activer le routage des Location-Based vers les stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="0f110-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="0f110-178">Pour appliquer le routage de Location-Based à des utilisateurs spécifiques, configurez la stratégie de voix de ces utilisateurs afin d’empêcher le contournement de numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="0f110-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0f110-179">Utilisez la commande Lync Server Windows PowerShell, New-CsVoicePolicy, pour créer une nouvelle stratégie de voix ou Set-CsVoicePolicy, si vous utilisez une stratégie existante, pour activer le routage des Location-Baseds en empêchant le contournement des appels RTC.</span><span class="sxs-lookup"><span data-stu-id="0f110-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="0f110-180">Pour plus d’informations, consultez la rubrique [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="0f110-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="0f110-181">Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’activation de la prévention du contournement payant PSTN vers les stratégies de voix Delhi et Hyderabad définies dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0f110-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="0f110-182">Seuls les paramètres spécifiques à Location-Based routage sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="0f110-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0f110-183">Stratégie de voix 1</span><span class="sxs-lookup"><span data-stu-id="0f110-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="0f110-184">Stratégie de voix 2</span><span class="sxs-lookup"><span data-stu-id="0f110-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f110-185">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="0f110-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0f110-186">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="0f110-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="0f110-187">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0f110-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f110-188">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="0f110-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0f110-189">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="0f110-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0f110-190">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="0f110-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f110-191">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="0f110-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="0f110-192">True</span><span class="sxs-lookup"><span data-stu-id="0f110-192">True</span></span></p></td>
<td><p><span data-ttu-id="0f110-193">True</span><span class="sxs-lookup"><span data-stu-id="0f110-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="0f110-194">Activer le routage des Location-Based dans la configuration de routage</span><span class="sxs-lookup"><span data-stu-id="0f110-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="0f110-195">Enfin, activez globalement le routage des Location-Based vers votre configuration de routage.</span><span class="sxs-lookup"><span data-stu-id="0f110-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="0f110-196">Utilisez la commande Lync Server Windows PowerShell, New-CsRoutingConfiguration, pour activer le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0f110-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="0f110-197">Pour plus d’informations, consultez la rubrique [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0f110-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f110-198">même si le routage de Location-Based doit être activé par le biais d’une configuration globale, l’ensemble de règles à appliquer n’est appliqué que pour les sites, les utilisateurs et les jonctions pour lesquels il a été configuré comme indiqué dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="0f110-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f110-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f110-199">See Also</span></span>


[<span data-ttu-id="0f110-200">Configuration du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f110-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

