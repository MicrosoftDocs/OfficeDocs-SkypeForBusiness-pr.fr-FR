---
title: 'Lync Server 2013 : Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2bbae2168362e8591b4dcdb765ae0d4cca85b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="9817b-102">Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9817b-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9817b-103">_**Dernière modification de la rubrique :** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="9817b-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="9817b-104">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9817b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9817b-105">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="9817b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9817b-106">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9817b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9817b-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="9817b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9817b-108">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="9817b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9817b-109">**Réseau de périmètre d’entreprise pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques**</span><span class="sxs-lookup"><span data-stu-id="9817b-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="9817b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="9817b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9817b-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="9817b-111">Port and Protocol Details</span></span>

<span data-ttu-id="9817b-112">Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="9817b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9817b-113">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="9817b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="9817b-114">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="9817b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="9817b-115">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques : interface externe – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="9817b-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9817b-116">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="9817b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9817b-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="9817b-117">Source IP address</span></span></th>
<th><span data-ttu-id="9817b-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="9817b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="9817b-119">Notes</span><span class="sxs-lookup"><span data-stu-id="9817b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9817b-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9817b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9817b-121">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-122">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="9817b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9817b-123">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="9817b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-124">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9817b-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9817b-125">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-126">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-127">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="9817b-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-128">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9817b-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9817b-129">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-130">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-131">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="9817b-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-132">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9817b-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9817b-133">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-135">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="9817b-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-136">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-137">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-137">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-138">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-139">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="9817b-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-140">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-141">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-142">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-143">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="9817b-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-144">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-145">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-146">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-146">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-147">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="9817b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-148">Conférence Web/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-149">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-150">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-151">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="9817b-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-152">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="9817b-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9817b-153">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-154">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-155">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9817b-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-156">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="9817b-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9817b-157">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-158">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-159">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9817b-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-160">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="9817b-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9817b-161">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-162">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-163">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9817b-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-164">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="9817b-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9817b-165">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-166">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-167">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9817b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9817b-169">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-170">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-171">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="9817b-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9817b-172">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="9817b-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9817b-174">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-175">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-176">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-178">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-179">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-180">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-182">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-183">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-183">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-184">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="9817b-185">Résumé du pare-feu pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques : interface interne – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="9817b-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9817b-186">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="9817b-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9817b-187">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="9817b-187">Source IP address</span></span></th>
<th><span data-ttu-id="9817b-188">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="9817b-188">Destination IP address</span></span></th>
<th><span data-ttu-id="9817b-189">Commentaires</span><span class="sxs-lookup"><span data-stu-id="9817b-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9817b-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9817b-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9817b-191">Any (peut être défini comme adresse de serveur frontal ou adresse IP de pool frontal exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="9817b-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9817b-192">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-193">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="9817b-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-195">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="9817b-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9817b-196">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-197">Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-199">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-200">Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="9817b-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9817b-201">Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9817b-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9817b-203">Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="9817b-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9817b-204">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-205">Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9817b-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9817b-207">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="9817b-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9817b-208">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-209">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9817b-211">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-211">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-212">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-213">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9817b-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-215">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-216">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-217">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="9817b-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9817b-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9817b-219">Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="9817b-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9817b-220">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-221">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9817b-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9817b-223">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-223">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-224">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-225">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="9817b-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9817b-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9817b-227">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-228">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-229">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="9817b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9817b-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9817b-231">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-232">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9817b-233">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="9817b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9817b-234">Résumé du pare-feu pour la fédération</span><span class="sxs-lookup"><span data-stu-id="9817b-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9817b-235">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="9817b-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9817b-236">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="9817b-236">Source IP address</span></span></th>
<th><span data-ttu-id="9817b-237">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="9817b-237">Destination IP address</span></span></th>
<th><span data-ttu-id="9817b-238">Notes</span><span class="sxs-lookup"><span data-stu-id="9817b-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9817b-239">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-240">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="9817b-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-241">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-241">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-242">Pour la connectivité fédérée et PIC utilisant SIP</span><span class="sxs-lookup"><span data-stu-id="9817b-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9817b-243">Résumé du pare-feu : connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="9817b-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9817b-244">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="9817b-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9817b-245">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="9817b-245">Source IP address</span></span></th>
<th><span data-ttu-id="9817b-246">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="9817b-246">Destination IP address</span></span></th>
<th><span data-ttu-id="9817b-247">Notes</span><span class="sxs-lookup"><span data-stu-id="9817b-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9817b-248">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-249">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="9817b-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9817b-250">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-251">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="9817b-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-252">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9817b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9817b-253">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-254">Partenaires de connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="9817b-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9817b-255">Pour la connectivité fédérée et PIC avec SIP</span><span class="sxs-lookup"><span data-stu-id="9817b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-256">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9817b-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9817b-257">Clients</span><span class="sxs-lookup"><span data-stu-id="9817b-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="9817b-258">Service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-259">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="9817b-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-260">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="9817b-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9817b-261">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-262">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9817b-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9817b-263">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</span><span class="sxs-lookup"><span data-stu-id="9817b-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9817b-265">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-266">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9817b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9817b-267">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9817b-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9817b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9817b-269">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9817b-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9817b-270">Service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9817b-271">Requis pour la connectivité PIC avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9817b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9817b-272">Résumé du pare-feu pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="9817b-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9817b-273">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="9817b-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9817b-274">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="9817b-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="9817b-275">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="9817b-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9817b-276">Commentaires</span><span class="sxs-lookup"><span data-stu-id="9817b-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9817b-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9817b-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9817b-278">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-278">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-279">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-280">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="9817b-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9817b-281">Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="9817b-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9817b-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9817b-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9817b-283">Adresse IP de l’interface du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9817b-284">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-284">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-285">Port de communication de serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="9817b-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9817b-286">Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="9817b-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9817b-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9817b-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9817b-288">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="9817b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="9817b-289">Adresse IP de chaque interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="9817b-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="9817b-290">Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</span><span class="sxs-lookup"><span data-stu-id="9817b-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

