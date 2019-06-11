---
title: 'Lync Server 2013 : Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="3904b-102">Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3904b-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3904b-103">_**Dernière modification de la rubrique:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="3904b-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="3904b-104">La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3904b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3904b-105">Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="3904b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3904b-106">Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3904b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3904b-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="3904b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3904b-108">Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="3904b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3904b-109">**Réseau de périmètre d’entreprise pour bordure consolidée mise à l’échelle avec des adresses IP privées à l’aide de tar**</span><span class="sxs-lookup"><span data-stu-id="3904b-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="3904b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead] (images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3904b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3904b-111">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="3904b-111">Port and Protocol Details</span></span>

<span data-ttu-id="3904b-112">Il est recommandé d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="3904b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3904b-113">Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="3904b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="3904b-114">Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans les fonctionnalités de messagerie instantanée, de présence, de conférence Web, audio/vidéo (A/V) et de Fédération.</span><span class="sxs-lookup"><span data-stu-id="3904b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3904b-115">Résumé du pare-feu pour les bords consolidés mis à l’échelle de l’équilibrage de charge DNS avec des adresses IP privées utilisant tar: interface externe-nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="3904b-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3904b-116">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="3904b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3904b-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="3904b-117">Source IP address</span></span></th>
<th><span data-ttu-id="3904b-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="3904b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="3904b-119">Remarques</span><span class="sxs-lookup"><span data-stu-id="3904b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3904b-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3904b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3904b-121">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-122">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="3904b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3904b-123">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</span><span class="sxs-lookup"><span data-stu-id="3904b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3904b-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3904b-125">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="3904b-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3904b-126">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-127">Le service de proxy XMPP envoie le trafic aux contacts XMPP dans les fédérations de XMPP définies.</span><span class="sxs-lookup"><span data-stu-id="3904b-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-128">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3904b-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3904b-129">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-130">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-131">Vérification et récupération des certificats</span><span class="sxs-lookup"><span data-stu-id="3904b-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3904b-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3904b-133">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-135">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="3904b-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3904b-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3904b-137">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-139">Requête DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="3904b-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-140">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-142">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-143">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="3904b-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-144">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-145">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-145">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-146">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-147">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="3904b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-148">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-149">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-150">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-151">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="3904b-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-152">PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-153">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-153">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-154">Service Edge de conférence Web Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-155">Support de conférences Web</span><span class="sxs-lookup"><span data-stu-id="3904b-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-156">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="3904b-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3904b-157">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-158">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-159">Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3904b-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-160">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="3904b-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3904b-161">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-162">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-162">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-163">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3904b-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-164">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="3904b-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3904b-165">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-166">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-167">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3904b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-168">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="3904b-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3904b-169">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-169">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-170">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-171">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3904b-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3904b-173">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-174">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-175">3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie.</span><span class="sxs-lookup"><span data-stu-id="3904b-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3904b-176">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="3904b-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3904b-178">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-179">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-180">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-182">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-183">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-184">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-186">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-187">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-187">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-188">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3904b-189">Résumé du pare-feu pour les bords consolidés mis à l’échelle de l’équilibrage de charge DNS avec des adresses IP privées à l’aide de tar: interface interne-nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="3904b-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3904b-190">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="3904b-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3904b-191">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="3904b-191">Source IP address</span></span></th>
<th><span data-ttu-id="3904b-192">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="3904b-192">Destination IP address</span></span></th>
<th><span data-ttu-id="3904b-193">Commentaires</span><span class="sxs-lookup"><span data-stu-id="3904b-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3904b-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3904b-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3904b-195">Tout (peut être défini comme adresse serveur frontale ou adresse IP de pool frontal exécutant le service passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="3904b-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3904b-196">Adresse IP de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3904b-197">Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="3904b-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3904b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-199">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="3904b-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3904b-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-201">Trafic SIP sortant (à partir du réalisateur, adresse IP du pool de réalisateurs, adresse IP du serveur frontal ou de la liste frontale) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3904b-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-203">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-204">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="3904b-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3904b-205">Trafic SIP entrant (adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3904b-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3904b-207">Tout (peut être défini comme adresse IP du serveur frontal ou chaque adresse IP du serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="3904b-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3904b-208">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-209">Trafic de conférences Web à partir du serveur frontal ou de chaque serveur frontal, s’il se trouve dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3904b-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3904b-211">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="3904b-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3904b-212">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-213">L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3904b-215">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-216">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-217">Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="3904b-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3904b-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-219">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-219">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-220">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-221">Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="3904b-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3904b-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3904b-223">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou pool contenant la Banque centrale de gestion).</span><span class="sxs-lookup"><span data-stu-id="3904b-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3904b-224">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-225">Réplication des modifications du magasin de gestion central vers le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="3904b-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3904b-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3904b-227">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-228">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-229">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="3904b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3904b-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3904b-231">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-232">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-233">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="3904b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3904b-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3904b-235">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-235">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-236">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3904b-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3904b-237">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="3904b-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3904b-238">Résumé du pare-feu pour la Fédération</span><span class="sxs-lookup"><span data-stu-id="3904b-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3904b-239">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="3904b-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3904b-240">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="3904b-240">Source IP address</span></span></th>
<th><span data-ttu-id="3904b-241">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="3904b-241">Destination IP address</span></span></th>
<th><span data-ttu-id="3904b-242">Remarques</span><span class="sxs-lookup"><span data-stu-id="3904b-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3904b-243">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-244">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="3904b-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3904b-245">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-245">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-246">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="3904b-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3904b-247">Résumé du pare-feu-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="3904b-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3904b-248">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="3904b-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3904b-249">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="3904b-249">Source IP address</span></span></th>
<th><span data-ttu-id="3904b-250">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="3904b-250">Destination IP address</span></span></th>
<th><span data-ttu-id="3904b-251">Remarques</span><span class="sxs-lookup"><span data-stu-id="3904b-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3904b-252">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-253">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="3904b-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3904b-254">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-255">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="3904b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-256">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3904b-257">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-258">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="3904b-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3904b-259">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="3904b-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-260">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3904b-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3904b-261">Clients</span><span class="sxs-lookup"><span data-stu-id="3904b-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="3904b-262">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-263">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="3904b-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-264">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="3904b-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3904b-265">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-266">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3904b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3904b-267">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</span><span class="sxs-lookup"><span data-stu-id="3904b-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3904b-269">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3904b-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3904b-271">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3904b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3904b-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3904b-273">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3904b-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3904b-274">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="3904b-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3904b-275">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3904b-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3904b-276">Résumé du pare-feu pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="3904b-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3904b-277">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="3904b-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3904b-278">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="3904b-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="3904b-279">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="3904b-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3904b-280">Commentaires</span><span class="sxs-lookup"><span data-stu-id="3904b-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3904b-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3904b-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3904b-282">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-282">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-283">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3904b-284">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="3904b-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3904b-285">Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="3904b-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3904b-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3904b-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3904b-287">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="3904b-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3904b-288">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-289">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="3904b-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3904b-290">Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="3904b-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3904b-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3904b-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3904b-292">Indifférente</span><span class="sxs-lookup"><span data-stu-id="3904b-292">Any</span></span></p></td>
<td><p><span data-ttu-id="3904b-293">Chaque adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="3904b-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="3904b-294">Trafic de XMPP interne depuis la passerelle XMPP du serveur frontal ou du pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="3904b-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

