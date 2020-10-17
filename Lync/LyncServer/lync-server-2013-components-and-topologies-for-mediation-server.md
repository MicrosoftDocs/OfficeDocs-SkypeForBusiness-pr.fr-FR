---
title: 'Lync Server 2013 : composants et topologies pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac46c8aba06bdfedaafa7846142d5a584c703c3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502561"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="92270-102">Composants et topologies pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92270-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92270-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="92270-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="92270-104">Cette rubrique décrit les composants dont dépend le serveur de médiation et les topologies dans lesquelles le serveur de médiation peut être déployé.</span><span class="sxs-lookup"><span data-stu-id="92270-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="92270-105">Dépendances</span><span class="sxs-lookup"><span data-stu-id="92270-105">Dependencies</span></span>

<span data-ttu-id="92270-106">Le serveur de médiation présente les dépendances suivantes :</span><span class="sxs-lookup"><span data-stu-id="92270-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="92270-107">**Inscriptions.**</span><span class="sxs-lookup"><span data-stu-id="92270-107">**Registrar.**</span></span> <span data-ttu-id="92270-108">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="92270-108">Required.</span></span> <span data-ttu-id="92270-109">Le serveur d’inscriptions est le tronçon suivant pour la signalisation dans les interactions du serveur de médiation avec le réseau Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92270-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="92270-110">Notez que le serveur de médiation peut être colocalisé sur un serveur frontal avec le serveur d’inscriptions, en plus d’être installé dans un pool autonome constitué uniquement de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="92270-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="92270-111">Le serveur d’inscriptions est colocalisé avec un serveur de médiation et une passerelle PSTN sur un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="92270-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="92270-112">**Serveur de surveillance.**</span><span class="sxs-lookup"><span data-stu-id="92270-112">**Monitoring Server.**</span></span> <span data-ttu-id="92270-113">Facultatif mais fortement recommandé.</span><span class="sxs-lookup"><span data-stu-id="92270-113">Optional but highly recommended.</span></span> <span data-ttu-id="92270-114">Le serveur de surveillance permet au serveur de médiation d’enregistrer les mesures de qualité associées à ses sessions multimédia.</span><span class="sxs-lookup"><span data-stu-id="92270-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="92270-115">**Serveur Edge.**</span><span class="sxs-lookup"><span data-stu-id="92270-115">**Edge Server.**</span></span> <span data-ttu-id="92270-116">Obligatoire pour la prise en charge des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="92270-116">Required for external user support.</span></span> <span data-ttu-id="92270-117">Le serveur Edge permet au serveur de médiation d’interagir avec les utilisateurs situés derrière un NAT ou un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="92270-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="92270-118">Topologies</span><span class="sxs-lookup"><span data-stu-id="92270-118">Topologies</span></span>

<span data-ttu-id="92270-119">Le serveur de médiation Lync Server 2013 est colocalisé par défaut avec une instance du serveur d’inscriptions sur un serveur Standard Edition, un pool frontal ou un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="92270-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="92270-120">Tous les serveurs de médiation d’un pool frontal doivent être configurés de manière identique.</span><span class="sxs-lookup"><span data-stu-id="92270-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="92270-121">Lorsque les performances sont problématiques, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié.</span><span class="sxs-lookup"><span data-stu-id="92270-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="92270-122">Ou, si vous déployez une jonction SIP, nous vous recommandons de déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="92270-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="92270-123">Si vous déployez des connexions SIP directes vers une passerelle PSTN qualifiée qui prend en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS, un pool de serveurs de médiation autonomes n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="92270-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="92270-124">Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="92270-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="92270-125">Il est également recommandé de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé des systèmes IP-PBX ou que vous vous êtes connecté(e) au contrôleur SBC (Session Border Controller) d‘un fournisseur ITSP (Internet Telephony Server Provider), à condition de respecter les indications suivantes :</span><span class="sxs-lookup"><span data-stu-id="92270-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="92270-126">Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.</span><span class="sxs-lookup"><span data-stu-id="92270-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="92270-127">Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage des communications vocales pour les appels auxquels la déviation du trafic multimédia ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="92270-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="92270-128">Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge.</span><span class="sxs-lookup"><span data-stu-id="92270-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="92270-129">Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="92270-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="92270-130">Pour plus d’informations sur la topologie à déployer, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="92270-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="92270-131">La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison WAN.</span><span class="sxs-lookup"><span data-stu-id="92270-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="92270-132">Le serveur de médiation est colocalisé avec le serveur d’inscriptions sur un pool frontal sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="92270-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="92270-133">Les serveurs de médiation du site 1 contrôlent à la fois la passerelle PSTN sur le site 1 et la passerelle sur le site 2.</span><span class="sxs-lookup"><span data-stu-id="92270-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="92270-134">Dans cette topologie, le contournement de média est activé globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle PSTN (GW1 et GW2).</span><span class="sxs-lookup"><span data-stu-id="92270-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="92270-135">**Exemple de sites connectés par une liaison WAN avec un serveur de médiation sur Site 1 et une passerelle PSTN sur Site 2**</span><span class="sxs-lookup"><span data-stu-id="92270-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="92270-136">![Topologie vocale avec passerelle WAN de serveur de médiation](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologie vocale avec passerelle WAN de serveur de médiation")</span><span class="sxs-lookup"><span data-stu-id="92270-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="92270-137">La figure suivante montre une topologie simple dans laquelle le serveur de médiation est colocalisé avec le serveur d’inscriptions sur le pool frontal sur le site 1 et dispose d’une connexion SIP directe vers le PBX IP sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="92270-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="92270-138">Dans cette illustration, le serveur de médiation contrôle également une passerelle RTC sur le site 2.</span><span class="sxs-lookup"><span data-stu-id="92270-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="92270-139">Supposons que des utilisateurs Lync existent sur les sites 1 et 2.</span><span class="sxs-lookup"><span data-stu-id="92270-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="92270-140">Supposons également que le système IP-PBX possède un processeur multimédia associé qui doit être traversé par tous les médias provenant de points de terminaison Lync avant d’être envoyés aux points de terminaison multimédias contrôlés par le système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="92270-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="92270-141">Dans cette topologie, le contournement de média est activé globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et PSTN.</span><span class="sxs-lookup"><span data-stu-id="92270-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="92270-142">**Exemple de sites connectés par une liaison WAN avec un serveur de médiation sur Site 1 et un PBX sur Site 2**</span><span class="sxs-lookup"><span data-stu-id="92270-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="92270-143">![Serveur de médiation de topologie vocale-PBX WAN](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Serveur de médiation de topologie vocale-PBX WAN")</span><span class="sxs-lookup"><span data-stu-id="92270-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="92270-144">Pour plus d’informations sur la planification des topologies PBX, voir [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) et [direct SIP Deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="92270-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="92270-145">La dernière figure de cette rubrique montre une topologie à laquelle le serveur de médiation est connecté à l’SBC d’un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="92270-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="92270-146">Pour plus d’informations sur les topologies de jonction SIP, voir [SIP Trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="92270-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

