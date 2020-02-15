---
title: 'Lync Server 2013 : Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la traduction d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96bf91dfaf4d231ec64ce1b385983f63b15ee0b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="da739-102">Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da739-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da739-103">_**Dernière modification de la rubrique :** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="da739-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="da739-104">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="da739-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="da739-105">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="da739-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="da739-106">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="da739-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="da739-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="da739-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="da739-108">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="da739-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="da739-109">**Réseau de périmètre d’entreprise pour le serveur Edge consolidé ajusté avec des adresses IP privées à l’aide de NAT**</span><span class="sxs-lookup"><span data-stu-id="da739-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="da739-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="da739-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="da739-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="da739-111">Port and Protocol Details</span></span>

<span data-ttu-id="da739-112">Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="da739-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="da739-113">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="da739-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="da739-114">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="da739-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="da739-115">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT : interface externe – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="da739-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da739-116">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="da739-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da739-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="da739-117">Source IP address</span></span></th>
<th><span data-ttu-id="da739-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="da739-118">Destination IP address</span></span></th>
<th><span data-ttu-id="da739-119">Notes</span><span class="sxs-lookup"><span data-stu-id="da739-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da739-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da739-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da739-121">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-121">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-122">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="da739-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="da739-123">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="da739-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da739-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da739-125">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="da739-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="da739-126">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-126">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-127">Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="da739-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-128">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="da739-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="da739-129">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-130">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-130">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-131">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="da739-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-132">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="da739-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="da739-133">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-134">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-135">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="da739-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-136">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="da739-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="da739-137">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-138">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-139">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="da739-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-140">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-141">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-141">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-142">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-143">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="da739-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-144">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-145">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-145">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-146">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-147">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="da739-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-148">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-149">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-150">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-150">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-151">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="da739-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-152">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-153">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-153">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-154">Service Edge de conférence Web de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-155">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="da739-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-156">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="da739-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da739-157">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-158">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-158">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-159">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da739-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-160">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="da739-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da739-161">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-162">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-162">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-163">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="da739-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-164">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="da739-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da739-165">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-165">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-166">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-167">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="da739-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-168">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="da739-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da739-169">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-169">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-170">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-171">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="da739-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da739-173">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-174">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-174">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-175">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="da739-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="da739-176">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="da739-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da739-178">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-178">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-179">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-180">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-182">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-182">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-183">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-184">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-186">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-187">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-187">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-188">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="da739-189">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT : interface interne – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="da739-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da739-190">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="da739-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da739-191">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="da739-191">Source IP address</span></span></th>
<th><span data-ttu-id="da739-192">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="da739-192">Destination IP address</span></span></th>
<th><span data-ttu-id="da739-193">Commentaires</span><span class="sxs-lookup"><span data-stu-id="da739-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da739-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="da739-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="da739-195">Any (peut être défini comme adresse de serveur frontal ou adresse IP de pool frontal exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="da739-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="da739-196">Adresse IP de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="da739-197">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="da739-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-199">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="da739-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="da739-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-201">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-203">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-204">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="da739-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="da739-205">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="da739-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="da739-207">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="da739-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="da739-208">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-209">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="da739-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="da739-211">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="da739-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="da739-212">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-213">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da739-215">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-215">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-216">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-217">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="da739-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-219">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-219">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-220">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-221">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="da739-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="da739-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="da739-223">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="da739-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="da739-224">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-225">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="da739-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="da739-227">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-227">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-228">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-229">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="da739-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="da739-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="da739-231">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-231">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-232">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-233">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="da739-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="da739-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="da739-235">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-235">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-236">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="da739-237">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="da739-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="da739-238">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="da739-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da739-239">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="da739-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da739-240">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="da739-240">Source IP address</span></span></th>
<th><span data-ttu-id="da739-241">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="da739-241">Destination IP address</span></span></th>
<th><span data-ttu-id="da739-242">Notes</span><span class="sxs-lookup"><span data-stu-id="da739-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da739-243">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-244">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="da739-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="da739-245">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-245">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-246">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="da739-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="da739-247">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="da739-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da739-248">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="da739-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da739-249">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="da739-249">Source IP address</span></span></th>
<th><span data-ttu-id="da739-250">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="da739-250">Destination IP address</span></span></th>
<th><span data-ttu-id="da739-251">Notes</span><span class="sxs-lookup"><span data-stu-id="da739-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da739-252">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-253">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="da739-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="da739-254">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-255">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="da739-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-256">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="da739-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="da739-257">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-258">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="da739-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="da739-259">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="da739-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-260">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="da739-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="da739-261">Clients</span><span class="sxs-lookup"><span data-stu-id="da739-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="da739-262">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-263">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="da739-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-264">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="da739-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="da739-265">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-266">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="da739-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="da739-267">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="da739-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da739-269">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="da739-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="da739-271">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="da739-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="da739-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="da739-273">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="da739-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="da739-274">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="da739-275">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="da739-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="da739-276">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="da739-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da739-277">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="da739-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="da739-278">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="da739-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="da739-279">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="da739-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="da739-280">Commentaires</span><span class="sxs-lookup"><span data-stu-id="da739-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da739-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da739-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da739-282">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-282">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-283">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="da739-284">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="da739-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="da739-285">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="da739-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da739-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="da739-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="da739-287">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="da739-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="da739-288">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-288">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-289">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="da739-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="da739-290">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="da739-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da739-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="da739-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="da739-292">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="da739-292">Any</span></span></p></td>
<td><p><span data-ttu-id="da739-293">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="da739-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="da739-294">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="da739-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

