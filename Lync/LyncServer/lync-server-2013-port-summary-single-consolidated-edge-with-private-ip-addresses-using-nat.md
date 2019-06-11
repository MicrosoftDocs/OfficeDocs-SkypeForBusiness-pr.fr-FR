---
title: Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avecla conversion d’adresses réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7c908d52577375f9caaab974f059ffda17fb35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="81eed-102">Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81eed-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81eed-103">_**Dernière modification de la rubrique:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="81eed-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="81eed-104">La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="81eed-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="81eed-105">Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="81eed-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="81eed-106">Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="81eed-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="81eed-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="81eed-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="81eed-108">Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="81eed-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="81eed-109">**Périmètre réseau d’un serveur Edge consolidé unique avec adresse IP privée utilisant tar**</span><span class="sxs-lookup"><span data-stu-id="81eed-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="81eed-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="81eed-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="81eed-111">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="81eed-111">Port and Protocol Details</span></span>

<span data-ttu-id="81eed-112">Nous vous recommandons d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="81eed-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="81eed-113">Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="81eed-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="81eed-114">Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans la messagerie instantanée, la présence, les conférences Web, les appels audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="81eed-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="81eed-115">Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP privées utilisant tar: interface externe</span><span class="sxs-lookup"><span data-stu-id="81eed-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81eed-116">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="81eed-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81eed-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="81eed-117">Source IP address</span></span></th>
<th><span data-ttu-id="81eed-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="81eed-118">Destination IP address</span></span></th>
<th><span data-ttu-id="81eed-119">Remarques</span><span class="sxs-lookup"><span data-stu-id="81eed-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81eed-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81eed-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81eed-121">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-121">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-122">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="81eed-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="81eed-123">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</span><span class="sxs-lookup"><span data-stu-id="81eed-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-124">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="81eed-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="81eed-125">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-126">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-126">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-127">Vérification et récupération des certificats</span><span class="sxs-lookup"><span data-stu-id="81eed-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="81eed-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="81eed-129">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-130">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-130">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-131">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="81eed-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="81eed-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="81eed-133">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-134">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-135">Requête DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="81eed-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-136">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-137">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-137">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-138">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-139">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="81eed-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-140">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-141">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-142">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-143">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="81eed-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-144">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-145">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-146">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-146">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-147">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="81eed-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-148">PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-149">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-149">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-150">Service Edge de conférence Web Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-151">Support de conférences Web</span><span class="sxs-lookup"><span data-stu-id="81eed-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-152">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81eed-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81eed-153">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-154">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-155">Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81eed-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-156">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81eed-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81eed-157">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-158">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-158">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-159">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="81eed-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-160">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81eed-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81eed-161">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-161">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-162">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-163">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="81eed-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-164">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81eed-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81eed-165">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-165">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-166">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-167">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="81eed-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81eed-169">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-170">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-170">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-171">3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie.</span><span class="sxs-lookup"><span data-stu-id="81eed-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="81eed-172">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="81eed-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81eed-174">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-174">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-175">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-176">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-178">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-178">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-179">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-180">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-182">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-183">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-183">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-184">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="81eed-185">Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP privées utilisant tar: interface interne</span><span class="sxs-lookup"><span data-stu-id="81eed-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81eed-186">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="81eed-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81eed-187">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="81eed-187">Source IP address</span></span></th>
<th><span data-ttu-id="81eed-188">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="81eed-188">Destination IP address</span></span></th>
<th><span data-ttu-id="81eed-189">Commentaires</span><span class="sxs-lookup"><span data-stu-id="81eed-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81eed-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="81eed-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="81eed-191">Tout (peut être défini comme Standard Edition Server IP, adresse IP du serveur Standard Edition ou adresse IP du pool exécutant le service passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="81eed-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="81eed-192">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-193">Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="81eed-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81eed-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-195">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="81eed-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="81eed-196">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-197">Trafic SIP sortant (à partir du réalisateur, adresse IP du pool de réalisateurs, adresse IP du serveur frontal ou de la liste frontale) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81eed-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-199">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-200">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="81eed-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="81eed-201">Trafic SIP entrant (adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="81eed-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="81eed-203">Tout (peut être défini comme adresse IP du serveur frontal ou chaque adresse IP du serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="81eed-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="81eed-204">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-205">Trafic de conférences Web à partir du serveur frontal ou de chaque serveur frontal, s’il se trouve dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="81eed-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="81eed-207">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="81eed-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="81eed-208">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-209">L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81eed-211">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-211">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-212">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-213">Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="81eed-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81eed-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-215">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-215">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-216">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-217">Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="81eed-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="81eed-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="81eed-219">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou pool contenant la Banque centrale de gestion).</span><span class="sxs-lookup"><span data-stu-id="81eed-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="81eed-220">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-221">Réplication des modifications du magasin de gestion central vers le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="81eed-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="81eed-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="81eed-223">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-223">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-224">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-225">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="81eed-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="81eed-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="81eed-227">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-227">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-228">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-229">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="81eed-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="81eed-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="81eed-231">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-231">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-232">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81eed-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81eed-233">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="81eed-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="81eed-234">Résumé du pare-feu pour la Fédération</span><span class="sxs-lookup"><span data-stu-id="81eed-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81eed-235">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="81eed-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81eed-236">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="81eed-236">Source IP address</span></span></th>
<th><span data-ttu-id="81eed-237">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="81eed-237">Destination IP address</span></span></th>
<th><span data-ttu-id="81eed-238">Remarques</span><span class="sxs-lookup"><span data-stu-id="81eed-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81eed-239">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-240">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="81eed-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81eed-241">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-241">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-242">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="81eed-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="81eed-243">Résumé du pare-feu-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="81eed-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81eed-244">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="81eed-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81eed-245">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="81eed-245">Source IP address</span></span></th>
<th><span data-ttu-id="81eed-246">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="81eed-246">Destination IP address</span></span></th>
<th><span data-ttu-id="81eed-247">Remarques</span><span class="sxs-lookup"><span data-stu-id="81eed-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81eed-248">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-249">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="81eed-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="81eed-250">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-251">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="81eed-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-252">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81eed-253">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-254">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="81eed-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="81eed-255">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="81eed-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-256">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="81eed-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81eed-257">Clients</span><span class="sxs-lookup"><span data-stu-id="81eed-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="81eed-258">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-259">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="81eed-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-260">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81eed-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81eed-261">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-262">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81eed-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81eed-263">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</span><span class="sxs-lookup"><span data-stu-id="81eed-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81eed-265">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-266">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81eed-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81eed-267">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81eed-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81eed-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81eed-269">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81eed-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81eed-270">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="81eed-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81eed-271">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81eed-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="81eed-272">Résumé du pare-feu pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="81eed-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81eed-273">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="81eed-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81eed-274">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="81eed-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="81eed-275">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="81eed-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="81eed-276">Commentaires</span><span class="sxs-lookup"><span data-stu-id="81eed-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81eed-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81eed-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81eed-278">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-278">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-279">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="81eed-280">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="81eed-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="81eed-281">Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="81eed-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81eed-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81eed-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81eed-283">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="81eed-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="81eed-284">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-284">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-285">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="81eed-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="81eed-286">Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="81eed-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81eed-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="81eed-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="81eed-288">Indifférente</span><span class="sxs-lookup"><span data-stu-id="81eed-288">Any</span></span></p></td>
<td><p><span data-ttu-id="81eed-289">Chaque adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="81eed-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="81eed-290">Trafic de XMPP interne depuis la passerelle XMPP du serveur frontal ou du pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="81eed-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

