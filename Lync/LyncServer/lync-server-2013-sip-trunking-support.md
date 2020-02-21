---
title: Prise en charge de la jonction SIP de Lync Server 2013
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
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="98dd9-102">Prise en charge de la jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98dd9-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98dd9-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="98dd9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="98dd9-104">Si vous envisagez d’utiliser la voix entreprise avec la jonction SIP, vous devez déployer un serveur de médiation et vous assurer que d’autres infrastructures et composants répondent aux exigences de prise en charge appropriées à votre modèle de déploiement.</span><span class="sxs-lookup"><span data-stu-id="98dd9-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="98dd9-105">Pour plus d’informations sur la façon de déterminer s’il faut implémenter la jonction SIP, voir [Overview of SIP Trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="98dd9-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="98dd9-106">Vous pouvez utiliser le programme d’interopérabilité Open Communications Microsoft pour l’infrastructure de téléphonie d’entreprise pour rechercher les passerelles RTC (réseau téléphonique commuté), les PBX IP et les services de jonction SIP qualifiés, y compris la téléphonie IP qualifiée fournisseurs de services.</span><span class="sxs-lookup"><span data-stu-id="98dd9-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="98dd9-107">Pour plus d’informations, consultez le site Web Microsoft Unified Communications Open [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)Interoperability Program à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="98dd9-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="98dd9-108">Prise en charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="98dd9-108">Mediation Server Support</span></span>

<span data-ttu-id="98dd9-109">Pour implémenter la jonction SIP, vous devez acheminer la connexion via un serveur de médiation qui agit comme un proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="98dd9-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="98dd9-110">Le serveur de médiation décode le trafic multimédia provenant des clients et serveurs puis le réencode avant de l’envoyer au fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="98dd9-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="98dd9-111">Le ré-encodage est nécessaire, car les jonctions SIP ne prennent pas en charge certains codecs utilisés, comme la négociation RTA (Real Time audio) ou la négociation de protocole d’établissement de connectivité interactive pour le traversée du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="98dd9-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="98dd9-112">Chaque serveur de médiation peut comporter deux cartes réseau, fournissant une interface réseau interne et externe.</span><span class="sxs-lookup"><span data-stu-id="98dd9-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="98dd9-113">L’interface externe est communément appelée interface de passerelle car elle a généralement été utilisée pour se connecter à une passerelle RTC ou à un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="98dd9-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="98dd9-114">Pour mettre en œuvre un acheminement SIP, vous connectez l’interface externe à un contrôleur de session en périphérie (SBC) au niveau d’un fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="98dd9-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="98dd9-115">Comparatif entre jonction SIP centralisée et jonction SIP distribuée</span><span class="sxs-lookup"><span data-stu-id="98dd9-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="98dd9-116">*Centralisé* La jonction SIP achemine tout le trafic VoIP (Voice over Internet Protocol), y compris le trafic de site de succursale, via votre centre de données.</span><span class="sxs-lookup"><span data-stu-id="98dd9-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="98dd9-117">Le modèle de déploiement centralisé est simple, rentable et constitue généralement l’approche par défaut pour l’implémentation de jonctions SIP avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98dd9-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="98dd9-p106">Selon les modèles d’utilisation de votre entreprise, vous pouvez choisir de ne pas acheminer tous les utilisateurs via un acheminement SIP centralisé. Pour vous aider à établir vos besoins, répondez aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="98dd9-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="98dd9-p107">Quelle est la taille de chaque site ? Combien y a-t-il d’utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="98dd9-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="98dd9-122">Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?</span><span class="sxs-lookup"><span data-stu-id="98dd9-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="98dd9-p108">La jonction SIP *distribuée* est un modèle de déploiement selon lequel vous mettez en œuvre une jonction SIP locale sur un ou plusieurs sites de succursale. Le trafic VoIP est ensuite acheminé à partir du site de succursale directement à son fournisseur de services, sans passer par votre centre de données.</span><span class="sxs-lookup"><span data-stu-id="98dd9-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="98dd9-125">La jonction SIP distribuée n’est requise que dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="98dd9-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="98dd9-126">Le site de succursale nécessite une connectivité téléphonique de secours (par exemple, en cas de panne de la liaison WAN).</span><span class="sxs-lookup"><span data-stu-id="98dd9-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="98dd9-127">Si la succursale n’a pas besoin d’une fonctionnalité de redondance et de basculement, le fournisseur de services facturera davantage et la configuration sera plus longue.</span><span class="sxs-lookup"><span data-stu-id="98dd9-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="98dd9-128">Cette éventualité devrait être étudiée pour chaque site de succursale.</span><span class="sxs-lookup"><span data-stu-id="98dd9-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="98dd9-129">Certaines de vos succursales peuvent nécessiter une redondance et un basculement, tandis que d’autres ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="98dd9-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="98dd9-p110">Le site de succursale et le centre de données sont situés dans différents pays/régions. Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région.</span><span class="sxs-lookup"><span data-stu-id="98dd9-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="98dd9-132">La décision de déployer une jonction SIP centralisée ou distribuée nécessite une analyse coûts-avantages.</span><span class="sxs-lookup"><span data-stu-id="98dd9-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="98dd9-133">Dans certains cas, il peut être avantageux d’opter pour le mode de déploiement distribué, même si cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="98dd9-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="98dd9-134">Dans un déploiement complètement centralisé, tout le trafic du site de succursale est acheminé via des liaisons WAN.</span><span class="sxs-lookup"><span data-stu-id="98dd9-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="98dd9-135">Au lieu de payer pour la bande passante requise pour la liaison WAN, il est peut-être préférable d’utiliser une jonction SIP distribuée.</span><span class="sxs-lookup"><span data-stu-id="98dd9-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98dd9-136">Pour plus d’informations sur la façon dont vous pouvez utiliser la jonction SIP distribuée, voir <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP Trunking in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="98dd9-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="98dd9-137">Types de connexion de jonction SIP pris en charge</span><span class="sxs-lookup"><span data-stu-id="98dd9-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="98dd9-138">Lync Server 2013 prend en charge les types de connexion suivants pour la jonction SIP :</span><span class="sxs-lookup"><span data-stu-id="98dd9-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="98dd9-p112">Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.</span><span class="sxs-lookup"><span data-stu-id="98dd9-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="98dd9-p113">Une connexion privée sans autre trafic constitue généralement le type de connexion le plus fiable et le plus sûr (par exemple, une connexion en bail à fibre optique ou une ligne T1). Ce type de connexion fournit la capacité de gestion d’appels la plus élevée, mais elle est généralement la plus coûteuse. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="98dd9-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="98dd9-147">L’Internet public représente le type de connexion le plus économique, mais également le moins fiable et celui qui offre la capacité de gestion des appels la plus faible.</span><span class="sxs-lookup"><span data-stu-id="98dd9-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="98dd9-148">Votre fournisseur de services de téléphonie Internet (téléphonie Internet) peut vous aider à sécuriser ce type de connexion de jonction SIP s’il prend en charge le protocole TLS (Transport Layer Security) et SRTP (Secure Real-Time Transport Protocol) pour chiffrer le trafic de signalisation et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="98dd9-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="98dd9-149">Si vous n’êtes pas en mesure de configurer une connexion par jonction SIP via Internet dans le but d’utiliser TLS et SRTP, nous vous recommandons vivement d’utiliser un tunnel VPN pour bénéficier d’une connexion plus sûre.</span><span class="sxs-lookup"><span data-stu-id="98dd9-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="98dd9-150">Contactez votre fournisseur de services de téléphonie Internet pour déterminer s’il offre une prise en charge de TLS avec SRTP.</span><span class="sxs-lookup"><span data-stu-id="98dd9-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="98dd9-151">Sélection d’un type de connexion</span><span class="sxs-lookup"><span data-stu-id="98dd9-151">Selecting a Connection Type</span></span>

<span data-ttu-id="98dd9-152">Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.</span><span class="sxs-lookup"><span data-stu-id="98dd9-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="98dd9-153">Pour une entreprise de taille moyenne ou grande, un réseau MPLS fournit généralement le plus de valeur.</span><span class="sxs-lookup"><span data-stu-id="98dd9-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="98dd9-154">Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.</span><span class="sxs-lookup"><span data-stu-id="98dd9-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="98dd9-155">Les grandes entreprises peuvent nécessiter une connexion à fibre optique privée ou une connexion T1.</span><span class="sxs-lookup"><span data-stu-id="98dd9-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="98dd9-156">Pour une petite entreprise ou un site de succursale avec un faible volume d’appels, la jonction SIP via Internet peut être le meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="98dd9-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="98dd9-157">Toutefois, ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou grande.</span><span class="sxs-lookup"><span data-stu-id="98dd9-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="98dd9-158">Prise en charge de codec</span><span class="sxs-lookup"><span data-stu-id="98dd9-158">Codec Support</span></span>

<span data-ttu-id="98dd9-159">Le proxy du fournisseur de services doit prendre en charge les codecs suivants :</span><span class="sxs-lookup"><span data-stu-id="98dd9-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="98dd9-160">G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="98dd9-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="98dd9-161">G.711 µ-law (utilisé en Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="98dd9-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

