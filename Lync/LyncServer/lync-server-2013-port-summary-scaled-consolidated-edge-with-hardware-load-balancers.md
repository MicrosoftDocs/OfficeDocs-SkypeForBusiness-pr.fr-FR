---
title: Résumé des ports-serveur Edge consolidé ajusté avec équilibreurs de charge matérielle
description: Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564590"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="e30dd-103">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30dd-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e30dd-104">_**Dernière modification de la rubrique :** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="e30dd-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="e30dd-105">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e30dd-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e30dd-106">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="e30dd-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e30dd-107">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="e30dd-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e30dd-108">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="e30dd-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e30dd-109">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="e30dd-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e30dd-110">**Serveur Edge consolidé ajusté à l’aide de l’équilibrage de charge matérielle**</span><span class="sxs-lookup"><span data-stu-id="e30dd-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="e30dd-111">![Protocoles et ports du réseau de périmètre du serveur Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Protocoles et ports du réseau de périmètre du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="e30dd-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e30dd-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="e30dd-112">Port and Protocol Details</span></span>

<span data-ttu-id="e30dd-113">Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="e30dd-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e30dd-114">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="e30dd-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e30dd-115">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="e30dd-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="e30dd-116">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : interface externe – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="e30dd-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30dd-117">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e30dd-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e30dd-118">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="e30dd-118">Source IP address</span></span></th>
<th><span data-ttu-id="e30dd-119">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="e30dd-119">Destination IP address</span></span></th>
<th><span data-ttu-id="e30dd-120">Notes</span><span class="sxs-lookup"><span data-stu-id="e30dd-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-121">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e30dd-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e30dd-122">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-123">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-123">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-124">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="e30dd-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-125">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e30dd-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e30dd-126">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-127">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-128">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="e30dd-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-129">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e30dd-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e30dd-130">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-131">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-132">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="e30dd-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-133">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="e30dd-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e30dd-134">Adresse IP du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-135">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-135">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-136">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e30dd-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-137">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="e30dd-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e30dd-138">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-140">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e30dd-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-141">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="e30dd-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e30dd-142">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-142">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-143">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-144">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e30dd-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-145">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="e30dd-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e30dd-146">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-146">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-147">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-148">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e30dd-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-149">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e30dd-150">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-151">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-151">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-152">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e30dd-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e30dd-153">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="e30dd-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-154">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e30dd-155">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-155">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-156">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-157">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-158">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-159">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-159">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-160">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-161">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-162">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-163">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-164">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-165">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="e30dd-166">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : nœud d’interface interne 1 et nœud 2</span><span class="sxs-lookup"><span data-stu-id="e30dd-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30dd-167">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e30dd-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e30dd-168">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="e30dd-168">Source IP address</span></span></th>
<th><span data-ttu-id="e30dd-169">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="e30dd-169">Destination IP address</span></span></th>
<th><span data-ttu-id="e30dd-170">Notes</span><span class="sxs-lookup"><span data-stu-id="e30dd-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e30dd-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e30dd-172">Any (peut être défini en tant qu’adresse de serveur frontal ou adresse IP virtuelle du pool frontal exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="e30dd-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-173">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-174">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="e30dd-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e30dd-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-176">Any (peut être défini comme le pool ou l’adresse IP du serveur frontal qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="e30dd-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-177">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-178">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e30dd-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e30dd-180">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="e30dd-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-181">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-182">Trafic de conférence Web depuis le déploiement interne vers l’interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="e30dd-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e30dd-184">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="e30dd-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-185">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-186">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e30dd-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-188">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="e30dd-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-189">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-190">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="e30dd-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e30dd-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e30dd-192">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-192">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-193">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-194">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="e30dd-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e30dd-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e30dd-196">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-196">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-197">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-198">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="e30dd-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e30dd-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e30dd-200">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-200">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-201">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-202">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="e30dd-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e30dd-203">Les programmes d’équilibrage de la charge matérielle ont des exigences spécifiques lorsqu’ils sont déployés pour assurer la disponibilité et l’équilibrage de la charge pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e30dd-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="e30dd-204">Les conditions requises sont définies dans les tableaux et les figures suivants.</span><span class="sxs-lookup"><span data-stu-id="e30dd-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="e30dd-205">Les fournisseurs tiers peuvent utiliser une terminologie différente pour les exigences définies ici.</span><span class="sxs-lookup"><span data-stu-id="e30dd-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="e30dd-206">Il sera nécessaire de mapper les exigences de Lync Server aux options de configuration et aux fonctionnalités fournies par votre fournisseur d’équilibreur de charge matériel.</span><span class="sxs-lookup"><span data-stu-id="e30dd-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="e30dd-207">Lors de la configuration des programmes d’équilibrage de la charge matérielle, tenez compte des exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="e30dd-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="e30dd-208">La traduction d’adresses réseau source (SNAT) peut être configurée sur le programme d’équilibrage de la charge matérielle (charge matérielle) pour le service Edge d’accès et le service Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="e30dd-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="e30dd-209">SNAT ne peut pas être configuré sur le service Edge A/V : le service Edge A/V doit répondre avec l’adresse de serveur réelle, et non avec l’adresse IP virtuelle charge matérielle, pour une simple traversée des/Traversal UDP sur NAT (STUN) à l’aide de l’interface NAT relais (TURN)/Federation TURN (FTURN) pour fonctionner correctement</span><span class="sxs-lookup"><span data-stu-id="e30dd-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="e30dd-210">Si le client envoie une demande au charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle</span><span class="sxs-lookup"><span data-stu-id="e30dd-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e30dd-211">Si le client envoie une demande au serveur Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e30dd-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e30dd-212">Les adresses IP publiques sont utilisées sur chaque interface de serveur et sur les VIP du charge matérielle, et les exigences de votre adresse IP publique sont N + 1, où il y a une adresse IP publique pour chaque interface de serveur réel et une pour chaque VIP charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="e30dd-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="e30dd-213">Lorsque vous avez 2 serveurs Edge dans le pool, il en résulte 9 adresses IP publiques, où 3 sont utilisées pour les VIP charge matérielle et une pour chaque interface de serveur Edge (un total de six pour les serveurs)</span><span class="sxs-lookup"><span data-stu-id="e30dd-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="e30dd-214">Pour le service Edge d’accès et le service Edge de conférence Web (et l’utilisation de la fonctionnalité NAT sur le charge matérielle), le client contacte l’adresse IP virtuelle, l’adresse IP virtuelle modifie l’adresse IP source du client vers sa propre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="e30dd-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="e30dd-215">L’interface serveur adresse l’adresse de retour au VIP, l’adresse IP virtuelle modifie l’adresse source à partir de l’adresse IP de l’interface du serveur et envoie le paquet au client.</span><span class="sxs-lookup"><span data-stu-id="e30dd-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="e30dd-216">Pour le service Edge A/V, l’adresse IP virtuelle ne doit pas modifier l’adresse IP source et l’adresse du serveur réel est directement renvoyée au client : vous ne pouvez pas configurer la traduction d’adresses réseau (NAT) sur le charge matérielle pour le trafic AV</span><span class="sxs-lookup"><span data-stu-id="e30dd-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="e30dd-217">Si le client envoie une demande au VIP charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle</span><span class="sxs-lookup"><span data-stu-id="e30dd-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e30dd-218">Si le client envoie une demande à l’adresse IP Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e30dd-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e30dd-219">Pour les AV, le pare-feu externe conservera l’adresse IP publique réelle du serveur pour tous les paquets.</span><span class="sxs-lookup"><span data-stu-id="e30dd-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="e30dd-220">Une fois la communication de service Edge A/V établie, le client vers le serveur réel et non le charge matérielle</span><span class="sxs-lookup"><span data-stu-id="e30dd-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="e30dd-221">Le périmètre interne vers les serveurs internes et les clients doit être routé, et les itinéraires persistants sont définis pour tous les réseaux internes hébergeant des serveurs ou des clients.</span><span class="sxs-lookup"><span data-stu-id="e30dd-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="e30dd-222">Le VIP du service Edge d’accès charge matérielle agira comme passerelle par défaut pour chaque interface de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e30dd-223">Pour plus d’informations sur la planification et les fonctionnalités de NAT, reportez-vous à la rubrique <A href="lync-server-2013-hardware-load-balancer-requirements.md">Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e30dd-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e30dd-224">![Détails des protocoles et ports du serveur Edge](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails des protocoles et ports du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="e30dd-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="e30dd-225">Paramètres de ports externes requis pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles d’interface externe</span><span class="sxs-lookup"><span data-stu-id="e30dd-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30dd-226">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e30dd-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e30dd-227">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="e30dd-227">Source IP address</span></span></th>
<th><span data-ttu-id="e30dd-228">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="e30dd-228">Destination IP address</span></span></th>
<th><span data-ttu-id="e30dd-229">Notes</span><span class="sxs-lookup"><span data-stu-id="e30dd-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e30dd-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e30dd-231">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-231">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-232">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="e30dd-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-233">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="e30dd-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e30dd-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e30dd-235">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="e30dd-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-236">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-236">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-237">Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="e30dd-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-238">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-239">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-239">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-240">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="e30dd-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-241">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="e30dd-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-242">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e30dd-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e30dd-243">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-243">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-244">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="e30dd-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-245">Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</span><span class="sxs-lookup"><span data-stu-id="e30dd-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-246">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e30dd-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e30dd-247">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="e30dd-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-248">Partenaire fédéré</span><span class="sxs-lookup"><span data-stu-id="e30dd-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="e30dd-249">Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</span><span class="sxs-lookup"><span data-stu-id="e30dd-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-250">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-251">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-251">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-252">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-253">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="e30dd-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-254">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e30dd-255">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-255">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-256">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-257">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-258">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-259">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-259">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-260">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e30dd-261">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="e30dd-262">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles de l’interface interne</span><span class="sxs-lookup"><span data-stu-id="e30dd-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30dd-263">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e30dd-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e30dd-264">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="e30dd-264">Source IP address</span></span></th>
<th><span data-ttu-id="e30dd-265">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="e30dd-265">Destination IP address</span></span></th>
<th><span data-ttu-id="e30dd-266">Notes</span><span class="sxs-lookup"><span data-stu-id="e30dd-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-267">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e30dd-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e30dd-268">Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="e30dd-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-269">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-270">Trafic SIP sortant (depuis le directeur, l’adresse IP virtuelle du pool Directeur, le serveur frontal ou l’adresse IP virtuelle du pool frontal) vers le protocole VIP interne</span><span class="sxs-lookup"><span data-stu-id="e30dd-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-271">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e30dd-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e30dd-272">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-273">Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="e30dd-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-274">Trafic SIP entrant (vers le directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e30dd-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e30dd-276">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="e30dd-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e30dd-277">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-278">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e30dd-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e30dd-280">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-280">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-281">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-282">Chemin d’accès préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes</span><span class="sxs-lookup"><span data-stu-id="e30dd-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30dd-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-284">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-284">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-285">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-286">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="e30dd-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30dd-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e30dd-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e30dd-288">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e30dd-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e30dd-289">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="e30dd-289">Any</span></span></p></td>
<td><p><span data-ttu-id="e30dd-290">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="e30dd-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

