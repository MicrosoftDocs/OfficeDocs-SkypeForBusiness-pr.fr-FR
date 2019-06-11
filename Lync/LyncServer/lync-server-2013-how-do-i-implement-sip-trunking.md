---
title: 'Lync Server 2013 : Implémentation d’une jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2e35c-102">Implémentation d’une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e35c-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e35c-103">_**Dernière modification de la rubrique:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="2e35c-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="2e35c-104">Pour implémenter le trunking SIP, vous devez Router la connexion à l’aide d’un serveur de médiation, qui fait office de proxy pour les sessions de communication entre les clients Lync Server 2013 et le fournisseur de service, et transcode le média, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2e35c-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="2e35c-105">Chaque serveur de médiation possède une interface réseau interne et une interface réseau externe.</span><span class="sxs-lookup"><span data-stu-id="2e35c-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="2e35c-106">L’interface interne se connecte aux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="2e35c-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="2e35c-107">L’interface externe est généralement appelée interface de la passerelle, car elle a traditionnellement été utilisée pour connecter le serveur de médiation à une passerelle de réseau téléphonique commuté (PSTN) ou un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="2e35c-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="2e35c-108">Pour implémenter une ligne SIP, vous connectez l’interface externe du serveur de médiation au composant de bord externe du ITSP.</span><span class="sxs-lookup"><span data-stu-id="2e35c-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e35c-109">Ce dernier peut être un contrôleur de session en périphérie (SBC), un routeur ou une passerelle.</span><span class="sxs-lookup"><span data-stu-id="2e35c-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="2e35c-110">Pour plus d’informations sur les serveurs de médiation, voir [composant serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="2e35c-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="2e35c-111">Comparatif entre jonction SIP centralisée et jonction SIP distribuée</span><span class="sxs-lookup"><span data-stu-id="2e35c-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="2e35c-112">*Centralisation* Le trunking SIP achemine tout le trafic VoIP (voix sur IP), y compris le trafic du site de succursale, par le biais de votre site central.</span><span class="sxs-lookup"><span data-stu-id="2e35c-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="2e35c-113">Le modèle de déploiement centralisé est simple, rentable et est généralement l’approche recommandée pour l’implémentation de Trunks SIP avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e35c-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="2e35c-114">*Distribué* Le trunking SIP est un modèle de déploiement dans lequel vous implémentez un Trunk SIP local au sein d’un ou plusieurs sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="2e35c-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="2e35c-115">Le trafic VoIP est alors acheminé à partir du site de succursale directement vers un fournisseur de services, sans passer par le site central.</span><span class="sxs-lookup"><span data-stu-id="2e35c-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="2e35c-116">La jonction SIP distribuée n’est requise que dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="2e35c-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="2e35c-117">Le site de succursale nécessite une connectivité téléphonique plus Survivable (par exemple, si le réseau étendu monte en panne).</span><span class="sxs-lookup"><span data-stu-id="2e35c-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="2e35c-118">Cette obligation doit être analysée pour chaque site de succursale; Il est possible que certaines de vos succursales nécessitent une redondance et un basculement, alors que d’autres ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="2e35c-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="2e35c-119">La résilience est requise entre deux sites centraux.</span><span class="sxs-lookup"><span data-stu-id="2e35c-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="2e35c-120">Vous devez vous assurer qu’un Trunk SIP s’arrête sur chaque site central.</span><span class="sxs-lookup"><span data-stu-id="2e35c-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="2e35c-121">Par exemple, si vous avez des sites centraux de Dublin et Tukwila et que vous utilisez uniquement le Trunk SIP d’un site, si le Trunk s’arrête, les utilisateurs du site ne peuvent pas passer d’appels RTC.</span><span class="sxs-lookup"><span data-stu-id="2e35c-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="2e35c-122">Le site de succursale et le site central sont dans des pays/régions différents.</span><span class="sxs-lookup"><span data-stu-id="2e35c-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="2e35c-123">Pour des raisons de compatibilité et légales, vous devez disposer d’au moins une jonction SIP par pays/région.</span><span class="sxs-lookup"><span data-stu-id="2e35c-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="2e35c-124">Par exemple, dans l’Union Européenne, les communications ne peuvent pas sortir d’un pays ou d’une région sans terminaison locale à un point centralisé.</span><span class="sxs-lookup"><span data-stu-id="2e35c-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="2e35c-125">En fonction de l’emplacement géographique des sites et de la quantité de trafic que vous prévoyez au sein de votre entreprise, il est possible que vous ne souhaitiez pas acheminer tous les utilisateurs par le biais du réseau SIP central ou vous pouvez choisir de router des utilisateurs via une ligne SIP sur leur site de succursale.</span><span class="sxs-lookup"><span data-stu-id="2e35c-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="2e35c-126">Pour vous aider à établir vos besoins, répondez aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e35c-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="2e35c-127">Quel est le niveau de chaque site (c’est-à-dire le nombre d’utilisateurs activés pour Enterprise Voice)?</span><span class="sxs-lookup"><span data-stu-id="2e35c-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="2e35c-128">Quels numéros de Sélection directe à l’arrivée (SDA) reçoivent le plus grand nombre d’appels sur chaque site ?</span><span class="sxs-lookup"><span data-stu-id="2e35c-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="2e35c-129">La décision d’opter pour une jonction SIP centralisée ou distribuée doit être basée sur une analyse des coûts-avantages.</span><span class="sxs-lookup"><span data-stu-id="2e35c-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="2e35c-130">Dans certains cas, il peut être plus avantageux d’opter pour un modèle de déploiement distribué, même s’il n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2e35c-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="2e35c-131">Dans un déploiement entièrement centralisé, le trafic de tous les sites de succursales est routé par le biais de liens WAN.</span><span class="sxs-lookup"><span data-stu-id="2e35c-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="2e35c-132">Au lieu de payer pour la bande passante requise pour la liaison de réseau étendu, il est peut-être préférable d’utiliser une jonction SIP distribuée.</span><span class="sxs-lookup"><span data-stu-id="2e35c-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="2e35c-133">Par exemple, vous pouvez choisir de déployer un serveur Standard Edition sur un site de succursale avec la Fédération sur le site central, ou vous pouvez déployer une application de succursale Survivable ou un serveur de succursales survivant avec une petite passerelle.</span><span class="sxs-lookup"><span data-stu-id="2e35c-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e35c-134">Pour plus d’informations sur le trunking SIP distribué, voir <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP site dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2e35c-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="2e35c-135">Types de connexion de jonction SIP pris en charge</span><span class="sxs-lookup"><span data-stu-id="2e35c-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="2e35c-136">Lync Server prend en charge les types de connexion suivants pour le trunking SIP:</span><span class="sxs-lookup"><span data-stu-id="2e35c-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="2e35c-p109">Le réseau privé MPLS (Multiprotocol Label Switching) dirige et transporte les données d’un nœud du réseau vers le suivant. La bande passante d’un réseau MPLS est partagée avec d’autres abonnés et un libellé est attribué à chaque paquet de données pour distinguer les données d’un abonné de celles d’un autre. Ce type de connexion ne requiert pas de réseau privé virtuel (VPN). Un des inconvénients possibles est que le trafic IP excessif peut interférer avec le trafic VoIP à moins qu’une priorité soit affectée au trafic VoIP.</span><span class="sxs-lookup"><span data-stu-id="2e35c-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="2e35c-p110">Une connexion privée sans autre trafic, par exemple, une connexion à fibre optique louée ou une ligne T1, est généralement le type de connexion le plus fiable et le plus sûr. En effet, elle offre la capacité la plus élevée en matière de transport des appels. Cependant, elle est généralement plus chère. Un VPN n’est pas nécessaire. Les connexions privées sont adaptées aux organisations à grands volumes d’appels ou soumises à des exigences strictes en matière de sécurité et de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="2e35c-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="2e35c-145">Internet est le type de connexion le moins cher, mais aussi le moins fiable.</span><span class="sxs-lookup"><span data-stu-id="2e35c-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="2e35c-146">Connexion Internet est le seul type de connexion de trunking SIP de Lync Server qui nécessite un réseau privé virtuel (VPN).</span><span class="sxs-lookup"><span data-stu-id="2e35c-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="2e35c-147">Sélection d’un type de connexion</span><span class="sxs-lookup"><span data-stu-id="2e35c-147">Selecting a Connection Type</span></span>

<span data-ttu-id="2e35c-148">Le type de connexion de jonction SIP le plus approprié à votre entreprise dépend de vos besoins et de votre budget.</span><span class="sxs-lookup"><span data-stu-id="2e35c-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="2e35c-p112">Pour les grandes et moyennes entreprises, un réseau MPLS offre en général la meilleure valeur. Il est capable de fournir la bande passante nécessaire à un tarif moindre qu’un réseau privé spécialisé.</span><span class="sxs-lookup"><span data-stu-id="2e35c-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="2e35c-151">Pour les grandes entreprises, une connexion privée à fibre optique, T1, T3 ou supérieure (E1, E3 ou supérieure dans l’Union Européenne) peut être adaptée.</span><span class="sxs-lookup"><span data-stu-id="2e35c-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="2e35c-152">Dans le cas d’une petite entreprise ou d’un site de succursale avec un volume d’appel faible, le trunking SIP via Internet est le meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="2e35c-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="2e35c-153">Ce type de connexion n’est pas recommandé pour les sites de taille moyenne ou de grande taille.</span><span class="sxs-lookup"><span data-stu-id="2e35c-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="2e35c-154">Bande passante requise</span><span class="sxs-lookup"><span data-stu-id="2e35c-154">Bandwidth Requirements</span></span>

<span data-ttu-id="2e35c-p114">La capacité d’appels (c’est-à-dire le nombre d’appels simultanés devant être pris en charge) détermine la bande passante requise pour votre implémentation. Vous devez prendre en compte la disponibilité de la bande passante pour pouvoir tirer parti de la capacité maximale facturée. Calculez vos besoins en bande passante de jonction SIP maximale à l’aide de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="2e35c-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="2e35c-158">Bande passante de jonction SIP maximale = Nbre max. d’appels simultanés (64 Kbits/s + taille d’en-tête)</span><span class="sxs-lookup"><span data-stu-id="2e35c-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e35c-159">La taille d’en-tête maximale est de 20 octets.</span><span class="sxs-lookup"><span data-stu-id="2e35c-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="2e35c-160">Prise en charge de codec</span><span class="sxs-lookup"><span data-stu-id="2e35c-160">Codec Support</span></span>

<span data-ttu-id="2e35c-161">Lync Server 2013 ne prend en charge que les codecs suivants:</span><span class="sxs-lookup"><span data-stu-id="2e35c-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="2e35c-162">G.711 a-law (utilisé principalement en dehors de l’Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="2e35c-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="2e35c-163">G.711 µ-law (utilisé en Amérique du Nord)</span><span class="sxs-lookup"><span data-stu-id="2e35c-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="2e35c-164">Fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="2e35c-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="2e35c-165">La manière dont vous mettez en œuvre le côté fournisseur de services d’une connexion de jonction SIP varie d’un fournisseur de services de téléphonie Internet à l’autre.</span><span class="sxs-lookup"><span data-stu-id="2e35c-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="2e35c-166">Pour plus d’informations sur le déploiement, contactez votre fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="2e35c-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="2e35c-167">Pour obtenir la liste des fournisseurs de services de trunking SIP certifiés, voir [site Web du programme d’interopérabilité Microsoft Unified Communications](http://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="2e35c-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="2e35c-168">Pour plus d’informations sur les fournisseurs de jonctions SIP approuvés par Microsoft, contactez votre représentant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e35c-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2e35c-p116">Vous devez utiliser un fournisseur de services approuvé par Microsoft pour garantir que votre fournisseur de services de téléphonie Internet prend en charge toutes les fonctionnalités qui transitent par la jonction SIP (par exemple, la configuration et la gestion des sessions et la prise en charge des services VoIP étendus). Le support technique Microsoft ne s’étend pas aux configurations qui utilisent des fournisseurs non approuvés. Si vous utilisez actuellement un fournisseur de services Internet non approuvé pour la jonction SIP, vous pouvez envisager de continuer à utiliser ce fournisseur en tant que FAI et utiliser un fournisseur approuvé par Microsoft pour la jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="2e35c-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

