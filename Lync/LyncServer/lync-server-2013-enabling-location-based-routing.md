---
title: 'Lync Server 2013 : activation du routage géodépendant'
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
ms.openlocfilehash: 4f36d28ca41bb12aa98bab5add471e102ed282b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="83886-102">Activation du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83886-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83886-103">_**Dernière modification de la rubrique :** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="83886-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="83886-104">Une fois que Enterprise Voice est déployé et que des régions réseau, des sites et des sous-réseaux sont définis, vous pouvez activer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="83886-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="83886-105">Le routage géodépendant doit être activé pour les éléments voix entreprise suivants :</span><span class="sxs-lookup"><span data-stu-id="83886-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="83886-106">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="83886-106">Network sites</span></span>

  - <span data-ttu-id="83886-107">Configurations de jonctions</span><span class="sxs-lookup"><span data-stu-id="83886-107">Trunk configurations</span></span>

  - <span data-ttu-id="83886-108">Stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="83886-108">Voice policies</span></span>

  - <span data-ttu-id="83886-109">Configuration du routage</span><span class="sxs-lookup"><span data-stu-id="83886-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="83886-110">Activer le routage géodépendant vers les sites réseau</span><span class="sxs-lookup"><span data-stu-id="83886-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="83886-111">Une fois que vous avez déployé voix entreprise, et configuré les sites réseau, vous êtes prêt à configurer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="83886-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="83886-112">Tout d’abord, vous créez une stratégie de routage des communications vocales pour associer le site réseau aux utilisations RTC appropriées.</span><span class="sxs-lookup"><span data-stu-id="83886-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="83886-113">Lorsque vous affectez des utilisations PSTN à une stratégie de routage des communications vocales, veillez à utiliser uniquement les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale sur le site ou une passerelle PSTN située dans une région où les restrictions de routage géodépendant ne sont pas nécessaires. Utilisez la commande Lync Server Windows PowerShell, le panneau de configuration New-CsVoiceRoutingPolicy ou Lync Server pour créer des stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="83886-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="83886-114">Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="83886-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="83886-115">Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent deux stratégies de routage des communications vocales et les utilisations RTC associées définies dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="83886-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="83886-116">Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="83886-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="83886-117">Stratégie de routage des communications vocales 1</span><span class="sxs-lookup"><span data-stu-id="83886-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="83886-118">Stratégie de routage des communications vocales 2</span><span class="sxs-lookup"><span data-stu-id="83886-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83886-119">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="83886-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="83886-120">Stratégie de routage des communications vocales de Delhi</span><span class="sxs-lookup"><span data-stu-id="83886-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="83886-121">Stratégie de routage des communications vocales Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83886-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-122">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="83886-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="83886-123">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="83886-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="83886-124">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="83886-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="83886-125">Ensuite, configurez le routage géodépendant pour les sites réseau applicables et associez-leur des stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="83886-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="83886-126">Utilisez la commande Lync Server Windows PowerShell, New-applet csnetworksite, pour activer le routage géodépendant et associer des stratégies de routage des communications vocales à vos sites réseau qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="83886-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="83886-127">Dans cet exemple, le tableau suivant illustre le routage basé sur l’emplacement de deux sites réseau différents, Delhi et Hyderabad, définis dans ce scénario à l’aide de Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83886-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="83886-128">Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="83886-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="83886-129">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="83886-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="83886-130">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="83886-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83886-131">Nom du site</span><span class="sxs-lookup"><span data-stu-id="83886-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="83886-132">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="83886-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="83886-133">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="83886-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="83886-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="83886-135">True</span><span class="sxs-lookup"><span data-stu-id="83886-135">True</span></span></p></td>
<td><p><span data-ttu-id="83886-136">True</span><span class="sxs-lookup"><span data-stu-id="83886-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83886-137">Stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="83886-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="83886-138">Stratégie de routage des communications vocales de Delhi</span><span class="sxs-lookup"><span data-stu-id="83886-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="83886-139">Stratégie de routage des communications vocales Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83886-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-140">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="83886-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="83886-141">Sous-réseau 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="83886-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="83886-142">Sous-réseau 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="83886-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="83886-143">Activer le routage géodépendant vers les jonctions</span><span class="sxs-lookup"><span data-stu-id="83886-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="83886-144">Avant de pouvoir activer une configuration de tronçon pour le routage géodépendant, vous devez créer une configuration de jonction pour chaque jonction ou chaque site réseau.</span><span class="sxs-lookup"><span data-stu-id="83886-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="83886-145">Utilisez la commande Lync Server Windows PowerShell, New-applet cstrunkconfiguration, pour créer une configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="83886-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="83886-146">Si plusieurs jonctions sont associées à un système donné (par exemple, une passerelle ou un PBX), chaque configuration de tronçon doit être modifiée pour permettre les restrictions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="83886-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="83886-147">Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="83886-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="83886-148">Pour cet exemple, les commandes Windows PowerShell suivantes illustrent la création d’une configuration de jonction pour chaque jonction dans le déploiement défini dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="83886-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="83886-149">Une fois qu’une configuration de jonction est configurée par jonction, vous pouvez utiliser la commande Lync Server Windows PowerShell, Set-applet cstrunkconfiguration, pour activer le routage géodépendant vers vos jonctions qui doivent appliquer des restrictions de routage.</span><span class="sxs-lookup"><span data-stu-id="83886-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="83886-150">Activez le routage géodépendant vers des jonctions qui acheminent les appels vers des passerelles PSTN qui acheminent les appels vers le réseau téléphonique commuté (RTC) et associez le site réseau sur lequel se trouve la passerelle.</span><span class="sxs-lookup"><span data-stu-id="83886-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="83886-151">Pour plus d’informations, consultez la rubrique [New-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="83886-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="83886-152">Dans cet exemple, le routage géodépendant est activé pour chaque jonction qui est associée à des passerelles PSTN à Delhi et Hyderabad :</span><span class="sxs-lookup"><span data-stu-id="83886-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="83886-153">N’activez pas le routage géodépendant pour les jonctions qui n’acheminent pas les appels vers le réseau téléphonique commuté (RTC). Toutefois, vous devez toujours associer la jonction au site réseau où se trouve le système en tant que les restrictions de routage basées sur l’emplacement doivent être appliquées pour que les appels PSTN atteignent les points de terminaison connectés via cette jonction.</span><span class="sxs-lookup"><span data-stu-id="83886-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="83886-154">Pour cet exemple, le routage géodépendant n’est pas activé pour chaque jonction associée aux systèmes PBX à Delhi et Hyderabad :</span><span class="sxs-lookup"><span data-stu-id="83886-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="83886-155">Les points de terminaison connectés aux systèmes qui n’acheminent pas les appels vers le réseau téléphonique commuté (PBX) auront des restrictions similaires à celles des points de terminaison Lync des utilisateurs activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="83886-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="83886-156">Cela signifie que ces utilisateurs pourront passer et recevoir des appels vers et à partir de l’utilisateur de Lync indépendamment de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="83886-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="83886-157">Ils peuvent également passer des appels reçus vers et à partir d’autres systèmes qui n’acheminent pas les appels vers le réseau PSTN (c’est-à-dire un point de terminaison connecté à un autre PBX), quel que soit le site réseau auquel le système est associé.</span><span class="sxs-lookup"><span data-stu-id="83886-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="83886-158">Tous les appels entrants, sortants, de transfert d’appel et de transfert d’appel impliquant des points de terminaison PSTN seront soumis à des mises en œuvre de routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="83886-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="83886-159">Ces appels doivent utiliser uniquement des passerelles PSTN définies comme locales à ces systèmes.</span><span class="sxs-lookup"><span data-stu-id="83886-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="83886-160">Le tableau suivant illustre la configuration de jonction de quatre tronçons dans deux sites réseau différents : deux connectés à des passerelles PSTN et deux connectés à des systèmes PBX.</span><span class="sxs-lookup"><span data-stu-id="83886-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83886-161">Nom</span><span class="sxs-lookup"><span data-stu-id="83886-161">Name</span></span></th>
<th><span data-ttu-id="83886-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="83886-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="83886-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="83886-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83886-164">PstnGateway : jonction 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="83886-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="83886-165">Vrai</span><span class="sxs-lookup"><span data-stu-id="83886-165">True</span></span></p></td>
<td><p><span data-ttu-id="83886-166">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="83886-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-167">PstnGateway : jonction 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="83886-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="83886-168">Vrai</span><span class="sxs-lookup"><span data-stu-id="83886-168">True</span></span></p></td>
<td><p><span data-ttu-id="83886-169">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="83886-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83886-170">PstnGateway : jonction 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="83886-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="83886-171">False</span><span class="sxs-lookup"><span data-stu-id="83886-171">False</span></span></p></td>
<td><p><span data-ttu-id="83886-172">Site 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="83886-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-173">PstnGateway : jonction 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="83886-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="83886-174">False</span><span class="sxs-lookup"><span data-stu-id="83886-174">False</span></span></p></td>
<td><p><span data-ttu-id="83886-175">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="83886-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="83886-176">Activer le routage géodépendant vers les stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="83886-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="83886-177">Pour appliquer le routage géodépendant à des utilisateurs spécifiques, configurez la stratégie de voix de ces utilisateurs afin d’empêcher le contournement de numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="83886-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="83886-178">Utilisez la commande Lync Server Windows PowerShell, New-CsVoicePolicy, pour créer une nouvelle stratégie de voix ou Set-CsVoicePolicy, si vous utilisez une stratégie existante, pour activer le routage géodépendant en prévenant le contournement de l’adresse PSTN.</span><span class="sxs-lookup"><span data-stu-id="83886-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="83886-179">Pour plus d’informations, consultez la rubrique [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="83886-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="83886-180">Pour cet exemple, le tableau suivant et les commandes Windows PowerShell illustrent l’activation de la prévention du contournement payant PSTN vers les stratégies de voix Delhi et Hyderabad définies dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="83886-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="83886-181">Seuls les paramètres spécifiques au routage géodépendant sont inclus dans le tableau à des fins d’illustration.</span><span class="sxs-lookup"><span data-stu-id="83886-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="83886-182">Stratégie de voix 1</span><span class="sxs-lookup"><span data-stu-id="83886-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="83886-183">Stratégie de voix 2</span><span class="sxs-lookup"><span data-stu-id="83886-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83886-184">ID de stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="83886-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="83886-185">Stratégie de voix de Delhi</span><span class="sxs-lookup"><span data-stu-id="83886-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="83886-186">Stratégie de voix Hyderabad</span><span class="sxs-lookup"><span data-stu-id="83886-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83886-187">Utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="83886-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="83886-188">Utilisation de Delhi, utilisation de PBX del, utilisation de PBX HYD</span><span class="sxs-lookup"><span data-stu-id="83886-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="83886-189">Utilisation de Hyderabad, utilisation de la HYD PBX, utilisation de PBX del</span><span class="sxs-lookup"><span data-stu-id="83886-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83886-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="83886-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="83886-191">True</span><span class="sxs-lookup"><span data-stu-id="83886-191">True</span></span></p></td>
<td><p><span data-ttu-id="83886-192">True</span><span class="sxs-lookup"><span data-stu-id="83886-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="83886-193">Activer le routage géodépendant dans la configuration de routage</span><span class="sxs-lookup"><span data-stu-id="83886-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="83886-194">Enfin, vous pouvez activer le routage géodépendant dans votre configuration de routage.</span><span class="sxs-lookup"><span data-stu-id="83886-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="83886-195">Utilisez la commande Lync Server Windows PowerShell, New-CsRoutingConfiguration, pour activer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="83886-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="83886-196">Pour plus d’informations, consultez la rubrique [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="83886-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83886-197">alors que le routage géodépendant doit être activé via une configuration globale, l’ensemble de règles à appliquer n’est appliqué que pour les sites, les utilisateurs et les jonctions pour lesquels il a été configuré comme indiqué dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="83886-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83886-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83886-198">See Also</span></span>


[<span data-ttu-id="83886-199">Configuration du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83886-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

