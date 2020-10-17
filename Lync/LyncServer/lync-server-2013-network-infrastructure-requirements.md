---
title: Configuration requise pour l’infrastructure réseau de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 338e2387b08898694bd621e220d7f889a8d25e0a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505541"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="8fdd2-102">Configuration requise pour l’infrastructure réseau pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd2-102">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fdd2-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8fdd2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8fdd2-104">La carte réseau de chaque serveur de la topologie Lync Server 2013 doit prendre en charge au moins 1 Gigabit par seconde (Gbits/s).</span><span class="sxs-lookup"><span data-stu-id="8fdd2-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="8fdd2-105">En général, vous devez connecter tous les rôles serveur au sein de la topologie Lync Server à l’aide d’une faible latence et d’un réseau local à bande passante élevée (LAN).</span><span class="sxs-lookup"><span data-stu-id="8fdd2-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="8fdd2-106">La taille du réseau local dépend de la taille de la topologie :</span><span class="sxs-lookup"><span data-stu-id="8fdd2-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="8fdd2-107">Dans les topologies Standard Edition, les serveurs doivent se trouver dans un réseau prenant en charge 1 Gbits/s ou équivalent.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="8fdd2-108">Dans les topologies de pool frontal, la plupart des serveurs doivent se trouver dans un réseau prenant en charge plus de 1 Gbits/s, en particulier lors de la prise en charge de la conférence audio/vidéo (A/V) et du partage d’applications.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="8fdd2-109">Pour l’intégration d’un réseau téléphonique commuté (PSTN), vous pouvez intégrer à l’aide de lignes T1/E1 ou de jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="8fdd2-110">Configuration requise pour le réseau audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="8fdd2-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="8fdd2-111">La configuration réseau requise pour l’audio/vidéo (A/V) dans un déploiement Lync Server inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8fdd2-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="8fdd2-112">Si vous déployez un serveur Edge unique ou un pool de serveurs Edge à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu externe en tant que NAT.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="8fdd2-113">Vous ne pouvez pas configurer le pare-feu interne en tant que NAT.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="8fdd2-114">Pour plus d’informations sur ces conditions requises, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fdd2-115">Si vous disposez d’un pool de serveurs Edge et que vous utilisez un programme d’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiques sur chaque serveur Edge et vous ne pouvez pas utiliser le protocole NAT pour les serveurs ou le pool sur votre périphérique NAT (par exemple, le pare-feu ou un autre périphérique d’infrastructure qui doit NAT le trafic entrant ou sortant).</span><span class="sxs-lookup"><span data-stu-id="8fdd2-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="8fdd2-116">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</A> dans la documentation sur la planification de l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="8fdd2-117">Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="8fdd2-118">Si vous utilisez la sécurité du protocole Internet (IPsec), nous vous recommandons de désactiver IPsec sur les plages de ports utilisées pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="8fdd2-119">Pour plus d’informations, reportez-vous à la rubrique [IPSec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="8fdd2-120">Pour garantir une qualité des médias optimale, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8fdd2-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="8fdd2-121">Configurez vos liens réseau pour qu’ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s’ils sont activés, pendant les périodes d’utilisation maximale.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="8fdd2-122">Une session audio ou vidéo bidirectionnelle est composée de deux flux.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="8fdd2-123">Pour faire face à des pics inattendus dans le trafic au-dessus de ce niveau et une utilisation accrue au fil du temps, les points de terminaison Lync Server Media peuvent s’adapter à des conditions de réseau variables et prendre en charge des charges de trois fois le débit (voir paragraphe précédent) pour l’audio et la vidéo tout en conservant une qualité acceptable.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="8fdd2-124">Toutefois, ne partez pas du principe que cette adaptabilité prend en charge un réseau sous-configuré.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="8fdd2-125">Dans un réseau sous-configuré, la capacité des points de terminaison multimédia Lync Server à traiter dynamiquement des conditions réseau variables (par exemple, une perte de paquets élevée temporaire) est réduite.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="8fdd2-126">Pour les liaisons réseau où la mise en service est extrêmement coûteuse et difficile, vous devrez peut-être envisager la mise en service d’un volume de trafic inférieur.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="8fdd2-127">Dans ce scénario, l’élasticité des points de terminaison de Lync Server Media absorbe la différence entre le volume de trafic et le niveau de trafic maximal, au prix d’une réduction de la qualité de la voix.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="8fdd2-128">De plus, il y a une diminution de la hauteur suffisante autrement pour absorber les pics soudains dans le trafic.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="8fdd2-129">Pour les liens qui ne peuvent pas être correctement configurés à court terme (par exemple, un site avec des liaisons de réseau étendu très médiocres), envisagez de désactiver la vidéo pour certains utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="8fdd2-130">Approvisionnez votre réseau pour garantir un retard de bout en bout de 150 millisecondes (MS) en dessous de la charge maximale.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="8fdd2-131">La latence est l’une des altérations de réseau que les composants multimédias de Lync Server ne peuvent pas réduire, et il est important de trouver et d’éliminer les points faibles.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="8fdd2-132">Pour les serveurs exécutant un logiciel antivirus, incluez tous les serveurs exécutant Lync Server dans la liste des exceptions afin de fournir des performances et une qualité audio optimales.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="8fdd2-133">Configuration requise pour le réseau de conférence</span><span class="sxs-lookup"><span data-stu-id="8fdd2-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="8fdd2-134">La bande passante utilisée pour télécharger le contenu de conférence à partir du serveur IIS (Internet Information Services) dépend de la taille du contenu téléchargé.</span><span class="sxs-lookup"><span data-stu-id="8fdd2-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

