---
title: 'Lync Server 2013 : composant de serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d540d37dee0de37d3986c02ac2243a95fe4404
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="5e390-102">Composant de serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e390-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5e390-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5e390-104">Vous devez déployer Lync Server 2013, serveur de médiation si vous déployez la charge de travail voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="5e390-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="5e390-105">Cette section décrit les fonctionnalités et topologies de base, les dépendances et les directives de planification.</span><span class="sxs-lookup"><span data-stu-id="5e390-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="5e390-106">Le serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre infrastructure interne de Lync Server 2013, votre infrastructure voix entreprise et une passerelle PSTN ou une jonction SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="5e390-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="5e390-107">Sur le côté Lync Server 2013, le serveur de médiation écoute sur une seule adresse de transport Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="5e390-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="5e390-108">Du côté de la passerelle, le serveur de médiation est à l’écoute sur tous les ports d’écoute associés aux jonctions définies dans le document de topologie.</span><span class="sxs-lookup"><span data-stu-id="5e390-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="5e390-109">Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="5e390-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="5e390-110">Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="5e390-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="5e390-111">Si vous disposez également d’un autocommutateur public (PBX) dans votre environnement, le serveur de médiation gère les appels entre les utilisateurs voix entreprise et le PBX.</span><span class="sxs-lookup"><span data-stu-id="5e390-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="5e390-112">Si votre PBX est un PBX IP, vous pouvez créer une connexion SIP directe entre le PBX et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5e390-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="5e390-113">Si votre PBX est un PBX de multiplexage temporel, vous devez également déployer une passerelle PSTN entre le serveur de médiation et le PBX.</span><span class="sxs-lookup"><span data-stu-id="5e390-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="5e390-114">Par défaut, le serveur de médiation est colocalisé avec le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="5e390-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="5e390-115">Le serveur de médiation peut également être déployé dans un pool autonome pour des raisons de performances, ou si vous déployez la jonction SIP, auquel cas le pool autonome est fortement recommandé.</span><span class="sxs-lookup"><span data-stu-id="5e390-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="5e390-116">Si vous déployez des connexions SIP directes vers une passerelle PSTN qualifiée qui prend en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS, un pool de serveurs de médiation autonomes n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5e390-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="5e390-117">Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="5e390-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="5e390-118">Il est également recommandé de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé des systèmes IP-PBX ou que vous vous êtes connecté(e) au contrôleur SBC (Session Border Controller) d‘un fournisseur ITSP (Internet Telephony Server Provider), à condition de respecter les indications suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e390-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="5e390-119">Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.</span><span class="sxs-lookup"><span data-stu-id="5e390-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="5e390-120">Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage des communications vocales pour les appels auxquels la déviation du trafic multimédia ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="5e390-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="5e390-121">Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge.</span><span class="sxs-lookup"><span data-stu-id="5e390-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="5e390-122">Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="5e390-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="5e390-123">Les principales fonctions du serveur de médiation sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e390-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="5e390-124">Chiffrement et déchiffrement des SRTP sur le côté Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e390-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="5e390-125">Traduction SIP sur TCP (pour les passerelles non compatibles TLS) vers SIP sur mutual TLS</span><span class="sxs-lookup"><span data-stu-id="5e390-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="5e390-126">Conversion de flux multimédia entre Lync Server et l’homologue de passerelle du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="5e390-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="5e390-127">Connexion des clients situés hors du réseau aux composants ICE internes, ce qui permet aux données multimédias de traverser les traducteurs d’adresses réseau (NAT) et les pare-feu</span><span class="sxs-lookup"><span data-stu-id="5e390-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="5e390-128">Agir en tant qu’intermédiaire pour les flux d’appels non pris en charge par une passerelle, tels que les appels de travailleurs distants sur un client voix entreprise</span><span class="sxs-lookup"><span data-stu-id="5e390-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="5e390-129">Dans les déploiements qui incluent la jonction SIP, collaboration avec le fournisseur de services de jonction SIP pour fournir la prise en charge PSTN, de sorte qu’il ne soit plus nécessaire de disposer d’une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="5e390-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="5e390-130">La figure suivante illustre les protocoles de signalisation et de média utilisés par le serveur de médiation lors de la communication avec une passerelle PSTN de base et l’infrastructure voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="5e390-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="5e390-131">**Protocoles de signalisation et de données multimédias utilisés par le serveur de médiation**</span><span class="sxs-lookup"><span data-stu-id="5e390-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="5e390-132">![Diagramme des protocoles de serveur de médiation](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramme des protocoles de serveur de médiation")</span><span class="sxs-lookup"><span data-stu-id="5e390-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e390-133">Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle PSTN et le serveur de médiation, nous vous recommandons de prendre des mesures pour garantir la sécurité et la confidentialité du réseau.</span><span class="sxs-lookup"><span data-stu-id="5e390-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5e390-134">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5e390-134">In This Section</span></span>

  - [<span data-ttu-id="5e390-135">Jonction M :N dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="5e390-136">Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="5e390-137">Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="5e390-138">Contournement de média et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="5e390-139">Composants et topologies pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="5e390-140">Instructions de déploiement pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e390-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

