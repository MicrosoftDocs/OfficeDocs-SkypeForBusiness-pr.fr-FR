---
title: Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques
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
ms.openlocfilehash: f94ac852959ca440f09f8878a17c1e23f7698bd4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="aa9e3-102">Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa9e3-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa9e3-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="aa9e3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aa9e3-104">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="aa9e3-105">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="aa9e3-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="aa9e3-106">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="aa9e3-107">Les informations de planification pour le proxy inverse et la Fédération sont disponibles dans [scénarios de proxy inverse dans Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) et [planification pour SIP, Fédération XMPP et messagerie instantanée publique dans les sections Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivement.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="aa9e3-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="aa9e3-109">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="aa9e3-110">**Réseau de périmètre d’entreprise pour un serveur Edge consolidé unique avec adressage IP public**</span><span class="sxs-lookup"><span data-stu-id="aa9e3-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="aa9e3-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="aa9e3-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="aa9e3-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="aa9e3-112">Port and Protocol Details</span></span>

<span data-ttu-id="aa9e3-113">Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="aa9e3-114">Pour l’accès distant à un service Edge, il est obligatoire d’autoriser le trafic SIP à circuler dans les deux sens, comme le montre l’illustration « Trafic Edge bidirectionnel ».</span><span class="sxs-lookup"><span data-stu-id="aa9e3-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="aa9e3-115">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="aa9e3-116">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface externe</span><span class="sxs-lookup"><span data-stu-id="aa9e3-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa9e3-117">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="aa9e3-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aa9e3-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="aa9e3-118">Source IP address</span></span></th>
<th><span data-ttu-id="aa9e3-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="aa9e3-119">Destination IP address</span></span></th>
<th><span data-ttu-id="aa9e3-120">Notes</span><span class="sxs-lookup"><span data-stu-id="aa9e3-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="aa9e3-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-122">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-122">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-123">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-124">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="aa9e3-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-125">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="aa9e3-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-126">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-127">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-127">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-128">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="aa9e3-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-129">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="aa9e3-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-130">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-131">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-132">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-133">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="aa9e3-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-134">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-135">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-135">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-136">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-137">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-138">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-139">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-140">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="aa9e3-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-141">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-142">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-142">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-143">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-144">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-145">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-146">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-147">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-147">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-148">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-149">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-150">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-150">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-151">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-152">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="aa9e3-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-153">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="aa9e3-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-154">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-155">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-155">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-156">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-157">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="aa9e3-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-158">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-159">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-159">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-160">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aa9e3-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-161">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="aa9e3-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-162">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-162">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-163">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-164">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-165">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="aa9e3-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-166">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-166">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-167">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-168">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-170">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-171">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-171">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-172">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="aa9e3-173">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-175">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-175">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-176">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-177">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-179">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-179">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-180">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-181">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-183">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-184">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-184">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-185">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="aa9e3-186">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface interne</span><span class="sxs-lookup"><span data-stu-id="aa9e3-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa9e3-187">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="aa9e3-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aa9e3-188">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="aa9e3-188">Source IP address</span></span></th>
<th><span data-ttu-id="aa9e3-189">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="aa9e3-189">Destination IP address</span></span></th>
<th><span data-ttu-id="aa9e3-190">Commentaires</span><span class="sxs-lookup"><span data-stu-id="aa9e3-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="aa9e3-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-192">Any (peut être défini en tant qu’adresse IP Standard Edition Server, Standard Edition Server ou adresse IP du pool exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-193">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-194">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="aa9e3-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-196">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-197">Adresse IP du serveur Edge ou pool qui contient l’interface interne</span><span class="sxs-lookup"><span data-stu-id="aa9e3-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-198">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-201">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-202">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="aa9e3-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-204">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-205">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-206">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="aa9e3-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-208">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-209">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-210">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-212">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-212">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-213">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-214">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="aa9e3-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-216">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-216">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-217">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-218">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="aa9e3-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-220">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-221">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-222">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="aa9e3-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-224">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-224">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-225">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-226">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="aa9e3-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-228">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-228">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-229">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-230">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="aa9e3-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-232">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-232">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-233">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-234">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="aa9e3-235">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="aa9e3-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa9e3-236">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="aa9e3-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aa9e3-237">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="aa9e3-237">Source IP address</span></span></th>
<th><span data-ttu-id="aa9e3-238">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="aa9e3-238">Destination IP address</span></span></th>
<th><span data-ttu-id="aa9e3-239">Notes</span><span class="sxs-lookup"><span data-stu-id="aa9e3-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-240">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-241">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="aa9e3-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-242">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-242">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-243">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="aa9e3-244">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="aa9e3-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa9e3-245">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="aa9e3-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aa9e3-246">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="aa9e3-246">Source IP address</span></span></th>
<th><span data-ttu-id="aa9e3-247">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="aa9e3-247">Destination IP address</span></span></th>
<th><span data-ttu-id="aa9e3-248">Notes</span><span class="sxs-lookup"><span data-stu-id="aa9e3-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-249">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-250">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="aa9e3-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-251">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-252">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-253">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="aa9e3-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-254">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-255">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="aa9e3-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-256">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-257">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="aa9e3-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-258">Clients</span><span class="sxs-lookup"><span data-stu-id="aa9e3-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-259">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-260">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="aa9e3-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-261">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="aa9e3-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-262">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-263">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="aa9e3-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-264">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-266">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-267">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="aa9e3-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-268">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="aa9e3-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="aa9e3-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="aa9e3-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-271">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-272">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="aa9e3-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="aa9e3-273">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="aa9e3-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa9e3-274">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="aa9e3-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aa9e3-275">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="aa9e3-276">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="aa9e3-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="aa9e3-277">Commentaires</span><span class="sxs-lookup"><span data-stu-id="aa9e3-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="aa9e3-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-279">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-279">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-280">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-281">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="aa9e3-282">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="aa9e3-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9e3-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="aa9e3-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-284">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-285">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-285">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-286">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="aa9e3-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="aa9e3-287">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="aa9e3-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9e3-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="aa9e3-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-289">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="aa9e3-289">Any</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-290">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="aa9e3-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="aa9e3-291">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="aa9e3-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

