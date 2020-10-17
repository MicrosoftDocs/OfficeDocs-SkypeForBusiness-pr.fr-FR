---
title: 'Lync Server 2013 : Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la traduction d’adresses réseau'
description: 'Lync Server 2013 : Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau.'
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563940"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="7bdf3-103">Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bdf3-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bdf3-104">_**Dernière modification de la rubrique :** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="7bdf3-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="7bdf3-105">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="7bdf3-106">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="7bdf3-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="7bdf3-107">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="7bdf3-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="7bdf3-109">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="7bdf3-110">**Réseau de périmètre d’entreprise pour le serveur Edge consolidé ajusté avec des adresses IP privées à l’aide de NAT**</span><span class="sxs-lookup"><span data-stu-id="7bdf3-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="7bdf3-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="7bdf3-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="7bdf3-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="7bdf3-112">Port and Protocol Details</span></span>

<span data-ttu-id="7bdf3-113">Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="7bdf3-114">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="7bdf3-115">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="7bdf3-116">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT : interface externe – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf3-117">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="7bdf3-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7bdf3-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="7bdf3-118">Source IP address</span></span></th>
<th><span data-ttu-id="7bdf3-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="7bdf3-119">Destination IP address</span></span></th>
<th><span data-ttu-id="7bdf3-120">Notes</span><span class="sxs-lookup"><span data-stu-id="7bdf3-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7bdf3-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-122">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-122">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-123">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-124">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="7bdf3-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7bdf3-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-126">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-127">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-127">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-128">Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="7bdf3-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-129">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="7bdf3-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-130">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-131">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-131">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-132">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="7bdf3-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-133">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="7bdf3-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-134">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-135">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-135">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-136">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-137">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="7bdf3-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-138">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-139">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-140">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-141">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-142">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-142">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-143">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-144">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="7bdf3-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-145">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-146">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-146">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-147">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-148">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-149">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-150">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-151">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-151">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-152">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-153">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-154">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-155">Service Edge de conférence Web de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-156">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="7bdf3-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-157">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="7bdf3-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-158">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-159">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-159">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-160">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-161">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="7bdf3-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-162">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-163">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-163">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-164">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-165">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="7bdf3-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-166">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-166">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-167">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-168">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="7bdf3-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-169">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="7bdf3-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-170">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-170">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-171">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-172">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="7bdf3-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-174">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-175">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-175">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-176">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="7bdf3-177">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-178">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-179">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-179">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-180">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-181">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-183">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-183">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-184">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-185">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-186">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-187">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-188">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-188">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-189">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="7bdf3-190">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT : interface interne – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf3-191">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="7bdf3-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7bdf3-192">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="7bdf3-192">Source IP address</span></span></th>
<th><span data-ttu-id="7bdf3-193">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="7bdf3-193">Destination IP address</span></span></th>
<th><span data-ttu-id="7bdf3-194">Comments</span><span class="sxs-lookup"><span data-stu-id="7bdf3-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7bdf3-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-196">Any (peut être défini comme adresse de serveur frontal ou adresse IP de pool frontal exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-197">Adresse IP de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-198">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="7bdf3-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-200">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-201">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-202">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-204">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-205">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-206">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="7bdf3-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-208">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-209">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-210">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="7bdf3-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-212">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-213">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-214">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-216">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-216">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-217">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-218">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="7bdf3-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-220">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-220">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-221">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-222">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="7bdf3-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-224">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-225">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-226">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="7bdf3-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-228">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-228">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-229">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-230">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="7bdf3-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="7bdf3-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-232">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-232">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-233">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-234">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="7bdf3-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="7bdf3-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-236">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-236">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-237">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-238">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="7bdf3-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="7bdf3-239">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="7bdf3-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf3-240">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="7bdf3-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7bdf3-241">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="7bdf3-241">Source IP address</span></span></th>
<th><span data-ttu-id="7bdf3-242">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="7bdf3-242">Destination IP address</span></span></th>
<th><span data-ttu-id="7bdf3-243">Notes</span><span class="sxs-lookup"><span data-stu-id="7bdf3-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-244">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-245">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="7bdf3-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-246">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-246">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-247">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7bdf3-248">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="7bdf3-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf3-249">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="7bdf3-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7bdf3-250">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="7bdf3-250">Source IP address</span></span></th>
<th><span data-ttu-id="7bdf3-251">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="7bdf3-251">Destination IP address</span></span></th>
<th><span data-ttu-id="7bdf3-252">Notes</span><span class="sxs-lookup"><span data-stu-id="7bdf3-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-253">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-254">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="7bdf3-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-255">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-256">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-257">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7bdf3-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-258">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-259">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="7bdf3-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-260">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-261">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7bdf3-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-262">Clients</span><span class="sxs-lookup"><span data-stu-id="7bdf3-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-263">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-264">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="7bdf3-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-265">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="7bdf3-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-266">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-267">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7bdf3-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-268">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-270">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-271">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7bdf3-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-272">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7bdf3-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-273">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7bdf3-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-274">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7bdf3-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-275">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-276">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7bdf3-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7bdf3-277">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="7bdf3-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf3-278">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="7bdf3-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7bdf3-279">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="7bdf3-280">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="7bdf3-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="7bdf3-281">Comments</span><span class="sxs-lookup"><span data-stu-id="7bdf3-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7bdf3-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-283">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-283">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-284">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-285">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7bdf3-286">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="7bdf3-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf3-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7bdf3-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-288">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-289">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-289">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-290">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="7bdf3-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7bdf3-291">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="7bdf3-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf3-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7bdf3-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-293">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="7bdf3-293">Any</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-294">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="7bdf3-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="7bdf3-295">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="7bdf3-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

