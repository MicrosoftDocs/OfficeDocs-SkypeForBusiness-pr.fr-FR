---
title: Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="38d98-102">Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d98-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d98-103">_**Dernière modification de la rubrique:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="38d98-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="38d98-104">La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="38d98-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="38d98-105">Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="38d98-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="38d98-106">Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="38d98-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="38d98-107">Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="38d98-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="38d98-108">Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.</span><span class="sxs-lookup"><span data-stu-id="38d98-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="38d98-109">**Contour consolidé mis à l’échelle à l’aide de l’équilibrage de charge matérielle**</span><span class="sxs-lookup"><span data-stu-id="38d98-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="38d98-110">![Ports et protocoles du réseau de périmètre du serveur Edge] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Ports et protocoles du réseau de périmètre du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="38d98-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="38d98-111">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="38d98-111">Port and Protocol Details</span></span>

<span data-ttu-id="38d98-112">Il est recommandé d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.</span><span class="sxs-lookup"><span data-stu-id="38d98-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="38d98-113">Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant.</span><span class="sxs-lookup"><span data-stu-id="38d98-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="38d98-114">Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans les fonctionnalités de messagerie instantanée, de présence, de conférence Web, audio/vidéo (A/V) et de Fédération.</span><span class="sxs-lookup"><span data-stu-id="38d98-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="38d98-115">Résumé du pare-feu pour les bords consolidés mis à l’échelle: équilibrage de charge matérielle: interface externe-nœud 1 et nœud 2 (exemple)</span><span class="sxs-lookup"><span data-stu-id="38d98-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38d98-116">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="38d98-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38d98-117">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="38d98-117">Source IP address</span></span></th>
<th><span data-ttu-id="38d98-118">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="38d98-118">Destination IP address</span></span></th>
<th><span data-ttu-id="38d98-119">Remarques</span><span class="sxs-lookup"><span data-stu-id="38d98-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d98-120">Accès/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="38d98-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="38d98-121">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="38d98-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-122">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-122">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-123">Vérification et récupération des certificats</span><span class="sxs-lookup"><span data-stu-id="38d98-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="38d98-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="38d98-125">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="38d98-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-126">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-126">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-127">Requête DNS sur TCP</span><span class="sxs-lookup"><span data-stu-id="38d98-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="38d98-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="38d98-129">Adresse IP publique du service Edge d’accès Edge Server</span><span class="sxs-lookup"><span data-stu-id="38d98-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-130">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-130">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-131">Requête DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="38d98-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-132">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="38d98-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="38d98-133">Adresse IP du service Edge serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-134">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-135">Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d98-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-136">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="38d98-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="38d98-137">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-138">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-139">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="38d98-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-140">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="38d98-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="38d98-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-141">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-142">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-143">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="38d98-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-144">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="38d98-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="38d98-145">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-145">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-146">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-147">Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="38d98-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38d98-149">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-150">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-150">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-151">3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie.</span><span class="sxs-lookup"><span data-stu-id="38d98-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="38d98-152">Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="38d98-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38d98-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-154">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-155">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-156">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-158">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-158">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-159">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-160">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-162">Adresse IP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-163">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-163">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-164">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="38d98-165">Résumé du pare-feu pour les bords consolidés mis à l’échelle: charge matérielle</span><span class="sxs-lookup"><span data-stu-id="38d98-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38d98-166">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="38d98-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38d98-167">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="38d98-167">Source IP address</span></span></th>
<th><span data-ttu-id="38d98-168">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="38d98-168">Destination IP address</span></span></th>
<th><span data-ttu-id="38d98-169">Remarques</span><span class="sxs-lookup"><span data-stu-id="38d98-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d98-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="38d98-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="38d98-171">Tout (peut être défini comme adresse serveur frontale ou adresse IP virtuelle de pool frontal exécutant le service passerelle XMPP)</span><span class="sxs-lookup"><span data-stu-id="38d98-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="38d98-172">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-173">Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</span><span class="sxs-lookup"><span data-stu-id="38d98-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="38d98-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="38d98-175">Tout (peut être défini en tant que serveur principal serveur ou pool serveur serveur principal)</span><span class="sxs-lookup"><span data-stu-id="38d98-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="38d98-176">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-177">Réplication des modifications du magasin de gestion central vers le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="38d98-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="38d98-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="38d98-179">Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="38d98-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="38d98-180">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-181">Trafic de conférences Web entre le déploiement interne et l’interface du serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="38d98-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38d98-183">Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="38d98-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="38d98-184">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-185">Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="38d98-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-187">Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</span><span class="sxs-lookup"><span data-stu-id="38d98-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="38d98-188">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-189">Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="38d98-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="38d98-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="38d98-191">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-191">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-192">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-193">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="38d98-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="38d98-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="38d98-195">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-195">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-196">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-197">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="38d98-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="38d98-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="38d98-199">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-199">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-200">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-201">Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</span><span class="sxs-lookup"><span data-stu-id="38d98-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38d98-202">Les équilibreurs de charge matérielle nécessitent des exigences spécifiques pour assurer la disponibilité et l’équilibrage de charge de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38d98-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="38d98-203">La configuration requise est définie dans les tableaux et figures suivants.</span><span class="sxs-lookup"><span data-stu-id="38d98-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="38d98-204">Les fournisseurs tiers pourront utiliser une terminologie différente pour les exigences définies ici.</span><span class="sxs-lookup"><span data-stu-id="38d98-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="38d98-205">Il est nécessaire de mapper les exigences de Lync Server aux options et aux options de configuration fournies par le fournisseur du programme d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="38d98-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="38d98-206">Lorsque vous configurez des équilibreurs de charge matérielle, prenez en compte les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="38d98-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="38d98-207">La traduction d’adresses réseau source (SNAT) peut être configurée sur l’équilibrage de charge matérielle (HLB) pour le service Edge d’accès et le service Edge de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="38d98-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="38d98-208">Les données SNAT ne peuvent pas être configurées sur le service Edge A/V: le service Edge A/V doit répondre avec l’adresse réelle du serveur (et non l’adresse IP virtuelle HLB) pour une traversée simple du protocole UDP sur NAT (STUN)/Traversal à l’aide d’un NAT relais (FDÉSACTIVEZ) pour fonctionner correctement</span><span class="sxs-lookup"><span data-stu-id="38d98-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="38d98-209">Si le client envoie une demande à l’HLB, la réponse doit être retirée du VIP HLB</span><span class="sxs-lookup"><span data-stu-id="38d98-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="38d98-210">Si le client envoie une demande à l’Edge, la réponse doit être retirée de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="38d98-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="38d98-211">Les adresses IP publiques sont utilisées sur chaque interface serveur et sur les adresses IP 2 du HLB et les exigences relatives à l’adresse IP publique sont de N + 1, car il existe une adresse IP publique pour chaque interface de serveur réel et une pour chaque VIP HLB.</span><span class="sxs-lookup"><span data-stu-id="38d98-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="38d98-212">Lorsque vous avez 2 serveurs de périmètre dans le pool, il s’agit de 9 adresses IP publiques, 3 qui sont utilisées pour les VIP HLB et une pour chaque interface de serveur Edge (un total de six pour les serveurs).</span><span class="sxs-lookup"><span data-stu-id="38d98-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="38d98-213">Pour le service Edge d’accès et le service Edge de conférence Web (et l’utilisation de la traduction d’adresses réseau sur le HLB), le client contacte l’adresse VIP, l’adresse VIP remplace l’adresse IP source du client par sa propre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="38d98-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="38d98-214">L’interface du serveur adresse l’adresse d’expéditeur au VIP, l’adresse VIP modifie l’adresse source à partir de l’adresse IP de l’interface du serveur et envoie le paquet au client.</span><span class="sxs-lookup"><span data-stu-id="38d98-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="38d98-215">Pour le service Edge A/V, l’adresse VIP ne doit pas modifier l’adresse IP source, et l’adresse réelle du serveur est directement renvoyée au client: vous ne pouvez pas configurer le NAT sur le HLB pour le trafic AV</span><span class="sxs-lookup"><span data-stu-id="38d98-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="38d98-216">Si le client envoie une demande à l’adresse VIP de HLB, la réponse doit être retirée du VIP HLB</span><span class="sxs-lookup"><span data-stu-id="38d98-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="38d98-217">Si le client envoie une demande à l’adresse IP du serveur Edge, la réponse doit être retirée de l’adresse IP du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="38d98-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="38d98-218">Pour les AV, le pare-feu externe conserve l’adresse IP publique réelle du serveur pour tous les paquets.</span><span class="sxs-lookup"><span data-stu-id="38d98-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="38d98-219">Une fois établi, le client à la communication de service Edge A/V est destiné au serveur réel et non au HLB</span><span class="sxs-lookup"><span data-stu-id="38d98-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="38d98-220">Le bord interne des serveurs et clients internes doit être routé et des itinéraires persistants sont définis pour tous les réseaux internes qui hébergent des serveurs ou des clients.</span><span class="sxs-lookup"><span data-stu-id="38d98-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="38d98-221">Le protocole VIP du service Edge d’accès HLB agit comme passerelle par défaut pour chaque interface de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="38d98-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="38d98-222">Pour plus d’informations sur la planification et la fonctionnalité de NAT, voir <A href="lync-server-2013-hardware-load-balancer-requirements.md">Configuration requise pour l’équilibrage de charge matérielle pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38d98-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="38d98-223">![Détails sur les ports et protocoles du serveur Edge] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails sur les ports et protocoles du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="38d98-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="38d98-224">Paramètres de port externe requis pour les bords consolidés mis à l’échelle, équilibrage de charge matérielle: IPs virtuel d’interface externe</span><span class="sxs-lookup"><span data-stu-id="38d98-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38d98-225">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="38d98-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38d98-226">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="38d98-226">Source IP address</span></span></th>
<th><span data-ttu-id="38d98-227">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="38d98-227">Destination IP address</span></span></th>
<th><span data-ttu-id="38d98-228">Remarques</span><span class="sxs-lookup"><span data-stu-id="38d98-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d98-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="38d98-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="38d98-230">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-230">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-231">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="38d98-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="38d98-232">Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</span><span class="sxs-lookup"><span data-stu-id="38d98-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="38d98-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="38d98-234">Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</span><span class="sxs-lookup"><span data-stu-id="38d98-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="38d98-235">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-235">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-236">Le service de proxy XMPP envoie le trafic aux contacts XMPP dans les fédérations de XMPP définies.</span><span class="sxs-lookup"><span data-stu-id="38d98-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-237">/TCP/443 d’accès/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38d98-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-238">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-238">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-239">Adresse VIP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="38d98-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-240">Trafic SIP client à serveur pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="38d98-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-241">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38d98-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38d98-242">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-242">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-243">Adresse VIP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="38d98-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-244">Signalisation SIP, connectivité par messagerie instantanée privée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="38d98-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-245">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38d98-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38d98-246">Adresse VIP publique du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="38d98-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-247">Partenaire fédéré</span><span class="sxs-lookup"><span data-stu-id="38d98-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="38d98-248">Signalisation SIP, connectivité par messagerie instantanée privée et publique à l’aide du protocole SIP</span><span class="sxs-lookup"><span data-stu-id="38d98-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-249">PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-250">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-250">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-251">Adresse VIP publique du service Edge Conferencing Server Web</span><span class="sxs-lookup"><span data-stu-id="38d98-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-252">Support de conférences Web</span><span class="sxs-lookup"><span data-stu-id="38d98-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38d98-254">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-254">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-255">Adresse VIP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-256">STUN/activer la négociation des candidats via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-258">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-258">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-259">Adresse VIP publique du service Edge Server A/V</span><span class="sxs-lookup"><span data-stu-id="38d98-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="38d98-260">STUN/activer la négociation des candidats via TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="38d98-261">Résumé du pare-feu pour les bords consolidés mis à l’échelle, équilibrage de charge matérielle: IPs virtuel d’interface</span><span class="sxs-lookup"><span data-stu-id="38d98-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38d98-262">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="38d98-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38d98-263">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="38d98-263">Source IP address</span></span></th>
<th><span data-ttu-id="38d98-264">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="38d98-264">Destination IP address</span></span></th>
<th><span data-ttu-id="38d98-265">Remarques</span><span class="sxs-lookup"><span data-stu-id="38d98-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38d98-266">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38d98-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38d98-267">Tout (peut être défini en tant que directeur, adresse IP virtuelle du pool de réalisateurs, serveur frontal ou adresse IP virtuelle de pool frontal)</span><span class="sxs-lookup"><span data-stu-id="38d98-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="38d98-268">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-269">Trafic SIP sortant (à partir du réalisateur, adresse IP virtuelle du pool de directeurs, serveur frontal ou liste d’adresses IP virtuelles) vers l’adresse VIP de périphérie interne</span><span class="sxs-lookup"><span data-stu-id="38d98-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-270">/TCP/5061 d’accès/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38d98-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38d98-271">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-272">Tout (peut être défini en tant que directeur, adresse IP virtuelle du pool de réalisateurs, serveur frontal ou adresse IP virtuelle de pool frontal)</span><span class="sxs-lookup"><span data-stu-id="38d98-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="38d98-273">Trafic SIP entrant (adresse IP virtuelle du pool de directeurs, serveur frontal ou liste d’adresses IP virtuelle) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="38d98-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="38d98-275">Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</span><span class="sxs-lookup"><span data-stu-id="38d98-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="38d98-276">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-277">L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38d98-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38d98-279">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-279">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-280">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-281">Chemin préféré pour le transfert de média A/V entre les utilisateurs internes et externes</span><span class="sxs-lookup"><span data-stu-id="38d98-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38d98-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-283">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-283">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-284">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-285">Chemin de secours pour le transfert de média A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="38d98-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38d98-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="38d98-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38d98-287">Interface VIP interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="38d98-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="38d98-288">Indifférente</span><span class="sxs-lookup"><span data-stu-id="38d98-288">Any</span></span></p></td>
<td><p><span data-ttu-id="38d98-289">Chemin de secours pour le transfert de média A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</span><span class="sxs-lookup"><span data-stu-id="38d98-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

