---
title: Prise en charge des jonctions SIP dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="b9c72-102">Prise en charge des jonctions SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9c72-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9c72-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b9c72-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b9c72-104">Si vous envisagez d’utiliser Enterprise Voice avec le trunking SIP, vous devez déployer un serveur de médiation et vous assurer que d’autres infrastructures et composants répondent aux exigences de support appropriées à votre modèle de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b9c72-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="b9c72-105">Pour plus d’informations sur la façon de déterminer s’il convient d’implémenter le trunking SIP, voir [vue d’ensemble du trunking SIP dans Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b9c72-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="b9c72-106">Vous pouvez utiliser le programme Microsoft Unified Communications Open Interoperability pour l’infrastructure de téléphonie pour les entreprises pour rechercher des passerelles de réseau téléphonique commuté (RTC), des PBX IP et des services de trunking SIP qualifiés, y compris la téléphonie IP. prestataires de services.</span><span class="sxs-lookup"><span data-stu-id="b9c72-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="b9c72-107">Pour plus d’informations, reportez-vous au site Web Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Unified Communications Open Interoperability du programme à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b9c72-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="b9c72-108">Prise en charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="b9c72-108">Mediation Server Support</span></span>

<span data-ttu-id="b9c72-109">Pour implémenter le trunking SIP, vous devez Router la connexion à l’aide d’un serveur de médiation, qui fait office de proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de service.</span><span class="sxs-lookup"><span data-stu-id="b9c72-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="b9c72-110">Le serveur de médiation décode le trafic multimédia de clients et de serveurs, puis le réactive avant de l’envoyer au fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="b9c72-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="b9c72-111">Le encodage est nécessaire, car les Trunks SIP ne prennent pas en charge certains codecs utilisés (par exemple, le protocole RTA) ou la négociation du protocole d’établissement de connexion interactive pour le traversée par un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="b9c72-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="b9c72-112">Chaque serveur de médiation peut avoir deux cartes réseau qui fournissent une interface réseau interne et externe.</span><span class="sxs-lookup"><span data-stu-id="b9c72-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="b9c72-113">L’interface externe est généralement appelée interface de passerelle, car elle a traditionnellement servi à se connecter à une passerelle PSTN ou à un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="b9c72-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="b9c72-114">Pour implémenter une ligne SIP, vous connectez l’interface externe à un contrôleur de bordure de session (SBC) auprès d’un fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="b9c72-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="b9c72-115">Comparatif entre jonction SIP centralisée et jonction SIP distribuée</span><span class="sxs-lookup"><span data-stu-id="b9c72-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="b9c72-116">*Centralisation* Le trunking SIP route tout le trafic VoIP (voix sur IP), y compris le trafic du site de succursales, par le biais du centre de données.</span><span class="sxs-lookup"><span data-stu-id="b9c72-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="b9c72-117">Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche préférée pour l’implémentation de Trunks SIP avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9c72-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="b9c72-118">Selon les modèles d’utilisation au sein de votre entreprise, il est possible que vous ne souhaitiez pas acheminer tous les utilisateurs via le Trunk SIP centralisé.</span><span class="sxs-lookup"><span data-stu-id="b9c72-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="b9c72-119">Pour vous aider à établir vos besoins, répondez aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9c72-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="b9c72-120">Quelle est la taille de chaque site ?</span><span class="sxs-lookup"><span data-stu-id="b9c72-120">How big is each site?</span></span> <span data-ttu-id="b9c72-121">Combien d’utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="b9c72-121">How many users?</span></span>

  - <span data-ttu-id="b9c72-122">Quels sont les numéros de téléphone à composer vers l’intérieur sur chaque site pour obtenir la plupart des appels téléphoniques ?</span><span class="sxs-lookup"><span data-stu-id="b9c72-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="b9c72-123">*Distribué* Le trunking SIP est un modèle de déploiement dans lequel vous implémentez un Trunk SIP local au sein d’un ou plusieurs sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="b9c72-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="b9c72-124">Le trafic VoIP est alors routé à partir du site de succursale directement vers son prestataire de services, sans passer par le centre de données.</span><span class="sxs-lookup"><span data-stu-id="b9c72-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="b9c72-125">La jonction SIP distribuée n’est requise que dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="b9c72-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="b9c72-126">Le site de succursale nécessite une connectivité téléphonique plus Survivable (par exemple, si le réseau étendu monte en panne).</span><span class="sxs-lookup"><span data-stu-id="b9c72-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="b9c72-127">Si la succursale a besoin d’une redondance et d’un basculement, le prestataire de services facturera davantage et la configuration sera plus longue.</span><span class="sxs-lookup"><span data-stu-id="b9c72-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="b9c72-128">Cela doit être analysé pour chaque site de succursale.</span><span class="sxs-lookup"><span data-stu-id="b9c72-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="b9c72-129">Certains de vos succursales sont susceptibles de nécessiter une redondance et un basculement, alors que d’autres ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="b9c72-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="b9c72-130">Le site de succursale et le centre de données se trouvent dans des pays/régions différents.</span><span class="sxs-lookup"><span data-stu-id="b9c72-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="b9c72-131">Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région.</span><span class="sxs-lookup"><span data-stu-id="b9c72-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="b9c72-132">Le choix entre le déploiement d’une trunkation SIP centralisée ou répartie nécessite une analyse coûts-avantages.</span><span class="sxs-lookup"><span data-stu-id="b9c72-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="b9c72-133">Dans certains cas, il peut être préférable de choisir le mode de déploiement distribué, même si ce n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b9c72-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="b9c72-134">Dans un déploiement entièrement centralisé, le trafic de tous les sites de succursales est routé par le biais de liens WAN.</span><span class="sxs-lookup"><span data-stu-id="b9c72-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="b9c72-135">Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée.</span><span class="sxs-lookup"><span data-stu-id="b9c72-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9c72-136">Pour plus d’informations sur les raisons et la façon dont vous pouvez utiliser le trunking SIP distribué, voir <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP site dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b9c72-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="b9c72-137">Types de connexion de jonction SIP pris en charge</span><span class="sxs-lookup"><span data-stu-id="b9c72-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="b9c72-138">Lync Server 2013 prend en charge les types de connexion suivants pour le trunking SIP :</span><span class="sxs-lookup"><span data-stu-id="b9c72-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="b9c72-139">Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant.</span><span class="sxs-lookup"><span data-stu-id="b9c72-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="b9c72-140">La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre.</span><span class="sxs-lookup"><span data-stu-id="b9c72-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="b9c72-141">Ce type de connexion n’exige pas VPN.</span><span class="sxs-lookup"><span data-stu-id="b9c72-141">This connection type does not require VPN.</span></span> <span data-ttu-id="b9c72-142">Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.</span><span class="sxs-lookup"><span data-stu-id="b9c72-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="b9c72-143">Une connexion privée sans autre trafic est généralement le type de connexion la plus fiable et la plus sécurisée (par exemple, une connexion fibre optique ou une ligne de type T1).</span><span class="sxs-lookup"><span data-stu-id="b9c72-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="b9c72-144">Ce type de connexion fournit la plus grande capacité de transport d’appel, mais c’est généralement le plus onéreux.</span><span class="sxs-lookup"><span data-stu-id="b9c72-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="b9c72-145">Aucun VPN n’est requis.</span><span class="sxs-lookup"><span data-stu-id="b9c72-145">VPN is not required.</span></span> <span data-ttu-id="b9c72-146">Les connexions privées conviennent aux organisations dont le volume d’appels est élevé ou dont les exigences de sécurité et de disponibilité sont rigoureuses.</span><span class="sxs-lookup"><span data-stu-id="b9c72-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="b9c72-147">L’Internet public est le type de connexion le moins cher, mais également le moins fiable, et celui doté de la plus petite capacité de transport d’appels.</span><span class="sxs-lookup"><span data-stu-id="b9c72-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="b9c72-148">Votre fournisseur de services de téléphonie Internet (ITSP) peut vous aider à sécuriser ce type de connexion SIP Trunk s’il prend en charge le protocole TLS (Transport Layer Security) et le protocole SRTP (Secure Real-Time Transport Protocol) pour chiffrer les signaux et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="b9c72-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="b9c72-149">Si vous ne parvenez pas à configurer une connexion SIP Trunk via Internet pour utiliser TLS et SRTP, nous vous recommandons vivement d’utiliser un tunnel VPN pour fournir une connexion plus sécurisée.</span><span class="sxs-lookup"><span data-stu-id="b9c72-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="b9c72-150">Contactez votre ITSP pour déterminer s’il prend en charge TLS avec SRTP.</span><span class="sxs-lookup"><span data-stu-id="b9c72-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="b9c72-151">Sélection d’un type de connexion</span><span class="sxs-lookup"><span data-stu-id="b9c72-151">Selecting a Connection Type</span></span>

<span data-ttu-id="b9c72-152">Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.</span><span class="sxs-lookup"><span data-stu-id="b9c72-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="b9c72-153">Dans le cas d’une entreprise du milieu ou d’une grande taille, un réseau MPLS fournit généralement le plus de valeur.</span><span class="sxs-lookup"><span data-stu-id="b9c72-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="b9c72-154">Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.</span><span class="sxs-lookup"><span data-stu-id="b9c72-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="b9c72-155">Les grandes entreprises pourront avoir besoin d’une connexion fibre optique privée ou T1.</span><span class="sxs-lookup"><span data-stu-id="b9c72-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="b9c72-156">Dans le cas d’une petite entreprise ou d’un site de succursale avec un volume d’appel faible, le trunking SIP via Internet est le meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="b9c72-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="b9c72-157">Toutefois, ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.</span><span class="sxs-lookup"><span data-stu-id="b9c72-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="b9c72-158">Prise en charge de codec</span><span class="sxs-lookup"><span data-stu-id="b9c72-158">Codec Support</span></span>

<span data-ttu-id="b9c72-159">Le proxy du fournisseur de services doit prendre en charge les codecs suivants :</span><span class="sxs-lookup"><span data-stu-id="b9c72-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="b9c72-160">G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="b9c72-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="b9c72-161">G.711 µ-law (utilisé en Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="b9c72-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

