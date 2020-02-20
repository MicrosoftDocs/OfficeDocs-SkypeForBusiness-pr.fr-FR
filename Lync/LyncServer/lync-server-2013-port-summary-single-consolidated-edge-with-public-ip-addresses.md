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
ms.openlocfilehash: 2c307ff7318a426610cf371a3d6f55591a7c6ed0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b468e-102">Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b468e-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b468e-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b468e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b468e-104">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b468e-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b468e-105">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="b468e-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b468e-106">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b468e-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b468e-107">Les informations de planification pour le proxy inverse et la Fédération sont disponibles dans [scénarios de proxy inverse dans Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) et [planification pour SIP, Fédération XMPP et messagerie instantanée publique dans les sections Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivement.</span><span class="sxs-lookup"><span data-stu-id="b468e-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="b468e-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="b468e-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b468e-109">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="b468e-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b468e-110">**Réseau de périmètre d’entreprise pour un serveur Edge consolidé unique avec adressage IP public**</span><span class="sxs-lookup"><span data-stu-id="b468e-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="b468e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="b468e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b468e-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="b468e-112">Port and Protocol Details</span></span>

<span data-ttu-id="b468e-113">Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="b468e-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b468e-114">Pour l’accès distant à un service Edge, il est obligatoire d’autoriser le trafic SIP à circuler dans les deux sens, comme le montre l’illustration « Trafic Edge bidirectionnel ».</span><span class="sxs-lookup"><span data-stu-id="b468e-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="b468e-115">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="b468e-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="b468e-116">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface externe</span><span class="sxs-lookup"><span data-stu-id="b468e-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b468e-117">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b468e-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b468e-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b468e-118">Source IP address</span></span></th>
<th><span data-ttu-id="b468e-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b468e-119">Destination IP address</span></span></th>
<th><span data-ttu-id="b468e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b468e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b468e-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b468e-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b468e-122">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-122">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-123">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="b468e-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b468e-124">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="b468e-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-125">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b468e-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b468e-126">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-127">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-127">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-128">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="b468e-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-129">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b468e-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b468e-130">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-131">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-132">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="b468e-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-133">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b468e-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b468e-134">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-135">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-135">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-136">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="b468e-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-137">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-138">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-139">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-140">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="b468e-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-141">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-142">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-142">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-143">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-144">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="b468e-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-145">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-146">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-147">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-147">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-148">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="b468e-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-149">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-150">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-150">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-151">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-152">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="b468e-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-153">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b468e-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b468e-154">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-155">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-155">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-156">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b468e-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-157">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b468e-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b468e-158">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-159">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-160">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="b468e-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-161">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b468e-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b468e-162">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-162">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-163">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-164">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b468e-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-165">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b468e-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b468e-166">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-166">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-167">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-168">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b468e-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b468e-170">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-171">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-171">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-172">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b468e-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b468e-173">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="b468e-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b468e-175">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-175">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-176">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-177">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-179">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-179">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-180">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-181">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-183">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-184">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-184">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-185">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="b468e-186">Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface interne</span><span class="sxs-lookup"><span data-stu-id="b468e-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b468e-187">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b468e-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b468e-188">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b468e-188">Source IP address</span></span></th>
<th><span data-ttu-id="b468e-189">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b468e-189">Destination IP address</span></span></th>
<th><span data-ttu-id="b468e-190">Commentaires</span><span class="sxs-lookup"><span data-stu-id="b468e-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b468e-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b468e-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b468e-192">Any (peut être défini en tant qu’adresse IP Standard Edition Server, Standard Edition Server ou adresse IP du pool exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="b468e-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b468e-193">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-194">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="b468e-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-196">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="b468e-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b468e-197">Adresse IP du serveur Edge ou pool qui contient l’interface interne</span><span class="sxs-lookup"><span data-stu-id="b468e-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-198">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-201">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="b468e-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="b468e-202">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b468e-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b468e-204">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="b468e-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b468e-205">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-206">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b468e-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b468e-208">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="b468e-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b468e-209">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-210">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b468e-212">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-212">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-213">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-214">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b468e-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-216">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-216">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-217">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-218">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="b468e-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b468e-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b468e-220">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="b468e-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b468e-221">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-222">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b468e-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b468e-224">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-224">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-225">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-226">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="b468e-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b468e-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b468e-228">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-228">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-229">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-230">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="b468e-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b468e-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b468e-232">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-232">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-233">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b468e-234">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="b468e-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b468e-235">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="b468e-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b468e-236">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b468e-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b468e-237">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b468e-237">Source IP address</span></span></th>
<th><span data-ttu-id="b468e-238">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b468e-238">Destination IP address</span></span></th>
<th><span data-ttu-id="b468e-239">Notes</span><span class="sxs-lookup"><span data-stu-id="b468e-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b468e-240">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-241">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="b468e-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-242">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-242">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-243">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="b468e-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b468e-244">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="b468e-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b468e-245">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b468e-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b468e-246">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b468e-246">Source IP address</span></span></th>
<th><span data-ttu-id="b468e-247">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b468e-247">Destination IP address</span></span></th>
<th><span data-ttu-id="b468e-248">Notes</span><span class="sxs-lookup"><span data-stu-id="b468e-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b468e-249">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-250">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="b468e-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b468e-251">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-252">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="b468e-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-253">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b468e-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b468e-254">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-255">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="b468e-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b468e-256">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="b468e-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-257">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b468e-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b468e-258">Clients</span><span class="sxs-lookup"><span data-stu-id="b468e-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="b468e-259">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-260">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="b468e-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-261">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="b468e-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b468e-262">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-263">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b468e-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b468e-264">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="b468e-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b468e-266">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-267">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b468e-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b468e-268">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b468e-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b468e-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b468e-270">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b468e-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b468e-271">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b468e-272">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b468e-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b468e-273">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="b468e-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b468e-274">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b468e-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b468e-275">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="b468e-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="b468e-276">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="b468e-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b468e-277">Commentaires</span><span class="sxs-lookup"><span data-stu-id="b468e-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b468e-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b468e-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b468e-279">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-279">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-280">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-281">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="b468e-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b468e-282">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="b468e-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b468e-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b468e-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b468e-284">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b468e-285">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-285">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-286">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="b468e-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b468e-287">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="b468e-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b468e-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b468e-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b468e-289">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b468e-289">Any</span></span></p></td>
<td><p><span data-ttu-id="b468e-290">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="b468e-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="b468e-291">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="b468e-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

