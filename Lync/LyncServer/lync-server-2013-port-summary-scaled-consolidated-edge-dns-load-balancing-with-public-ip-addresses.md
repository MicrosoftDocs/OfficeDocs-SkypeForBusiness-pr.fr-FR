---
title: 'Lync Server 2013 : Résumé des ports - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques'
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
ms.openlocfilehash: f67a12b05d8724d31f8ef83bfa4aa704b41cee13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="08087-102">Résumé des ports - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08087-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08087-103">_**Dernière modification de la rubrique :** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="08087-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="08087-104">La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="08087-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="08087-105">Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="08087-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="08087-106">Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="08087-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="08087-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="08087-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="08087-108">Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="08087-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="08087-109">**Réseau de périmètre d’entreprise pour l’équilibrage de charge DNS à l’échelle**</span><span class="sxs-lookup"><span data-stu-id="08087-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="08087-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="08087-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="08087-111">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="08087-111">Port and Protocol Details</span></span>

<span data-ttu-id="08087-112">Il est recommandé d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="08087-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="08087-113">Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="08087-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="08087-114">Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans les fonctionnalités de messagerie instantanée, de présence, de conférence Web, audio/vidéo (A/V) et de Fédération.</span><span class="sxs-lookup"><span data-stu-id="08087-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="08087-115">Résumé du pare-feu pour le bord consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP publiques : interface externe-nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="08087-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08087-116">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08087-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08087-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="08087-117">Source IP address</span></span></th>
<th><span data-ttu-id="08087-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="08087-118">Destination IP address</span></span></th>
<th><span data-ttu-id="08087-119">Remarques</span><span class="sxs-lookup"><span data-stu-id="08087-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08087-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08087-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08087-121">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-121">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-122">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="08087-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="08087-123">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</span><span class="sxs-lookup"><span data-stu-id="08087-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-124">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="08087-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="08087-125">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-126">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-126">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-127">Vérification et récupération des certificats</span><span class="sxs-lookup"><span data-stu-id="08087-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="08087-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="08087-129">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-130">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-130">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-131">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="08087-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="08087-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="08087-133">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-134">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-135">Requête DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="08087-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-136">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="08087-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-137">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-137">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-138">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-139">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="08087-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-140">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="08087-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-141">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-142">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-143">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="08087-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-144">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="08087-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-145">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-146">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-146">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-147">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="08087-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-148">PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-149">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-149">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-150">Adresse IP publique du service Edge Conferencing Server Web</span><span class="sxs-lookup"><span data-stu-id="08087-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-151">Support de conférences Web</span><span class="sxs-lookup"><span data-stu-id="08087-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-152">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="08087-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08087-153">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-154">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-155">Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08087-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-156">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="08087-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08087-157">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-158">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-158">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-159">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="08087-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-160">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="08087-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08087-161">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-161">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-162">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-163">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="08087-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-164">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="08087-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08087-165">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-165">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-166">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-167">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="08087-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08087-169">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-170">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-170">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-171">3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie.</span><span class="sxs-lookup"><span data-stu-id="08087-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="08087-172">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="08087-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08087-174">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-174">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-175">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-176">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-178">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-178">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-179">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="08087-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-180">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-182">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="08087-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-183">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-183">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-184">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="08087-185">Résumé du pare-feu pour les bords consolidés mis à l’échelle, équilibrage de charge DNS avec adresses IP publiques : interface interne – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="08087-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08087-186">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08087-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08087-187">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="08087-187">Source IP address</span></span></th>
<th><span data-ttu-id="08087-188">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="08087-188">Destination IP address</span></span></th>
<th><span data-ttu-id="08087-189">Commentaires</span><span class="sxs-lookup"><span data-stu-id="08087-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08087-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="08087-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="08087-191">Tout (peut être défini comme adresse serveur frontale ou adresse IP de pool frontal exécutant le service passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="08087-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="08087-192">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-193">Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="08087-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08087-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-195">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="08087-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="08087-196">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-197">Trafic SIP sortant (à partir du réalisateur, adresse IP du pool de réalisateurs, adresse IP du serveur frontal ou de la liste frontale) vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08087-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-199">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-200">Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="08087-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="08087-201">Trafic SIP entrant (adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="08087-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="08087-203">Tout (peut être défini comme adresse IP du serveur frontal ou chaque adresse IP du serveur frontal dans un pool frontal)</span><span class="sxs-lookup"><span data-stu-id="08087-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="08087-204">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-205">Trafic de conférences Web à partir du serveur frontal ou de chaque serveur frontal, s’il se trouve dans un pool, vers l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="08087-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="08087-207">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="08087-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="08087-208">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-209">L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08087-211">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-211">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-212">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-213">Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="08087-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08087-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-215">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-215">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-216">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-217">Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="08087-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="08087-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="08087-219">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou pool contenant la Banque centrale de gestion).</span><span class="sxs-lookup"><span data-stu-id="08087-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="08087-220">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-221">Réplication des modifications du magasin de gestion central vers le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="08087-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="08087-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="08087-223">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-223">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-224">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-225">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="08087-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="08087-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="08087-227">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-227">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-228">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-229">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="08087-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="08087-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="08087-231">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-231">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-232">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="08087-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08087-233">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="08087-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="08087-234">Résumé du pare-feu pour la Fédération</span><span class="sxs-lookup"><span data-stu-id="08087-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08087-235">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08087-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08087-236">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="08087-236">Source IP address</span></span></th>
<th><span data-ttu-id="08087-237">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="08087-237">Destination IP address</span></span></th>
<th><span data-ttu-id="08087-238">Remarques</span><span class="sxs-lookup"><span data-stu-id="08087-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08087-239">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="08087-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-240">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="08087-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-241">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-241">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-242">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="08087-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="08087-243">Résumé du pare-feu-connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="08087-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08087-244">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08087-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08087-245">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="08087-245">Source IP address</span></span></th>
<th><span data-ttu-id="08087-246">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="08087-246">Destination IP address</span></span></th>
<th><span data-ttu-id="08087-247">Remarques</span><span class="sxs-lookup"><span data-stu-id="08087-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08087-248">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="08087-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-249">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="08087-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="08087-250">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-251">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="08087-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-252">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="08087-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08087-253">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-254">Partenaires de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="08087-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="08087-255">Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="08087-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-256">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="08087-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08087-257">Clients</span><span class="sxs-lookup"><span data-stu-id="08087-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="08087-258">Service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-259">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="08087-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-260">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="08087-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08087-261">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="08087-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-262">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08087-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08087-263">Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</span><span class="sxs-lookup"><span data-stu-id="08087-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08087-265">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="08087-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-266">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08087-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08087-267">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08087-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08087-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08087-269">Clients Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08087-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08087-270">Service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="08087-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08087-271">Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08087-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="08087-272">Résumé du pare-feu pour le protocole extensible de messagerie et de présence</span><span class="sxs-lookup"><span data-stu-id="08087-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08087-273">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08087-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08087-274">Source (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="08087-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="08087-275">Destination (adresse IP)</span><span class="sxs-lookup"><span data-stu-id="08087-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="08087-276">Commentaires</span><span class="sxs-lookup"><span data-stu-id="08087-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08087-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08087-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08087-278">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-278">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-279">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-280">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="08087-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="08087-281">Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="08087-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08087-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08087-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08087-283">Adresse IP de l’interface du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="08087-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="08087-284">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-284">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-285">Port de communication serveur à serveur standard pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="08087-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="08087-286">Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</span><span class="sxs-lookup"><span data-stu-id="08087-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08087-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="08087-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="08087-288">Indifférente</span><span class="sxs-lookup"><span data-stu-id="08087-288">Any</span></span></p></td>
<td><p><span data-ttu-id="08087-289">Chaque adresse IP de l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="08087-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="08087-290">Trafic de XMPP interne depuis la passerelle XMPP du serveur frontal ou du pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="08087-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

