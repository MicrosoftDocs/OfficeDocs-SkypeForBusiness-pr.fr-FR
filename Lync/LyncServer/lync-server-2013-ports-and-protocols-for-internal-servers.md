---
title: 'Lync Server 2013 : ports et protocoles pour les serveurs internes'
description: 'Lync Server 2013 : ports et protocoles pour les serveurs internes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566353"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="a4c2d-103">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c2d-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c2d-104">_**Dernière modification de la rubrique :** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="a4c2d-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="a4c2d-105">Cette section récapitule les ports et les protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4c2d-106">Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="a4c2d-107">Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="a4c2d-108">Le IMMCU est un composant de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="a4c2d-109">La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="a4c2d-110">La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="a4c2d-111">Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a4c2d-112">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="a4c2d-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4c2d-113">Le pare-feu Windows doit être en cours d’exécution avant de démarrer les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="a4c2d-114">Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="a4c2d-115">Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="a4c2d-116">Ports de serveurs requis (par rôle serveur)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-116">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c2d-117">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-117">Server role</span></span></th>
<th><span data-ttu-id="a4c2d-118">Nom du service</span><span class="sxs-lookup"><span data-stu-id="a4c2d-118">Service name</span></span></th>
<th><span data-ttu-id="a4c2d-119">Port</span><span class="sxs-lookup"><span data-stu-id="a4c2d-119">Port</span></span></th>
<th><span data-ttu-id="a4c2d-120">Protocole</span><span class="sxs-lookup"><span data-stu-id="a4c2d-120">Protocol</span></span></th>
<th><span data-ttu-id="a4c2d-121">Notes</span><span class="sxs-lookup"><span data-stu-id="a4c2d-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-122">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-123">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="a4c2d-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-124">1434</span><span class="sxs-lookup"><span data-stu-id="a4c2d-124">1434</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-125">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="a4c2d-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-126">SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-127">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-128">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-129">5060</span><span class="sxs-lookup"><span data-stu-id="a4c2d-129">5060</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-130">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-131">Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-132">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-133">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-134">5061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-134">5061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-p102">Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-138">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-139">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-140">444</span><span class="sxs-lookup"><span data-stu-id="a4c2d-140">444</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-141">HTTPS</span></span></p>
<p><span data-ttu-id="a4c2d-142">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-143">Utilisé pour les communications HTTPs entre le focus (le composant Lync Server qui gère l’état des conférences) et les serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="a4c2d-144">Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliances et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-145">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-146">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-147">135</span><span class="sxs-lookup"><span data-stu-id="a4c2d-147">135</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-148">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-149">Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-150">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-151">Service de conférence par messagerie instantanée Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-152">5062</span><span class="sxs-lookup"><span data-stu-id="a4c2d-152">5062</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-153">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-154">Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-155">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-156">Service de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-157">8057</span><span class="sxs-lookup"><span data-stu-id="a4c2d-157">8057</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-159">Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-160">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-161">Service de compatibilité de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-162">8058</span><span class="sxs-lookup"><span data-stu-id="a4c2d-162">8058</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-164">Utilisé pour l’écoute des connexions PSOM (persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-165">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-166">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-167">5063</span><span class="sxs-lookup"><span data-stu-id="a4c2d-167">5063</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-168">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-169">Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-170">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-171">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="a4c2d-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-174">Plage de ports multimédias utilisée pour les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-175">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-176">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-177">80</span><span class="sxs-lookup"><span data-stu-id="a4c2d-177">80</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-179">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-180">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-181">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-182">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-182">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-184">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-185">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-186">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-187">8080</span><span class="sxs-lookup"><span data-stu-id="a4c2d-187">8080</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-188">TCP et HTTP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-189">Utilisé par les composants Web pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-190">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-191">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="a4c2d-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-192">4443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-192">4443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-194">HTTPs (des proxys inverses) et les communications inter-pool frontaux HTTPs pour la connexion au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-195">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-196">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="a4c2d-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-197">8060</span><span class="sxs-lookup"><span data-stu-id="a4c2d-197">8060</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-199">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-200">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="a4c2d-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-201">8061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-201">8061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-203">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-204">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="a4c2d-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-205">5086</span><span class="sxs-lookup"><span data-stu-id="a4c2d-205">5086</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-207">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="a4c2d-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-208">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-209">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="a4c2d-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-210">5087</span><span class="sxs-lookup"><span data-stu-id="a4c2d-210">5087</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-212">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="a4c2d-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-213">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-214">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="a4c2d-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-215">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-215">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-217">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-218">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-219">5064</span><span class="sxs-lookup"><span data-stu-id="a4c2d-219">5064</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-220">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-221">Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-222">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-223">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-224">5072</span><span class="sxs-lookup"><span data-stu-id="a4c2d-224">5072</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-225">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-226">Utilisé pour les demandes SIP entrantes pour le service de surveillance (Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-227">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-228">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-229">5070</span><span class="sxs-lookup"><span data-stu-id="a4c2d-229">5070</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-230">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-231">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-232">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-233">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-234">5067</span><span class="sxs-lookup"><span data-stu-id="a4c2d-234">5067</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-236">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-237">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-238">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-239">5068</span><span class="sxs-lookup"><span data-stu-id="a4c2d-239">5068</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-240">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-241">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-242">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-243">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-244">5081</span><span class="sxs-lookup"><span data-stu-id="a4c2d-244">5081</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-245">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-246">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-247">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-248">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-249">5082</span><span class="sxs-lookup"><span data-stu-id="a4c2d-249">5082</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-251">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-252">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-253">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-254">5065</span><span class="sxs-lookup"><span data-stu-id="a4c2d-254">5065</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-255">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-256">Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-257">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-258">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="a4c2d-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-260">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-261">Plage de ports multimédias utilisée pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-262">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-263">Service d’annonce de conférence Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-264">5073</span><span class="sxs-lookup"><span data-stu-id="a4c2d-264">5073</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-265">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-266">Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Lync Server (c’est-à-dire pour les conférences rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-267">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-268">service de parcage d’appel Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-269">5075</span><span class="sxs-lookup"><span data-stu-id="a4c2d-269">5075</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-270">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-271">Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-272">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-273">Service de test audio Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-274">5076</span><span class="sxs-lookup"><span data-stu-id="a4c2d-274">5076</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-275">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-276">Utilisé pour les demandes SIP entrantes du service de test audio.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-277">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-278">Non applicable</span><span class="sxs-lookup"><span data-stu-id="a4c2d-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-279">5066</span><span class="sxs-lookup"><span data-stu-id="a4c2d-279">5066</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-280">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-281">Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-282">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-283">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-284">5071</span><span class="sxs-lookup"><span data-stu-id="a4c2d-284">5071</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-285">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-286">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-287">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-288">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-289">8404</span><span class="sxs-lookup"><span data-stu-id="a4c2d-289">8404</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-291">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-292">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-293">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-294">5080</span><span class="sxs-lookup"><span data-stu-id="a4c2d-294">5080</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-295">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-296">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-297">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a4c2d-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-298">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-299">448</span><span class="sxs-lookup"><span data-stu-id="a4c2d-299">448</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-300">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-301">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-302">Serveurs frontaux où réside le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="a4c2d-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-303">Service de l’agent réplicateur maître Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-304">445</span><span class="sxs-lookup"><span data-stu-id="a4c2d-304">445</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-305">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-306">Utilisé pour envoyer des données de configuration à partir du magasin central de gestion vers les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-307">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-308">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="a4c2d-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-309">1434</span><span class="sxs-lookup"><span data-stu-id="a4c2d-309">1434</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-310">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="a4c2d-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-311">SQL Browser pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="a4c2d-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-312">Tous les serveurs internes</span><span class="sxs-lookup"><span data-stu-id="a4c2d-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-313">Divers</span><span class="sxs-lookup"><span data-stu-id="a4c2d-313">Various</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="a4c2d-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-316">Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="a4c2d-317">Utilisé par tous les serveurs qui terminent l’audio : serveurs frontaux (service de surveillance de conférence Lync Server, service d’annonce de conférence Lync Server et service de conférence audio/vidéo Lync Server) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-318">Serveurs Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="a4c2d-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4c2d-319">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4c2d-320">Utilisé par Lync Server 2013 pour se connecter à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-321">Directeurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-322">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-323">5060</span><span class="sxs-lookup"><span data-stu-id="a4c2d-323">5060</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-324">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-325">Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-326">Directeurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-327">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-328">444</span><span class="sxs-lookup"><span data-stu-id="a4c2d-328">444</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-329">HTTPS</span></span></p>
<p><span data-ttu-id="a4c2d-330">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-331">Communication entre serveurs frontaux et directeurs.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="a4c2d-332">De plus, le certificat client doit être publié (sur les serveurs frontaux) ou validé si le certificat client a déjà été publié.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-333">Directeurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-334">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-335">80</span><span class="sxs-lookup"><span data-stu-id="a4c2d-335">80</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-336">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-p105">Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-339">Directeurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-340">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-341">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-341">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-343">Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-344">Directeurs</span><span class="sxs-lookup"><span data-stu-id="a4c2d-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-345">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-346">5061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-346">5061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-347">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-348">Utilisé pour les communications internes entre serveurs et pour les connexions client.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-349">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="a4c2d-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-350">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-351">5070</span><span class="sxs-lookup"><span data-stu-id="a4c2d-351">5070</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-352">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-353">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-354">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="a4c2d-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-355">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-356">5067</span><span class="sxs-lookup"><span data-stu-id="a4c2d-356">5067</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-358">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-359">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="a4c2d-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-360">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-361">5068</span><span class="sxs-lookup"><span data-stu-id="a4c2d-361">5068</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-362">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-363">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-364">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="a4c2d-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-365">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="a4c2d-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-366">5070</span><span class="sxs-lookup"><span data-stu-id="a4c2d-366">5070</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-368">Utilisé pour les demandes SIP des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-369">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a4c2d-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-370">SIP de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a4c2d-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-371">5041</span><span class="sxs-lookup"><span data-stu-id="a4c2d-371">5041</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-373">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a4c2d-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-374">Conversation permanente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-375">881</span><span class="sxs-lookup"><span data-stu-id="a4c2d-375">881</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-376">TCP (TLS) et TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-377">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a4c2d-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-378">Service de transfert de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a4c2d-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-379">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-379">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a4c2d-381">Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="a4c2d-382">Bien que Lync Server n’utilise plus le port TCP 5060, pendant le déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou directeur utilisera pour se connecter au système PBX.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="a4c2d-383">Pour plus d’informations, reportez-vous à l’applet de commande <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="a4c2d-384">Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="a4c2d-385">Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé</span><span class="sxs-lookup"><span data-stu-id="a4c2d-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c2d-386">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="a4c2d-386">Load Balancer</span></span></th>
<th><span data-ttu-id="a4c2d-387">Port</span><span class="sxs-lookup"><span data-stu-id="a4c2d-387">Port</span></span></th>
<th><span data-ttu-id="a4c2d-388">Protocole</span><span class="sxs-lookup"><span data-stu-id="a4c2d-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-389">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-390">5061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-390">5061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-392">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-393">444</span><span class="sxs-lookup"><span data-stu-id="a4c2d-393">444</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-395">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-396">135</span><span class="sxs-lookup"><span data-stu-id="a4c2d-396">135</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-397">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-398">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-399">80</span><span class="sxs-lookup"><span data-stu-id="a4c2d-399">80</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-401">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-402">8080</span><span class="sxs-lookup"><span data-stu-id="a4c2d-402">8080</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-403">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="a4c2d-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-404">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-405">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-405">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-407">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-408">4443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-408">4443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-409">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-410">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-411">5072</span><span class="sxs-lookup"><span data-stu-id="a4c2d-411">5072</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-412">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-413">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-414">5073</span><span class="sxs-lookup"><span data-stu-id="a4c2d-414">5073</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-415">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-416">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-417">5075</span><span class="sxs-lookup"><span data-stu-id="a4c2d-417">5075</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-418">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-419">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-420">5076</span><span class="sxs-lookup"><span data-stu-id="a4c2d-420">5076</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-421">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-422">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-423">5071</span><span class="sxs-lookup"><span data-stu-id="a4c2d-423">5071</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-424">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-425">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-426">5080</span><span class="sxs-lookup"><span data-stu-id="a4c2d-426">5080</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-427">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-428">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-429">448</span><span class="sxs-lookup"><span data-stu-id="a4c2d-429">448</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-430">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-431">Programme d’équilibrage de la charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="a4c2d-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-432">5070</span><span class="sxs-lookup"><span data-stu-id="a4c2d-432">5070</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-433">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-434">Programme d’équilibrage de la charge du serveur frontal (si le pool exécute également le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-435">5070</span><span class="sxs-lookup"><span data-stu-id="a4c2d-435">5070</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-436">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-437">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-438">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-438">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-440">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-441">444</span><span class="sxs-lookup"><span data-stu-id="a4c2d-441">444</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-443">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-444">5061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-444">5061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-445">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-446">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-447">4443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-447">4443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-448">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4c2d-p107">Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="a4c2d-451">Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé</span><span class="sxs-lookup"><span data-stu-id="a4c2d-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c2d-452">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="a4c2d-452">Load Balancer</span></span></th>
<th><span data-ttu-id="a4c2d-453">Port</span><span class="sxs-lookup"><span data-stu-id="a4c2d-453">Port</span></span></th>
<th><span data-ttu-id="a4c2d-454">Protocole</span><span class="sxs-lookup"><span data-stu-id="a4c2d-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-455">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-456">80</span><span class="sxs-lookup"><span data-stu-id="a4c2d-456">80</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-458">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-459">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-459">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-461">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-462">8080</span><span class="sxs-lookup"><span data-stu-id="a4c2d-462">8080</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-463">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="a4c2d-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-464">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="a4c2d-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-465">4443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-465">4443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-466">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-467">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-468">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-468">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a4c2d-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-470">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="a4c2d-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-471">4443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-471">4443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-472">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="a4c2d-473">Ports client requis</span><span class="sxs-lookup"><span data-stu-id="a4c2d-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c2d-474">Composant</span><span class="sxs-lookup"><span data-stu-id="a4c2d-474">Component</span></span></th>
<th><span data-ttu-id="a4c2d-475">Port</span><span class="sxs-lookup"><span data-stu-id="a4c2d-475">Port</span></span></th>
<th><span data-ttu-id="a4c2d-476">Protocole</span><span class="sxs-lookup"><span data-stu-id="a4c2d-476">Protocol</span></span></th>
<th><span data-ttu-id="a4c2d-477">Notes</span><span class="sxs-lookup"><span data-stu-id="a4c2d-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-478">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-479">67/68</span><span class="sxs-lookup"><span data-stu-id="a4c2d-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-480">SERVICE</span><span class="sxs-lookup"><span data-stu-id="a4c2d-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-481">Utilisé par Lync Server pour rechercher le nom de domaine complet du serveur d’inscriptions (en d’autres points, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-482">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-483">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-483">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-485">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-486">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-487">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-487">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-489">Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-490">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-491">443</span><span class="sxs-lookup"><span data-stu-id="a4c2d-491">443</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-493">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-494">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-495">3478</span><span class="sxs-lookup"><span data-stu-id="a4c2d-495">3478</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-497">Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-498">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-499">5061</span><span class="sxs-lookup"><span data-stu-id="a4c2d-499">5061</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-501">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-502">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="a4c2d-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-504">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-505">Utilisé pour le transfert de fichiers entre les clients Lync et les clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-506">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a4c2d-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-509">Plage de ports audio (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-510">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a4c2d-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-513">Plage de ports vidéo (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-514">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a4c2d-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-516">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-517">Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c2d-518">Clients</span><span class="sxs-lookup"><span data-stu-id="a4c2d-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="a4c2d-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-520">TCP</span><span class="sxs-lookup"><span data-stu-id="a4c2d-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-521">Partage d’application.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c2d-522">Téléphone de partie commune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="a4c2d-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="a4c2d-523">Téléphone de bureau Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="a4c2d-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="a4c2d-524">Téléphone IP HP 4110 (téléphone de partie commune)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="a4c2d-525">Téléphone IP HP 4120 (téléphone de bureau)</span><span class="sxs-lookup"><span data-stu-id="a4c2d-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="a4c2d-526">Téléphone de partie commune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="a4c2d-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="a4c2d-527">Téléphone de bureau IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="a4c2d-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="a4c2d-528">Téléphone de bureau IP CX700</span><span class="sxs-lookup"><span data-stu-id="a4c2d-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="a4c2d-529">Téléphone de conférence IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="a4c2d-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-530">67/68</span><span class="sxs-lookup"><span data-stu-id="a4c2d-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-531">SERVICE</span><span class="sxs-lookup"><span data-stu-id="a4c2d-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="a4c2d-532">Utilisé par les appareils mentionnés pour rechercher le certificat Lync Server, le nom de domaine complet (FQDN) de mise en service et le nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4c2d-533">**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres clientmediaportrangeenabled, ClientMediaPort et ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4c2d-534">Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu de système d’exploitation requises sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a4c2d-535">Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).</span><span class="sxs-lookup"><span data-stu-id="a4c2d-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

