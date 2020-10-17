---
title: Résumé des ports-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau
description: Résumé des ports-serveur Edge unique consolidé avec adresses IP privées à l’aide de la conversion d’adresses réseau.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564560"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="722d8-103">Résumé des ports-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="722d8-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="722d8-104">_**Dernière modification de la rubrique :** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="722d8-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="722d8-105">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="722d8-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="722d8-106">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="722d8-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="722d8-107">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="722d8-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="722d8-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="722d8-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="722d8-109">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="722d8-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="722d8-110">**Périmètre réseau pour un serveur Edge consolidé unique avec un adressage IP privé à l’aide de la traduction d’adresses réseau**</span><span class="sxs-lookup"><span data-stu-id="722d8-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="722d8-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="722d8-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="722d8-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="722d8-112">Port and Protocol Details</span></span>

<span data-ttu-id="722d8-113">Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="722d8-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="722d8-114">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="722d8-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="722d8-115">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="722d8-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="722d8-116">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP privées à l’aide de NAT : interface externe</span><span class="sxs-lookup"><span data-stu-id="722d8-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="722d8-117">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="722d8-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="722d8-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="722d8-118">Source IP address</span></span></th>
<th><span data-ttu-id="722d8-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="722d8-119">Destination IP address</span></span></th>
<th><span data-ttu-id="722d8-120">Notes</span><span class="sxs-lookup"><span data-stu-id="722d8-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="722d8-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="722d8-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="722d8-122">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-122">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-123">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="722d8-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="722d8-124">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="722d8-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-125">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="722d8-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="722d8-126">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-127">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-127">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-128">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="722d8-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-129">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="722d8-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="722d8-130">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-131">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-131">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-132">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="722d8-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-133">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="722d8-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="722d8-134">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-135">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-135">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-136">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="722d8-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-137">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-138">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-138">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-139">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-140">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="722d8-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-141">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-142">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-142">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-143">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-144">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="722d8-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-145">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-146">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-147">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-147">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-148">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="722d8-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-149">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-150">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-150">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-151">Service Edge de conférence Web de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-152">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="722d8-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-153">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="722d8-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="722d8-154">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-155">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-155">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-156">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="722d8-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-157">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="722d8-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="722d8-158">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-159">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-159">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-160">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="722d8-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-161">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="722d8-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="722d8-162">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-162">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-163">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-164">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="722d8-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-165">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="722d8-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="722d8-166">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-166">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-167">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-168">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="722d8-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="722d8-170">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-171">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-171">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-172">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="722d8-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="722d8-173">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="722d8-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="722d8-175">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-175">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-176">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-177">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-179">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-179">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-180">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-181">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-183">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-184">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-184">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-185">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="722d8-186">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP privées à l’aide de NAT : interface interne</span><span class="sxs-lookup"><span data-stu-id="722d8-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="722d8-187">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="722d8-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="722d8-188">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="722d8-188">Source IP address</span></span></th>
<th><span data-ttu-id="722d8-189">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="722d8-189">Destination IP address</span></span></th>
<th><span data-ttu-id="722d8-190">Comments</span><span class="sxs-lookup"><span data-stu-id="722d8-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="722d8-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="722d8-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="722d8-192">Any (peut être défini en tant qu’adresse IP Standard Edition Server, Standard Edition Server ou adresse IP du pool exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="722d8-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="722d8-193">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-194">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="722d8-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-196">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="722d8-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="722d8-197">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-198">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-201">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="722d8-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="722d8-202">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="722d8-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="722d8-204">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="722d8-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="722d8-205">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-206">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="722d8-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="722d8-208">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="722d8-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="722d8-209">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-210">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="722d8-212">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-212">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-213">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-214">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="722d8-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-216">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-216">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-217">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-218">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="722d8-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="722d8-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="722d8-220">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="722d8-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="722d8-221">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-222">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="722d8-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="722d8-224">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-224">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-225">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-226">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="722d8-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="722d8-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="722d8-228">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-228">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-229">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-230">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="722d8-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="722d8-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="722d8-232">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-232">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-233">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="722d8-234">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="722d8-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="722d8-235">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="722d8-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="722d8-236">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="722d8-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="722d8-237">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="722d8-237">Source IP address</span></span></th>
<th><span data-ttu-id="722d8-238">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="722d8-238">Destination IP address</span></span></th>
<th><span data-ttu-id="722d8-239">Notes</span><span class="sxs-lookup"><span data-stu-id="722d8-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="722d8-240">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-241">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="722d8-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="722d8-242">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-242">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-243">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="722d8-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="722d8-244">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="722d8-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="722d8-245">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="722d8-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="722d8-246">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="722d8-246">Source IP address</span></span></th>
<th><span data-ttu-id="722d8-247">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="722d8-247">Destination IP address</span></span></th>
<th><span data-ttu-id="722d8-248">Notes</span><span class="sxs-lookup"><span data-stu-id="722d8-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="722d8-249">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-250">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="722d8-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="722d8-251">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-252">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="722d8-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-253">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="722d8-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="722d8-254">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-255">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="722d8-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="722d8-256">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="722d8-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-257">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="722d8-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="722d8-258">Clients</span><span class="sxs-lookup"><span data-stu-id="722d8-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="722d8-259">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-260">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="722d8-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-261">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="722d8-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="722d8-262">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-263">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="722d8-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="722d8-264">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="722d8-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="722d8-266">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-267">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="722d8-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="722d8-268">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="722d8-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="722d8-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="722d8-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="722d8-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="722d8-271">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="722d8-272">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="722d8-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="722d8-273">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="722d8-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="722d8-274">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="722d8-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="722d8-275">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="722d8-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="722d8-276">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="722d8-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="722d8-277">Comments</span><span class="sxs-lookup"><span data-stu-id="722d8-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="722d8-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="722d8-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="722d8-279">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-279">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-280">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="722d8-281">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="722d8-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="722d8-282">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="722d8-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="722d8-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="722d8-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="722d8-284">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="722d8-285">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-285">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-286">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="722d8-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="722d8-287">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="722d8-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="722d8-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="722d8-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="722d8-289">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="722d8-289">Any</span></span></p></td>
<td><p><span data-ttu-id="722d8-290">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="722d8-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="722d8-291">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="722d8-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

