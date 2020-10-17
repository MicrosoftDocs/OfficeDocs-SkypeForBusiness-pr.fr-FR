---
title: Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques
description: Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques.
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566400"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="425cc-103">Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="425cc-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="425cc-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="425cc-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="425cc-105">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="425cc-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="425cc-106">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="425cc-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="425cc-107">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="425cc-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="425cc-108">Les informations de planification pour le proxy inverse et la Fédération sont disponibles dans [scénarios de proxy inverse dans Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) et [planification pour SIP, Fédération XMPP et messagerie instantanée publique dans les sections Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivement.</span><span class="sxs-lookup"><span data-stu-id="425cc-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="425cc-109">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="425cc-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="425cc-110">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="425cc-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="425cc-111">**Réseau de périmètre d’entreprise pour un serveur Edge consolidé unique avec adressage IP public**</span><span class="sxs-lookup"><span data-stu-id="425cc-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="425cc-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="425cc-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="425cc-113">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="425cc-113">Port and Protocol Details</span></span>

<span data-ttu-id="425cc-114">Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="425cc-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="425cc-115">Pour l’accès distant à un service Edge, il est obligatoire d’autoriser le trafic SIP à circuler dans les deux sens, comme le montre l’illustration « Trafic Edge bidirectionnel ».</span><span class="sxs-lookup"><span data-stu-id="425cc-115">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="425cc-116">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="425cc-116">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="425cc-117">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface externe</span><span class="sxs-lookup"><span data-stu-id="425cc-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425cc-118">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="425cc-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="425cc-119">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="425cc-119">Source IP address</span></span></th>
<th><span data-ttu-id="425cc-120">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="425cc-120">Destination IP address</span></span></th>
<th><span data-ttu-id="425cc-121">Notes</span><span class="sxs-lookup"><span data-stu-id="425cc-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425cc-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="425cc-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="425cc-123">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-123">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-124">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="425cc-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="425cc-125">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="425cc-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-126">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="425cc-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="425cc-127">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-128">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-128">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-129">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="425cc-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-130">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="425cc-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="425cc-131">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-132">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-132">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-133">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="425cc-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-134">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="425cc-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="425cc-135">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-136">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-136">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-137">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="425cc-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-138">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-139">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-140">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-141">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="425cc-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-142">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-143">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-143">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-144">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-145">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="425cc-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-146">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-147">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-148">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-148">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-149">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="425cc-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-150">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-151">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-151">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-152">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-153">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="425cc-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-154">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="425cc-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="425cc-155">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-156">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-156">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-157">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="425cc-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-158">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="425cc-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="425cc-159">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-160">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-160">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-161">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="425cc-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-162">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="425cc-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="425cc-163">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-163">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-164">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-165">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="425cc-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-166">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="425cc-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="425cc-167">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-167">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-168">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-169">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="425cc-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-170">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="425cc-171">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-172">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-172">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-173">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="425cc-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="425cc-174">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="425cc-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-175">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="425cc-176">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-176">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-177">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-178">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-179">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-180">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-180">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-181">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-182">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-183">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-184">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-185">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-185">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-186">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="425cc-187">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface interne</span><span class="sxs-lookup"><span data-stu-id="425cc-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425cc-188">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="425cc-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="425cc-189">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="425cc-189">Source IP address</span></span></th>
<th><span data-ttu-id="425cc-190">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="425cc-190">Destination IP address</span></span></th>
<th><span data-ttu-id="425cc-191">Comments</span><span class="sxs-lookup"><span data-stu-id="425cc-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425cc-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="425cc-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="425cc-193">Any (peut être défini en tant qu’adresse IP Standard Edition Server, Standard Edition Server ou adresse IP du pool exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="425cc-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="425cc-194">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-195">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="425cc-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-197">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="425cc-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="425cc-198">Adresse IP du serveur Edge ou pool qui contient l’interface interne</span><span class="sxs-lookup"><span data-stu-id="425cc-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-199">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-201">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-202">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="425cc-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="425cc-203">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="425cc-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="425cc-205">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="425cc-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="425cc-206">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-207">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="425cc-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="425cc-209">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="425cc-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="425cc-210">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-211">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="425cc-213">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-213">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-214">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-215">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="425cc-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-217">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-217">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-218">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-219">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="425cc-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="425cc-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="425cc-221">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="425cc-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="425cc-222">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-223">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="425cc-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="425cc-225">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-225">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-226">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-227">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="425cc-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="425cc-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="425cc-229">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-229">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-230">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-231">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="425cc-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="425cc-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="425cc-233">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-233">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-234">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="425cc-235">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="425cc-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="425cc-236">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="425cc-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425cc-237">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="425cc-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="425cc-238">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="425cc-238">Source IP address</span></span></th>
<th><span data-ttu-id="425cc-239">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="425cc-239">Destination IP address</span></span></th>
<th><span data-ttu-id="425cc-240">Notes</span><span class="sxs-lookup"><span data-stu-id="425cc-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425cc-241">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-242">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="425cc-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-243">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-243">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-244">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="425cc-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="425cc-245">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="425cc-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425cc-246">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="425cc-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="425cc-247">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="425cc-247">Source IP address</span></span></th>
<th><span data-ttu-id="425cc-248">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="425cc-248">Destination IP address</span></span></th>
<th><span data-ttu-id="425cc-249">Notes</span><span class="sxs-lookup"><span data-stu-id="425cc-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425cc-250">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-251">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="425cc-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="425cc-252">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-253">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="425cc-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-254">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="425cc-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="425cc-255">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-256">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="425cc-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="425cc-257">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="425cc-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-258">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="425cc-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="425cc-259">Clients</span><span class="sxs-lookup"><span data-stu-id="425cc-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="425cc-260">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-261">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="425cc-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-262">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="425cc-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="425cc-263">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-264">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="425cc-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="425cc-265">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="425cc-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-266">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="425cc-267">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-268">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="425cc-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="425cc-269">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="425cc-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-270">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="425cc-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="425cc-271">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="425cc-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="425cc-272">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="425cc-273">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="425cc-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="425cc-274">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="425cc-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425cc-275">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="425cc-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="425cc-276">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="425cc-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="425cc-277">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="425cc-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="425cc-278">Comments</span><span class="sxs-lookup"><span data-stu-id="425cc-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425cc-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="425cc-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="425cc-280">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-280">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-281">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-282">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="425cc-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="425cc-283">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="425cc-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425cc-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="425cc-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="425cc-285">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="425cc-286">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-286">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-287">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="425cc-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="425cc-288">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="425cc-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425cc-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="425cc-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="425cc-290">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="425cc-290">Any</span></span></p></td>
<td><p><span data-ttu-id="425cc-291">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="425cc-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="425cc-292">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="425cc-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

