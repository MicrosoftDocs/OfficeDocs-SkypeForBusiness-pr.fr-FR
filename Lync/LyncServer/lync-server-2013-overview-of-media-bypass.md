---
title: 'Lync Server 2013: vue d’ensemble de contournement de média'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="1ae52-102">Présentation de l’exclusion de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae52-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae52-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1ae52-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1ae52-104">La dérivation de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés.</span><span class="sxs-lookup"><span data-stu-id="1ae52-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="1ae52-105">En règle générale, un pool de serveurs de médiation est déployé sur un site central et contrôle les passerelles dans les sites de succursales.</span><span class="sxs-lookup"><span data-stu-id="1ae52-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="1ae52-106">L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites.</span><span class="sxs-lookup"><span data-stu-id="1ae52-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="1ae52-107">Les itinéraires d’appels sortants de Lync Server 2013 et les stratégies voix entreprise doivent être correctement configurés pour que les appels RTC de clients sur un site de succursale soient routés vers la passerelle appropriée.</span><span class="sxs-lookup"><span data-stu-id="1ae52-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="1ae52-p102">Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="1ae52-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="1ae52-113">Une fois que votre structure vocale d’entreprise est en place, il est facile de planifier une dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="1ae52-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="1ae52-114">Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.</span><span class="sxs-lookup"><span data-stu-id="1ae52-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="1ae52-115">Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1ae52-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="1ae52-116">Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="1ae52-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="1ae52-117">Quels sont les sites bien connectés dans chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="1ae52-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="1ae52-118">Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.</span><span class="sxs-lookup"><span data-stu-id="1ae52-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="1ae52-p103">Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.</span><span class="sxs-lookup"><span data-stu-id="1ae52-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="1ae52-121">Lorsqu’un utilisateur effectue un appel vers le RTC, le serveur de médiation compare l’ID de contournement du sous-réseau du client à l’ID de contournement du sous-réseau de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="1ae52-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="1ae52-122">Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ae52-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="1ae52-123">Si les ID de contournement ne correspondent pas, le média de l’appel doit être acheminé via le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1ae52-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="1ae52-124">Lorsqu’un utilisateur reçoit un appel depuis le réseau téléphonique commuté, le client de l’utilisateur compare son ID de contournement à celui de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ae52-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="1ae52-125">Si les deux ID de contournement correspondent, les flux multimédias sont directement de la passerelle au client, en ignorant le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1ae52-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="1ae52-126">Seuls Lync 2010 ou les clients et appareils supérieurs prennent en charge les interactions de contournement multimédia avec un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1ae52-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ae52-p106">En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction PSTN. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction PSTN donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction PSTN. En outre, lorsque la déviation du trafic multimédia est définie sur <STRONG>Utiliser les informations de site et de région</STRONG>, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.</span><span class="sxs-lookup"><span data-stu-id="1ae52-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ae52-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ae52-132">See Also</span></span>


[<span data-ttu-id="1ae52-133">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae52-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="1ae52-134">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae52-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="1ae52-135">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae52-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

