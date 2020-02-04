---
title: Résumé des ports - Serveur Edge unique consolidé avec adresses IP publiques
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="63024-102">Résumé des ports - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63024-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63024-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="63024-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="63024-104">La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="63024-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="63024-105">Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="63024-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="63024-106">Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="63024-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="63024-107">Les informations de planification du proxy inverse et de la Fédération s’exécutent dans [les scénarios de proxy inverse dans Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) et la [planification de la Fédération SIP, de la Fédération et de la messagerie instantanée publique dans les sections de Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivement.</span><span class="sxs-lookup"><span data-stu-id="63024-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="63024-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="63024-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="63024-109">Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="63024-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="63024-110">**Réseau de périmètre d’entreprise pour une seule périphérie consolidée avec un adresse IP publique**</span><span class="sxs-lookup"><span data-stu-id="63024-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="63024-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="63024-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="63024-112">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="63024-112">Port and Protocol Details</span></span>

<span data-ttu-id="63024-113">Nous vous recommandons d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="63024-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="63024-114">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire que le trafic SIP soit acheminé de manière bidirectionnelle, comme le montre la figure dans le trafic de périphérie entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="63024-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="63024-115">Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans les fonctionnalités de messagerie instantanée, de présence, de conférence Web, audio/vidéo (A/V) et de Fédération.</span><span class="sxs-lookup"><span data-stu-id="63024-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="63024-116">Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP publiques : interface externe</span><span class="sxs-lookup"><span data-stu-id="63024-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63024-117">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="63024-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="63024-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="63024-118">Source IP address</span></span></th>
<th><span data-ttu-id="63024-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="63024-119">Destination IP address</span></span></th>
<th><span data-ttu-id="63024-120">Remarques</span><span class="sxs-lookup"><span data-stu-id="63024-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63024-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="63024-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="63024-122">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-122">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-123">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="63024-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="63024-124">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</span><span class="sxs-lookup"><span data-stu-id="63024-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-125">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="63024-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="63024-126">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-127">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-127">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-128">Vérification et récupération des certificats</span><span class="sxs-lookup"><span data-stu-id="63024-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="63024-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="63024-130">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-131">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-131">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-132">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="63024-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="63024-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="63024-134">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-135">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-135">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-136">Requête DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="63024-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-137">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="63024-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-138">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-139">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-140">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="63024-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-141">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="63024-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-142">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-142">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-143">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-144">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="63024-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-145">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="63024-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-146">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-147">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-147">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-148">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="63024-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-149">PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-150">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-150">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-151">Adresse IP publique du service Edge Conferencing Server Web</span><span class="sxs-lookup"><span data-stu-id="63024-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-152">Support de conférences Web</span><span class="sxs-lookup"><span data-stu-id="63024-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-153">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="63024-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="63024-154">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-155">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-155">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-156">Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63024-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-157">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="63024-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="63024-158">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-159">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-159">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-160">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="63024-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-161">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="63024-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="63024-162">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-162">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-163">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-164">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="63024-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-165">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="63024-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="63024-166">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-166">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-167">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-168">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="63024-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="63024-170">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-171">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-171">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-172">3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie.</span><span class="sxs-lookup"><span data-stu-id="63024-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="63024-173">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="63024-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="63024-175">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-175">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-176">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-177">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-179">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-179">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-180">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-181">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-183">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="63024-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-184">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-184">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-185">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="63024-186">Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP publiques : interface interne</span><span class="sxs-lookup"><span data-stu-id="63024-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63024-187">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="63024-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="63024-188">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="63024-188">Source IP address</span></span></th>
<th><span data-ttu-id="63024-189">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="63024-189">Destination IP address</span></span></th>
<th><span data-ttu-id="63024-190">Commentaires</span><span class="sxs-lookup"><span data-stu-id="63024-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63024-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="63024-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="63024-192">Tout (peut être défini comme Standard Edition Server IP, adresse IP du serveur Standard Edition ou adresse IP du pool exécutant le service passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="63024-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="63024-193">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-194">Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="63024-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="63024-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-196">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="63024-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="63024-197">Adresse IP du serveur Edge ou pool qui contient l’interface interne</span><span class="sxs-lookup"><span data-stu-id="63024-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-198">Trafic SIP sortant (à partir du réalisateur, adresse IP du pool de réalisateurs, adresse IP du serveur frontal ou de la liste frontale) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="63024-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-201">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, serveur frontal ou adresse du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="63024-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="63024-202">Trafic SIP entrant (adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="63024-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="63024-204">Tout (peut être défini comme adresse IP du serveur frontal ou chaque adresse IP du serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="63024-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="63024-205">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-206">Trafic de conférences Web à partir du serveur frontal ou de chaque serveur frontal, s’il se trouve dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="63024-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="63024-208">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="63024-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="63024-209">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-210">L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="63024-212">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-212">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-213">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-214">Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="63024-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="63024-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-216">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-216">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-217">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-218">Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="63024-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="63024-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="63024-220">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou pool contenant la Banque centrale de gestion).</span><span class="sxs-lookup"><span data-stu-id="63024-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="63024-221">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-222">Réplication des modifications du magasin de gestion central vers le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="63024-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="63024-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="63024-224">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-224">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-225">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-226">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="63024-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="63024-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="63024-228">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-228">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-229">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-230">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="63024-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="63024-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="63024-232">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-232">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-233">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="63024-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="63024-234">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="63024-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="63024-235">Résumé du pare-feu pour la Fédération</span><span class="sxs-lookup"><span data-stu-id="63024-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63024-236">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="63024-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="63024-237">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="63024-237">Source IP address</span></span></th>
<th><span data-ttu-id="63024-238">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="63024-238">Destination IP address</span></span></th>
<th><span data-ttu-id="63024-239">Remarques</span><span class="sxs-lookup"><span data-stu-id="63024-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63024-240">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="63024-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-241">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="63024-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-242">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-242">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-243">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="63024-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="63024-244">Résumé du pare-feu-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="63024-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63024-245">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="63024-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="63024-246">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="63024-246">Source IP address</span></span></th>
<th><span data-ttu-id="63024-247">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="63024-247">Destination IP address</span></span></th>
<th><span data-ttu-id="63024-248">Remarques</span><span class="sxs-lookup"><span data-stu-id="63024-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63024-249">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="63024-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-250">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="63024-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="63024-251">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-252">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="63024-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-253">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="63024-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="63024-254">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-255">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="63024-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="63024-256">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="63024-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-257">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="63024-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="63024-258">Clients</span><span class="sxs-lookup"><span data-stu-id="63024-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="63024-259">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-260">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="63024-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-261">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="63024-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="63024-262">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="63024-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-263">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="63024-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="63024-264">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</span><span class="sxs-lookup"><span data-stu-id="63024-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="63024-266">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="63024-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-267">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="63024-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="63024-268">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="63024-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="63024-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="63024-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="63024-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="63024-271">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="63024-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="63024-272">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="63024-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="63024-273">Résumé du pare-feu pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="63024-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63024-274">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="63024-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="63024-275">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="63024-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="63024-276">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="63024-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="63024-277">Commentaires</span><span class="sxs-lookup"><span data-stu-id="63024-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63024-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="63024-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="63024-279">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-279">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-280">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-281">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="63024-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="63024-282">Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="63024-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63024-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="63024-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="63024-284">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="63024-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="63024-285">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-285">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-286">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="63024-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="63024-287">Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="63024-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63024-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="63024-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="63024-289">Indifférente</span><span class="sxs-lookup"><span data-stu-id="63024-289">Any</span></span></p></td>
<td><p><span data-ttu-id="63024-290">Chaque adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="63024-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="63024-291">Trafic de XMPP interne depuis la passerelle XMPP du serveur frontal ou du pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="63024-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

