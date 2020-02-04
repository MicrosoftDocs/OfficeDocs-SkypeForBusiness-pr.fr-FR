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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="201a3-102">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="201a3-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="201a3-103">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="201a3-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="201a3-104">Les communications en temps réel sont sensibles à la latence et à la perte de paquets qui peuvent se produire sur des réseaux encombrés.</span><span class="sxs-lookup"><span data-stu-id="201a3-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="201a3-105">Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies.</span><span class="sxs-lookup"><span data-stu-id="201a3-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="201a3-106">La conception CAC de Lync Server 2013 propose quatre attributs principaux :</span><span class="sxs-lookup"><span data-stu-id="201a3-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="201a3-107">Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.</span><span class="sxs-lookup"><span data-stu-id="201a3-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="201a3-p102">Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du point de terminaison et non pas de l’emplacement où est hébergé l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="201a3-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="201a3-110">Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="201a3-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="201a3-111">Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau.</span><span class="sxs-lookup"><span data-stu-id="201a3-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="201a3-112">Pour consulter des exemples, voir [composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="201a3-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="201a3-113">Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison de réseau étendu, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur RTC.</span><span class="sxs-lookup"><span data-stu-id="201a3-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="201a3-p104">Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.</span><span class="sxs-lookup"><span data-stu-id="201a3-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="201a3-116">Les administrateurs définissent des stratégies CAC qui sont appliquées par le service de stratégie de bande passante qui est installé avec chaque pool frontal.</span><span class="sxs-lookup"><span data-stu-id="201a3-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="201a3-117">Les paramètres CAC sont automatiquement propagés vers tous les serveurs front end de Lync Server de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="201a3-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="201a3-118">Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :</span><span class="sxs-lookup"><span data-stu-id="201a3-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="201a3-119">Internet</span><span class="sxs-lookup"><span data-stu-id="201a3-119">Internet</span></span>

2.  <span data-ttu-id="201a3-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="201a3-120">PSTN</span></span>

3.  <span data-ttu-id="201a3-121">Messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="201a3-121">Voice mail</span></span>

<span data-ttu-id="201a3-p106">L’enregistrement des détails des appels capture les informations concernant les appels réacheminés vers RTC ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.</span><span class="sxs-lookup"><span data-stu-id="201a3-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="201a3-124">Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="201a3-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="201a3-p107">Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison de réseau étendu. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="201a3-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="201a3-129">Considérations relatives au contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="201a3-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="201a3-130">L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central.</span><span class="sxs-lookup"><span data-stu-id="201a3-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="201a3-131">Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites.</span><span class="sxs-lookup"><span data-stu-id="201a3-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="201a3-132">Le service de stratégie de bande passante s’exécute dans le cadre des serveurs frontaux et, par conséquent, la haute disponibilité est intégrée au sein de ce pool.</span><span class="sxs-lookup"><span data-stu-id="201a3-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="201a3-133">Le service de stratégie de bande passante qui s’exécute sur chaque serveur frontal se synchronise toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="201a3-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="201a3-134">Si le pool frontal ne fonctionne pas, les stratégies CAC ne sont plus appliquées pour ce site tant qu’il n’y a pas de pool frontal</span><span class="sxs-lookup"><span data-stu-id="201a3-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="201a3-135">Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="201a3-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="201a3-136">Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.</span><span class="sxs-lookup"><span data-stu-id="201a3-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="201a3-137">Le service de stratégie de bande passante fournit une haute disponibilité au sein d’un pool frontal. Toutefois, elle ne fournit pas de redondance entre les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="201a3-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="201a3-138">Le service de stratégie de bande passante ne peut pas basculer d’un pool frontal à un autre.</span><span class="sxs-lookup"><span data-stu-id="201a3-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="201a3-139">Une fois que le service pour le pool frontal est restauré, le service de stratégie de bande passante reprend et peut appliquer de nouveau les contrôles de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="201a3-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="201a3-140">Considérations relatives au réseau</span><span class="sxs-lookup"><span data-stu-id="201a3-140">Network Considerations</span></span>

<span data-ttu-id="201a3-141">Même si la restriction de bande passante pour l’audio et la vidéo est appliquée par le service de stratégie de bande passante dans Lync Server 2013, cette restriction n’est pas appliquée sur le routeur réseau (couches 2 et 3).</span><span class="sxs-lookup"><span data-stu-id="201a3-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="201a3-142">Lync Server 2010 CAC ne peut pas empêcher une application de données (par exemple, l’utilisation de la bande passante réseau entière sur une liaison réseau étendu, y compris la bande passante réservée aux appels audio et vidéo par votre stratégie CAC).</span><span class="sxs-lookup"><span data-stu-id="201a3-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="201a3-143">Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="201a3-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="201a3-144">Par conséquent, la meilleure pratique consiste à coordonner les stratégies de bande passante du contrôle d’admission des données que vous définissez avec les paramètres QoS que vous pouvez déployer.</span><span class="sxs-lookup"><span data-stu-id="201a3-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="201a3-145">Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)</span><span class="sxs-lookup"><span data-stu-id="201a3-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="201a3-p111">Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.</span><span class="sxs-lookup"><span data-stu-id="201a3-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="201a3-148">Contrôle d’admission des appels des utilisateurs extérieurs</span><span class="sxs-lookup"><span data-stu-id="201a3-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="201a3-149">Le contrôle d’admission des appels n’est pas appliqué aux utilisateurs distants où le trafic réseau circule via Internet.</span><span class="sxs-lookup"><span data-stu-id="201a3-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="201a3-150">Dans la mesure où le trafic multimédia traverse Internet, qui n’est pas géré par Lync Server, le CAC ne peut pas être appliqué.</span><span class="sxs-lookup"><span data-stu-id="201a3-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="201a3-151">Les vérifications CAC seront exécutées, toutefois, sur la partie de l’appel qui circule par le biais du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="201a3-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="201a3-152">Contrôle d’admission des appels des connexions RTC</span><span class="sxs-lookup"><span data-stu-id="201a3-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="201a3-153">Le contrôle d’admission des appels est applicable sur le serveur de médiation, qu’il s’agisse d’un réseau IP/PBX, d’une passerelle PSTN ou d’une connexion SIP.</span><span class="sxs-lookup"><span data-stu-id="201a3-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="201a3-154">Dans la mesure où le serveur de médiation est un agent utilisateur dorsal (B2BUA), il arrête le média.</span><span class="sxs-lookup"><span data-stu-id="201a3-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="201a3-155">Il a deux côtés de connexion : le côté connecté à Lync Server et un côté passerelle, qui est connecté à des passerelles RTC, des PBX IP/PBX ou des lignes SIP.</span><span class="sxs-lookup"><span data-stu-id="201a3-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="201a3-156">Pour plus d’informations sur les connexions RTC, voir [planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="201a3-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="201a3-157">Le CAC peut être appliqué sur les deux côtés du serveur de médiation, sauf si la dérivation multimédia est activée.</span><span class="sxs-lookup"><span data-stu-id="201a3-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="201a3-158">Si l’option de contournement du contenu multimédia est activée, le trafic multimédia ne traverse pas le serveur de médiation mais est transmis directement entre le client et la passerelle Lync.</span><span class="sxs-lookup"><span data-stu-id="201a3-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="201a3-159">Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="201a3-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="201a3-160">Pour plus d’informations, reportez-vous à la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="201a3-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="201a3-161">La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions RTC avec ou sans la déviation du trafic multimédia activée.</span><span class="sxs-lookup"><span data-stu-id="201a3-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="201a3-162">**Application du contrôle d’admission des appels sur des connexions RTC**</span><span class="sxs-lookup"><span data-stu-id="201a3-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="201a3-163">![Application de connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de connexion de contournement de média CAC vocal")</span><span class="sxs-lookup"><span data-stu-id="201a3-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="201a3-164">Compatibilité du contrôle d’admission des appels avec les versions antérieures d’Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="201a3-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="201a3-165">Le contrôle d’admission des appels ne peut être activé que sur les points de terminaison activés pour Lync Server 2010 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="201a3-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="201a3-166">Le contrôle d’admission des appels ne peut pas être activé sur des points de terminaison exécutant Office Communicator 2007 R2 ou une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="201a3-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="201a3-167">**Application de CAC sur différentes versions de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="201a3-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="201a3-168">![Diagramme de comparaison de version CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramme de comparaison de version CAC")</span><span class="sxs-lookup"><span data-stu-id="201a3-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

