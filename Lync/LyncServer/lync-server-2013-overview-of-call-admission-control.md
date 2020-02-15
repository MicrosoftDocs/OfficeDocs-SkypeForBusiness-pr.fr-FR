---
title: 'Lync Server 2013 : vue d’ensemble du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a37e2-102">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a37e2-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37e2-103">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="a37e2-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="a37e2-104">Les communications en temps réel sont sensibles à la latence et à la perte de paquets susceptibles de survenir sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="a37e2-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="a37e2-105">Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies.</span><span class="sxs-lookup"><span data-stu-id="a37e2-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="a37e2-106">La conception CAC dans Lync Server 2013 propose quatre attributs principaux :</span><span class="sxs-lookup"><span data-stu-id="a37e2-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="a37e2-107">Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.</span><span class="sxs-lookup"><span data-stu-id="a37e2-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="a37e2-p102">Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du système d’extrémité et non pas de l’emplacement où est hébergé l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a37e2-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="a37e2-110">Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="a37e2-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="a37e2-111">Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau.</span><span class="sxs-lookup"><span data-stu-id="a37e2-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="a37e2-112">Pour obtenir des exemples, voir [composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="a37e2-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="a37e2-113">Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison WAN, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur PSTN.</span><span class="sxs-lookup"><span data-stu-id="a37e2-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="a37e2-p104">Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.</span><span class="sxs-lookup"><span data-stu-id="a37e2-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="a37e2-116">Les administrateurs définissent les stratégies de contrôle d’admission des stratégies, qui sont appliquées par le service de stratégie de bande passante installé avec chaque pool frontal.</span><span class="sxs-lookup"><span data-stu-id="a37e2-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="a37e2-117">Les paramètres CAC sont automatiquement propagés sur tous les serveurs frontaux Lync Server de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a37e2-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="a37e2-118">Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="a37e2-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="a37e2-119">Internet</span><span class="sxs-lookup"><span data-stu-id="a37e2-119">Internet</span></span>

2.  <span data-ttu-id="a37e2-120">RTC</span><span class="sxs-lookup"><span data-stu-id="a37e2-120">PSTN</span></span>

3.  <span data-ttu-id="a37e2-121">Messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="a37e2-121">Voice mail</span></span>

<span data-ttu-id="a37e2-p106">L’enregistrement des détails des appels capture les informations concernant les appels qui sont réacheminés vers PSTN ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.</span><span class="sxs-lookup"><span data-stu-id="a37e2-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a37e2-124">Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a37e2-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="a37e2-p107">Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison WAN. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="a37e2-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="a37e2-129">Considérations relatives au contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="a37e2-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="a37e2-130">L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central.</span><span class="sxs-lookup"><span data-stu-id="a37e2-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="a37e2-131">Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites.</span><span class="sxs-lookup"><span data-stu-id="a37e2-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="a37e2-132">Le service de stratégie de bande passante s’exécute sur les serveurs frontaux et, par conséquent, la haute disponibilité est intégrée au sein de ce pool.</span><span class="sxs-lookup"><span data-stu-id="a37e2-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="a37e2-133">Le service de stratégie de bande passante s’exécutant sur chaque serveur frontal se synchronise toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="a37e2-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="a37e2-134">Si le pool frontal échoue, les stratégies de contrôle d’admission des stratégies ne sont plus appliquées pour ce site jusqu’à ce que le pool frontal et, par conséquent, le service de stratégie de bande passante soit à nouveau opérationnel.</span><span class="sxs-lookup"><span data-stu-id="a37e2-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="a37e2-135">Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a37e2-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="a37e2-136">Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.</span><span class="sxs-lookup"><span data-stu-id="a37e2-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="a37e2-137">Le service de stratégie de bande passante offre une haute disponibilité au sein d’un pool frontal ; Toutefois, il ne fournit pas de redondance dans les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="a37e2-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="a37e2-138">Le service de stratégie de bande passante ne peut pas basculer d’un pool frontal à un autre.</span><span class="sxs-lookup"><span data-stu-id="a37e2-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="a37e2-139">Une fois le service sur le pool frontal restauré, le service de stratégie de bande passante reprend et peut appliquer de nouveau les contrôles de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a37e2-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="a37e2-140">Considérations relatives au réseau</span><span class="sxs-lookup"><span data-stu-id="a37e2-140">Network Considerations</span></span>

<span data-ttu-id="a37e2-141">Bien que la restriction de bande passante pour l’audio et la vidéo soit appliquée par le service de stratégie de bande passante dans Lync Server 2013, cette restriction n’est pas appliquée au niveau du routeur réseau (couches 2 et 3).</span><span class="sxs-lookup"><span data-stu-id="a37e2-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="a37e2-142">Lync Server 2010 le contrôle d’admission des appels ne peut pas empêcher une application de données de consommer toute la bande passante réseau sur une liaison de réseau étendu, y compris la bande passante réservée à la stratégie de contrôle d’admission des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="a37e2-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="a37e2-143">Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="a37e2-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="a37e2-144">Par conséquent, il est recommandé de coordonner les stratégies de bande passante de contrôle d’admission des coordonnées définies avec tous les paramètres de qualité de service que vous pouvez déployer.</span><span class="sxs-lookup"><span data-stu-id="a37e2-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="a37e2-145">Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)</span><span class="sxs-lookup"><span data-stu-id="a37e2-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="a37e2-p111">Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.</span><span class="sxs-lookup"><span data-stu-id="a37e2-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="a37e2-148">Contrôle d’admission des appels des utilisateurs extérieurs</span><span class="sxs-lookup"><span data-stu-id="a37e2-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="a37e2-149">Le contrôle d’admission des appels ne s’applique pas aux utilisateurs distants où le trafic réseau transite par Internet.</span><span class="sxs-lookup"><span data-stu-id="a37e2-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="a37e2-150">Étant donné que le trafic multimédia traverse Internet, qui n’est pas géré par Lync Server, le contrôle d’admission des médias ne peut pas être appliqué.</span><span class="sxs-lookup"><span data-stu-id="a37e2-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="a37e2-151">Le contrôle d’admission des appels effectuera néanmoins des vérifications sur la portion d’appel qui transite par le réseau de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a37e2-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="a37e2-152">Contrôle d’admission des appels des connexions PSTN</span><span class="sxs-lookup"><span data-stu-id="a37e2-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="a37e2-153">Le contrôle d’admission des appels est applicable sur le serveur de médiation, qu’il soit connecté à un IP/PBX, à une passerelle PSTN ou à une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="a37e2-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="a37e2-154">Étant donné que le serveur de médiation est un agent utilisateur dos à dos (B2BUA), il met fin au support.</span><span class="sxs-lookup"><span data-stu-id="a37e2-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="a37e2-155">Il comporte deux côtés de connexion : un côté connecté à Lync Server et un côté passerelle, qui est connecté à des passerelles PSTN, IP/PBX ou à des jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="a37e2-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="a37e2-156">Pour plus d’informations sur les connexions PSTN, voir [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a37e2-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="a37e2-157">Le contrôle d’admission des médias peut être appliqué sur les deux côtés du serveur de médiation sauf si la déviation du trafic multimédia est activée.</span><span class="sxs-lookup"><span data-stu-id="a37e2-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="a37e2-158">Si la déviation du trafic multimédia est activée, le trafic multimédia ne traverse pas le serveur de médiation mais transite directement entre le client Lync et la passerelle.</span><span class="sxs-lookup"><span data-stu-id="a37e2-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="a37e2-159">Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a37e2-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="a37e2-160">Pour plus d’informations, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a37e2-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="a37e2-161">La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions PSTN avec ou sans le contournement de média activé.</span><span class="sxs-lookup"><span data-stu-id="a37e2-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="a37e2-162">**Application du contrôle d’admission des appels sur des connexions PSTN**</span><span class="sxs-lookup"><span data-stu-id="a37e2-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="a37e2-163">![Application de la connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion de contournement de média CAC vocal")</span><span class="sxs-lookup"><span data-stu-id="a37e2-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="a37e2-164">Compatibilité du contrôle d’admission des appels avec les versions précédentes d’Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="a37e2-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="a37e2-165">Le contrôle d’admission des appels peut être activé uniquement sur les points de terminaison qui sont activés pour Lync Server 2010 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a37e2-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="a37e2-166">Le contrôle d’admission des appels ne peut pas être activé sur les points de terminaison exécutant Office Communicator 2007 R2 ou une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="a37e2-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="a37e2-167">**Application du contrôle d’admission des appels sur des versions de Lync Server différentes**</span><span class="sxs-lookup"><span data-stu-id="a37e2-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="a37e2-168">![Diagramme de comparaison des versions de la version CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramme de comparaison des versions de la version CAC")</span><span class="sxs-lookup"><span data-stu-id="a37e2-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

