---
title: 'Lync Server 2013 : Composants et topologies utilisés pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="3a68b-102">Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a68b-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a68b-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3a68b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3a68b-104">Cette rubrique décrit les composants sur lesquels le serveur de médiation dépend et les topologies dans lesquelles il est possible de déployer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3a68b-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="3a68b-105">Dépendances</span><span class="sxs-lookup"><span data-stu-id="3a68b-105">Dependencies</span></span>

<span data-ttu-id="3a68b-106">Le serveur de médiation a les dépendances suivantes:</span><span class="sxs-lookup"><span data-stu-id="3a68b-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="3a68b-107">**Autorités.**</span><span class="sxs-lookup"><span data-stu-id="3a68b-107">**Registrar.**</span></span> <span data-ttu-id="3a68b-108">Requis.</span><span class="sxs-lookup"><span data-stu-id="3a68b-108">Required.</span></span> <span data-ttu-id="3a68b-109">Le Bureau d’enregistrement est le tronçon suivant de signalisation dans les interactions du serveur de médiation avec le réseau Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a68b-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="3a68b-110">Notez que le serveur de médiation peut être localisé sur un serveur frontal conjointement au bureau d’enregistrement, en plus d’être installé dans un pool autonome composé uniquement de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="3a68b-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="3a68b-111">Le Bureau d’enregistrement est colocalisé par un serveur de médiation et une passerelle RTC sur une unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="3a68b-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="3a68b-112">**Serveur de surveillance.**</span><span class="sxs-lookup"><span data-stu-id="3a68b-112">**Monitoring Server.**</span></span> <span data-ttu-id="3a68b-113">Facultatif, mais fortement recommandé.</span><span class="sxs-lookup"><span data-stu-id="3a68b-113">Optional but highly recommended.</span></span> <span data-ttu-id="3a68b-114">Le serveur de surveillance permet au serveur de médiation d’enregistrer les mesures de qualité associées à ses sessions multimédias.</span><span class="sxs-lookup"><span data-stu-id="3a68b-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="3a68b-115">**Serveur Edge.**</span><span class="sxs-lookup"><span data-stu-id="3a68b-115">**Edge Server.**</span></span> <span data-ttu-id="3a68b-116">Requis pour la prise en charge des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="3a68b-116">Required for external user support.</span></span> <span data-ttu-id="3a68b-117">Le serveur Edge permet au serveur de médiation d’interagir avec des utilisateurs situés derrière un NAT ou un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="3a68b-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="3a68b-118">Topologies</span><span class="sxs-lookup"><span data-stu-id="3a68b-118">Topologies</span></span>

<span data-ttu-id="3a68b-119">Le serveur Lync Server 2013, médiation Server est par défaut colocalisé avec une instance du Bureau d’enregistrement sur un serveur Standard Edition Server, un pool frontal ou une unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="3a68b-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="3a68b-120">Tous les serveurs de médiation dans un pool frontal doivent être configurés de la même manière.</span><span class="sxs-lookup"><span data-stu-id="3a68b-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="3a68b-121">Lorsque la performance est un problème, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié.</span><span class="sxs-lookup"><span data-stu-id="3a68b-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="3a68b-122">Par contre, si vous déployez le trunking SIP, nous vous recommandons de déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="3a68b-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="3a68b-123">Si vous déployez des connexions SIP directes vers une passerelle RTC qualifiée qui prend en charge le contournement du contenu multimédia et l’équilibrage de charge DNS, vous n’avez pas besoin d’un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="3a68b-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="3a68b-124">Il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonomes, car les passerelles qualifiées sont en mesure d’équilibrer la charge DNS vers un pool de serveurs de médiation et ils peuvent recevoir le trafic de n’importe quel serveur de médiation dans un pool.</span><span class="sxs-lookup"><span data-stu-id="3a68b-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="3a68b-125">Nous vous recommandons également de collocate le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou de vous connecter à un contrôleur de bordure de session du fournisseur de téléphonie Internet (SBC), à condition que l’une des conditions suivantes soit remplie:</span><span class="sxs-lookup"><span data-stu-id="3a68b-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="3a68b-126">Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.</span><span class="sxs-lookup"><span data-stu-id="3a68b-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="3a68b-127">Le PBX IP ne prend pas en charge la dérivation multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage de la voix pour les appels pour lesquels aucune dérivation de média ne s’applique.</span><span class="sxs-lookup"><span data-stu-id="3a68b-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="3a68b-128">Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si le pool frontal sur lequel vous souhaitez collocate le serveur de médiation peut gérer le chargement.</span><span class="sxs-lookup"><span data-stu-id="3a68b-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="3a68b-129">Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="3a68b-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="3a68b-130">Pour plus d’informations sur la topologie à déployer, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="3a68b-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="3a68b-131">La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison de réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="3a68b-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="3a68b-132">Le serveur de médiation est colocalisé avec le Bureau d’enregistrement sur un pool frontal sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="3a68b-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="3a68b-133">Les serveurs de médiation du site 1 contrôlent à la fois la passerelle RTC sur le site 1 et la passerelle sur le site 2.</span><span class="sxs-lookup"><span data-stu-id="3a68b-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="3a68b-134">Dans cette topologie, la déviation du trafic multimédia est activée globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle RTC (GW1 et GW2).</span><span class="sxs-lookup"><span data-stu-id="3a68b-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="3a68b-135">**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et une passerelle RTC pour Site 2**</span><span class="sxs-lookup"><span data-stu-id="3a68b-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="3a68b-136">![Topologie vocale avec passerelle du réseau WAN du serveur de médiation] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologie vocale avec passerelle du réseau WAN du serveur de médiation")</span><span class="sxs-lookup"><span data-stu-id="3a68b-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="3a68b-137">La figure suivante illustre une topologie simple dans laquelle le serveur de médiation est colocalisé avec le Bureau d’enregistrement de niveau frontal sur le site 1 et dispose d’une connexion SIP directe au PBX IP sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="3a68b-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="3a68b-138">Dans cette figure, le serveur de médiation contrôle également une passerelle RTC sur le site 2.</span><span class="sxs-lookup"><span data-stu-id="3a68b-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="3a68b-139">Supposez que les utilisateurs de Lync existent sur les sites 1 et 2.</span><span class="sxs-lookup"><span data-stu-id="3a68b-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="3a68b-140">Par ailleurs, supposez que le PBX IP possède un processeur de média associé qui doit être parcouru par tous les éléments multimédias provenant de points de terminaison Lync avant d’être envoyés aux points de terminaison multimédias contrôlés par le PBX IP.</span><span class="sxs-lookup"><span data-stu-id="3a68b-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="3a68b-141">Dans cette topologie, la déviation du trafic multimédia est activée globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et RTC.</span><span class="sxs-lookup"><span data-stu-id="3a68b-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="3a68b-142">**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et un PBX pour Site 2**</span><span class="sxs-lookup"><span data-stu-id="3a68b-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="3a68b-143">![PBX WAN du serveur de médiation vocale] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "PBX WAN du serveur de médiation vocale")</span><span class="sxs-lookup"><span data-stu-id="3a68b-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="3a68b-144">Pour plus d’informations sur la planification des topologies PBX, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) et [options de déploiement SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="3a68b-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="3a68b-145">La dernière figure de cette rubrique montre une topologie dans laquelle le serveur de médiation est connecté à l’SBC d’un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="3a68b-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="3a68b-146">Pour plus d’informations sur les topologies du Trunk SIP, consultez l’une des [lignes SIP dans Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="3a68b-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

