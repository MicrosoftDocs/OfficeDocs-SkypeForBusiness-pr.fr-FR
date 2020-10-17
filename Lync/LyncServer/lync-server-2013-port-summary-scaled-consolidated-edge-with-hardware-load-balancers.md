---
title: Résumé des ports-serveur Edge consolidé ajusté avec équilibreurs de charge matérielle
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
ms.openlocfilehash: dc4a56edb79d2eff52bf0d234aedcee1b3cdced4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534111"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="73d44-102">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73d44-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d44-103">_**Dernière modification de la rubrique :** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="73d44-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="73d44-104">La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="73d44-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="73d44-105">L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="73d44-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="73d44-106">Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="73d44-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="73d44-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="73d44-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="73d44-108">Par souci de clarté, seul IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="73d44-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="73d44-109">**Serveur Edge consolidé ajusté à l’aide de l’équilibrage de charge matérielle**</span><span class="sxs-lookup"><span data-stu-id="73d44-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="73d44-110">![Protocoles et ports du réseau de périmètre du serveur Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Protocoles et ports du réseau de périmètre du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="73d44-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="73d44-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="73d44-111">Port and Protocol Details</span></span>

<span data-ttu-id="73d44-112">Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="73d44-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="73d44-113">Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="73d44-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="73d44-114">Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.</span><span class="sxs-lookup"><span data-stu-id="73d44-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="73d44-115">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : interface externe – nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="73d44-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73d44-116">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="73d44-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73d44-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="73d44-117">Source IP address</span></span></th>
<th><span data-ttu-id="73d44-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="73d44-118">Destination IP address</span></span></th>
<th><span data-ttu-id="73d44-119">Notes</span><span class="sxs-lookup"><span data-stu-id="73d44-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73d44-120">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="73d44-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="73d44-121">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-122">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-122">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-123">Vérification et extraction de la liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="73d44-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-124">Accès/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="73d44-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="73d44-125">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-126">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-126">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-127">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="73d44-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-128">Accès/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="73d44-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="73d44-129">Adresse IP publique du service Edge d’accès au serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-130">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-130">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-131">Requête DNS sur UDP</span><span class="sxs-lookup"><span data-stu-id="73d44-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-132">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="73d44-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73d44-133">Adresse IP du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-134">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-134">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-135">Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73d44-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-136">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="73d44-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73d44-137">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-138">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-138">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-139">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="73d44-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-140">A/V/RTP/TCP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="73d44-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73d44-141">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-141">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-142">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-143">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="73d44-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-144">A/V/RTP/UDP/50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="73d44-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73d44-145">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-145">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-146">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-147">Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="73d44-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73d44-149">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-150">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-150">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-151">3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="73d44-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="73d44-152">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="73d44-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73d44-154">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-154">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-155">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-156">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-158">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-158">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-159">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-160">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-162">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-163">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-163">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-164">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="73d44-165">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : nœud d’interface interne 1 et nœud 2</span><span class="sxs-lookup"><span data-stu-id="73d44-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73d44-166">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="73d44-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73d44-167">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="73d44-167">Source IP address</span></span></th>
<th><span data-ttu-id="73d44-168">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="73d44-168">Destination IP address</span></span></th>
<th><span data-ttu-id="73d44-169">Notes</span><span class="sxs-lookup"><span data-stu-id="73d44-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73d44-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="73d44-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="73d44-171">Any (peut être défini en tant qu’adresse de serveur frontal ou adresse IP virtuelle du pool frontal exécutant le service de passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="73d44-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="73d44-172">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-173">Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</span><span class="sxs-lookup"><span data-stu-id="73d44-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="73d44-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="73d44-175">Any (peut être défini comme le pool ou l’adresse IP du serveur frontal qui contient le magasin central de gestion)</span><span class="sxs-lookup"><span data-stu-id="73d44-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="73d44-176">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-177">Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="73d44-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="73d44-179">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="73d44-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="73d44-180">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-181">Trafic de conférence Web depuis le déploiement interne vers l’interface de serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="73d44-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73d44-183">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="73d44-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="73d44-184">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-185">Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="73d44-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-187">Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="73d44-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="73d44-188">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-189">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="73d44-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="73d44-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="73d44-191">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-191">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-192">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-193">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="73d44-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="73d44-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="73d44-195">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-195">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-196">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-197">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="73d44-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="73d44-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="73d44-199">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-199">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-201">Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des cmdlets du service de journalisation centralisée, de la ligne de commande ClsController (ClsController.exe) ou des commandes de l’agent (ClsAgent.exe) et de la collection de journaux</span><span class="sxs-lookup"><span data-stu-id="73d44-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="73d44-202">Les programmes d’équilibrage de la charge matérielle ont des exigences spécifiques lorsqu’ils sont déployés pour assurer la disponibilité et l’équilibrage de la charge pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73d44-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="73d44-203">Les conditions requises sont définies dans les tableaux et les figures suivants.</span><span class="sxs-lookup"><span data-stu-id="73d44-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="73d44-204">Les fournisseurs tiers peuvent utiliser une terminologie différente pour les exigences définies ici.</span><span class="sxs-lookup"><span data-stu-id="73d44-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="73d44-205">Il sera nécessaire de mapper les exigences de Lync Server aux options de configuration et aux fonctionnalités fournies par votre fournisseur d’équilibreur de charge matériel.</span><span class="sxs-lookup"><span data-stu-id="73d44-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="73d44-206">Lors de la configuration des programmes d’équilibrage de la charge matérielle, tenez compte des exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="73d44-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="73d44-207">La traduction d’adresses réseau source (SNAT) peut être configurée sur le programme d’équilibrage de la charge matérielle (charge matérielle) pour le service Edge d’accès et le service Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="73d44-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="73d44-208">SNAT ne peut pas être configuré sur le service Edge A/V : le service Edge A/V doit répondre avec l’adresse de serveur réelle, et non avec l’adresse IP virtuelle charge matérielle, pour une simple traversée des/Traversal UDP sur NAT (STUN) à l’aide de l’interface NAT relais (TURN)/Federation TURN (FTURN) pour fonctionner correctement</span><span class="sxs-lookup"><span data-stu-id="73d44-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="73d44-209">Si le client envoie une demande au charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle</span><span class="sxs-lookup"><span data-stu-id="73d44-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="73d44-210">Si le client envoie une demande au serveur Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="73d44-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="73d44-211">Les adresses IP publiques sont utilisées sur chaque interface de serveur et sur les VIP du charge matérielle, et les exigences de votre adresse IP publique sont N + 1, où il y a une adresse IP publique pour chaque interface de serveur réel et une pour chaque VIP charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="73d44-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="73d44-212">Lorsque vous avez 2 serveurs Edge dans le pool, il en résulte 9 adresses IP publiques, où 3 sont utilisées pour les VIP charge matérielle et une pour chaque interface de serveur Edge (un total de six pour les serveurs)</span><span class="sxs-lookup"><span data-stu-id="73d44-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="73d44-213">Pour le service Edge d’accès et le service Edge de conférence Web (et l’utilisation de la fonctionnalité NAT sur le charge matérielle), le client contacte l’adresse IP virtuelle, l’adresse IP virtuelle modifie l’adresse IP source du client vers sa propre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="73d44-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="73d44-214">L’interface serveur adresse l’adresse de retour au VIP, l’adresse IP virtuelle modifie l’adresse source à partir de l’adresse IP de l’interface du serveur et envoie le paquet au client.</span><span class="sxs-lookup"><span data-stu-id="73d44-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="73d44-215">Pour le service Edge A/V, l’adresse IP virtuelle ne doit pas modifier l’adresse IP source et l’adresse du serveur réel est directement renvoyée au client : vous ne pouvez pas configurer la traduction d’adresses réseau (NAT) sur le charge matérielle pour le trafic AV</span><span class="sxs-lookup"><span data-stu-id="73d44-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="73d44-216">Si le client envoie une demande au VIP charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle</span><span class="sxs-lookup"><span data-stu-id="73d44-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="73d44-217">Si le client envoie une demande à l’adresse IP Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="73d44-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="73d44-218">Pour les AV, le pare-feu externe conservera l’adresse IP publique réelle du serveur pour tous les paquets.</span><span class="sxs-lookup"><span data-stu-id="73d44-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="73d44-219">Une fois la communication de service Edge A/V établie, le client vers le serveur réel et non le charge matérielle</span><span class="sxs-lookup"><span data-stu-id="73d44-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="73d44-220">Le périmètre interne vers les serveurs internes et les clients doit être routé, et les itinéraires persistants sont définis pour tous les réseaux internes hébergeant des serveurs ou des clients.</span><span class="sxs-lookup"><span data-stu-id="73d44-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="73d44-221">Le VIP du service Edge d’accès charge matérielle agira comme passerelle par défaut pour chaque interface de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="73d44-222">Pour plus d’informations sur la planification et les fonctionnalités de NAT, reportez-vous à la rubrique <A href="lync-server-2013-hardware-load-balancer-requirements.md">Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73d44-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="73d44-223">![Détails des protocoles et ports du serveur Edge](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails des protocoles et ports du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="73d44-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="73d44-224">Paramètres de ports externes requis pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles d’interface externe</span><span class="sxs-lookup"><span data-stu-id="73d44-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73d44-225">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="73d44-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73d44-226">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="73d44-226">Source IP address</span></span></th>
<th><span data-ttu-id="73d44-227">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="73d44-227">Destination IP address</span></span></th>
<th><span data-ttu-id="73d44-228">Notes</span><span class="sxs-lookup"><span data-stu-id="73d44-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73d44-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="73d44-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="73d44-230">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-230">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-231">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="73d44-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="73d44-232">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="73d44-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="73d44-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="73d44-234">Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="73d44-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="73d44-235">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-235">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-236">Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</span><span class="sxs-lookup"><span data-stu-id="73d44-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-237">Accès/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-238">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-238">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-239">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="73d44-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-240">Trafic SIP client vers serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="73d44-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-241">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73d44-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73d44-242">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-242">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-243">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="73d44-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-244">Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</span><span class="sxs-lookup"><span data-stu-id="73d44-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-245">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73d44-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73d44-246">Adresse IP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="73d44-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-247">Partenaire fédéré</span><span class="sxs-lookup"><span data-stu-id="73d44-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="73d44-248">Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</span><span class="sxs-lookup"><span data-stu-id="73d44-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-249">Conférence Web/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-250">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-250">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-251">Adresse IP publique du service Edge de conférence Web du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-252">Support de conférence Web</span><span class="sxs-lookup"><span data-stu-id="73d44-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73d44-254">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-254">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-255">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-256">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-258">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-258">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-259">Adresse IP publique du service Edge A/V du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="73d44-260">STUN/activer la négociation des candidats sur TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="73d44-261">Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles de l’interface interne</span><span class="sxs-lookup"><span data-stu-id="73d44-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73d44-262">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="73d44-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73d44-263">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="73d44-263">Source IP address</span></span></th>
<th><span data-ttu-id="73d44-264">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="73d44-264">Destination IP address</span></span></th>
<th><span data-ttu-id="73d44-265">Notes</span><span class="sxs-lookup"><span data-stu-id="73d44-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73d44-266">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73d44-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73d44-267">Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="73d44-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="73d44-268">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-269">Trafic SIP sortant (depuis le directeur, l’adresse IP virtuelle du pool Directeur, le serveur frontal ou l’adresse IP virtuelle du pool frontal) vers le protocole VIP interne</span><span class="sxs-lookup"><span data-stu-id="73d44-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-270">Accès/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73d44-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73d44-271">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-272">Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</span><span class="sxs-lookup"><span data-stu-id="73d44-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="73d44-273">Trafic SIP entrant (vers le directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="73d44-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="73d44-275">Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="73d44-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="73d44-276">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-277">Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73d44-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73d44-279">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-279">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-280">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-281">Chemin d’accès préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes</span><span class="sxs-lookup"><span data-stu-id="73d44-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d44-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-283">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-283">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-284">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-285">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="73d44-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d44-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73d44-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73d44-287">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="73d44-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="73d44-288">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="73d44-288">Any</span></span></p></td>
<td><p><span data-ttu-id="73d44-289">Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="73d44-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

