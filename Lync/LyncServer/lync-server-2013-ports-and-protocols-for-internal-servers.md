---
title: 'Lync Server 2013 : ports et protocoles pour les serveurs internes'
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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513401"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="2df00-102">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2df00-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2df00-103">_**Dernière modification de la rubrique :** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="2df00-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="2df00-104">Cette section récapitule les ports et les protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2df00-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2df00-105">Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="2df00-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="2df00-106">Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu.</span><span class="sxs-lookup"><span data-stu-id="2df00-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="2df00-107">Le IMMCU est un composant de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="2df00-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="2df00-108">La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="2df00-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="2df00-109">La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="2df00-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="2df00-110">Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.</span><span class="sxs-lookup"><span data-stu-id="2df00-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="2df00-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="2df00-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2df00-112">Le pare-feu Windows doit être en cours d’exécution avant de démarrer les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="2df00-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="2df00-113">Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df00-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="2df00-114">Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.</span><span class="sxs-lookup"><span data-stu-id="2df00-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="2df00-115">Ports de serveurs requis (par rôle serveur)</span><span class="sxs-lookup"><span data-stu-id="2df00-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="2df00-116">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="2df00-116">Server role</span></span></th>
<th><span data-ttu-id="2df00-117">Nom du service</span><span class="sxs-lookup"><span data-stu-id="2df00-117">Service name</span></span></th>
<th><span data-ttu-id="2df00-118">Port</span><span class="sxs-lookup"><span data-stu-id="2df00-118">Port</span></span></th>
<th><span data-ttu-id="2df00-119">Protocole</span><span class="sxs-lookup"><span data-stu-id="2df00-119">Protocol</span></span></th>
<th><span data-ttu-id="2df00-120">Notes</span><span class="sxs-lookup"><span data-stu-id="2df00-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df00-121">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="2df00-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="2df00-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="2df00-123">1434</span><span class="sxs-lookup"><span data-stu-id="2df00-123">1434</span></span></p></td>
<td><p><span data-ttu-id="2df00-124">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="2df00-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-125">SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="2df00-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-126">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-127">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-128">5060</span><span class="sxs-lookup"><span data-stu-id="2df00-128">5060</span></span></p></td>
<td><p><span data-ttu-id="2df00-129">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-130">Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="2df00-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-131">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-132">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-133">5061</span><span class="sxs-lookup"><span data-stu-id="2df00-133">5061</span></span></p></td>
<td><p><span data-ttu-id="2df00-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-p102">Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="2df00-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-137">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-138">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-139">444</span><span class="sxs-lookup"><span data-stu-id="2df00-139">444</span></span></p></td>
<td><p><span data-ttu-id="2df00-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-140">HTTPS</span></span></p>
<p><span data-ttu-id="2df00-141">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-142">Utilisé pour les communications HTTPs entre le focus (le composant Lync Server qui gère l’état des conférences) et les serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="2df00-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="2df00-143">Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliances et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="2df00-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-144">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-145">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-146">135</span><span class="sxs-lookup"><span data-stu-id="2df00-146">135</span></span></p></td>
<td><p><span data-ttu-id="2df00-147">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="2df00-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="2df00-148">Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="2df00-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-149">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-150">Service de conférence par messagerie instantanée Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-151">5062</span><span class="sxs-lookup"><span data-stu-id="2df00-151">5062</span></span></p></td>
<td><p><span data-ttu-id="2df00-152">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-153">Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="2df00-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-154">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-155">Service de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-156">8057</span><span class="sxs-lookup"><span data-stu-id="2df00-156">8057</span></span></p></td>
<td><p><span data-ttu-id="2df00-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-158">Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="2df00-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-159">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-160">Service de compatibilité de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-161">8058</span><span class="sxs-lookup"><span data-stu-id="2df00-161">8058</span></span></p></td>
<td><p><span data-ttu-id="2df00-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-163">Utilisé pour l’écoute des connexions PSOM (persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2df00-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-164">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-165">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-166">5063</span><span class="sxs-lookup"><span data-stu-id="2df00-166">5063</span></span></p></td>
<td><p><span data-ttu-id="2df00-167">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-168">Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="2df00-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-169">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-170">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="2df00-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="2df00-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2df00-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-173">Plage de ports multimédias utilisée pour les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="2df00-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-174">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-175">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-176">80</span><span class="sxs-lookup"><span data-stu-id="2df00-176">80</span></span></p></td>
<td><p><span data-ttu-id="2df00-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="2df00-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="2df00-178">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-179">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-180">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-181">443</span><span class="sxs-lookup"><span data-stu-id="2df00-181">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2df00-183">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="2df00-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-184">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-185">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-186">8080</span><span class="sxs-lookup"><span data-stu-id="2df00-186">8080</span></span></p></td>
<td><p><span data-ttu-id="2df00-187">TCP et HTTP</span><span class="sxs-lookup"><span data-stu-id="2df00-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="2df00-188">Utilisé par les composants Web pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="2df00-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-189">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-190">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="2df00-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2df00-191">4443</span><span class="sxs-lookup"><span data-stu-id="2df00-191">4443</span></span></p></td>
<td><p><span data-ttu-id="2df00-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2df00-193">HTTPs (des proxys inverses) et les communications inter-pool frontaux HTTPs pour la connexion au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="2df00-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-194">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-195">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="2df00-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2df00-196">8060</span><span class="sxs-lookup"><span data-stu-id="2df00-196">8060</span></span></p></td>
<td><p><span data-ttu-id="2df00-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-198">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-199">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="2df00-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="2df00-200">8061</span><span class="sxs-lookup"><span data-stu-id="2df00-200">8061</span></span></p></td>
<td><p><span data-ttu-id="2df00-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-202">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-203">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="2df00-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2df00-204">5086</span><span class="sxs-lookup"><span data-stu-id="2df00-204">5086</span></span></p></td>
<td><p><span data-ttu-id="2df00-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-206">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="2df00-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-207">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-208">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="2df00-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2df00-209">5087</span><span class="sxs-lookup"><span data-stu-id="2df00-209">5087</span></span></p></td>
<td><p><span data-ttu-id="2df00-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-211">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="2df00-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-212">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-213">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="2df00-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="2df00-214">443</span><span class="sxs-lookup"><span data-stu-id="2df00-214">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-216">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-217">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="2df00-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="2df00-218">5064</span><span class="sxs-lookup"><span data-stu-id="2df00-218">5064</span></span></p></td>
<td><p><span data-ttu-id="2df00-219">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-220">Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2df00-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-221">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-222">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="2df00-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="2df00-223">5072</span><span class="sxs-lookup"><span data-stu-id="2df00-223">5072</span></span></p></td>
<td><p><span data-ttu-id="2df00-224">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-225">Utilisé pour les demandes SIP entrantes pour le service de surveillance (Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="2df00-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-226">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-227">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-228">5070</span><span class="sxs-lookup"><span data-stu-id="2df00-228">5070</span></span></p></td>
<td><p><span data-ttu-id="2df00-229">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-230">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="2df00-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-231">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-232">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-233">5067</span><span class="sxs-lookup"><span data-stu-id="2df00-233">5067</span></span></p></td>
<td><p><span data-ttu-id="2df00-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-235">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="2df00-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-236">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-237">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-238">5068</span><span class="sxs-lookup"><span data-stu-id="2df00-238">5068</span></span></p></td>
<td><p><span data-ttu-id="2df00-239">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-240">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="2df00-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-241">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-242">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-243">5081</span><span class="sxs-lookup"><span data-stu-id="2df00-243">5081</span></span></p></td>
<td><p><span data-ttu-id="2df00-244">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-245">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2df00-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-246">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="2df00-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-247">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-248">5082</span><span class="sxs-lookup"><span data-stu-id="2df00-248">5082</span></span></p></td>
<td><p><span data-ttu-id="2df00-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-250">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2df00-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-251">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-252">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-253">5065</span><span class="sxs-lookup"><span data-stu-id="2df00-253">5065</span></span></p></td>
<td><p><span data-ttu-id="2df00-254">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-255">Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="2df00-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-256">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-257">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="2df00-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="2df00-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="2df00-259">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-260">Plage de ports multimédias utilisée pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="2df00-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-261">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-262">Service d’annonce de conférence Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="2df00-263">5073</span><span class="sxs-lookup"><span data-stu-id="2df00-263">5073</span></span></p></td>
<td><p><span data-ttu-id="2df00-264">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-265">Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Lync Server (c’est-à-dire pour les conférences rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="2df00-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-266">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-267">service de parcage d’appel Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="2df00-268">5075</span><span class="sxs-lookup"><span data-stu-id="2df00-268">5075</span></span></p></td>
<td><p><span data-ttu-id="2df00-269">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-270">Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="2df00-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-271">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-272">Service de test audio Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="2df00-273">5076</span><span class="sxs-lookup"><span data-stu-id="2df00-273">5076</span></span></p></td>
<td><p><span data-ttu-id="2df00-274">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-275">Utilisé pour les demandes SIP entrantes du service de test audio.</span><span class="sxs-lookup"><span data-stu-id="2df00-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-276">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-277">Non applicable</span><span class="sxs-lookup"><span data-stu-id="2df00-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="2df00-278">5066</span><span class="sxs-lookup"><span data-stu-id="2df00-278">5066</span></span></p></td>
<td><p><span data-ttu-id="2df00-279">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-280">Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</span><span class="sxs-lookup"><span data-stu-id="2df00-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-281">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-282">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="2df00-283">5071</span><span class="sxs-lookup"><span data-stu-id="2df00-283">5071</span></span></p></td>
<td><p><span data-ttu-id="2df00-284">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-285">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="2df00-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-286">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-287">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="2df00-288">8404</span><span class="sxs-lookup"><span data-stu-id="2df00-288">8404</span></span></p></td>
<td><p><span data-ttu-id="2df00-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-290">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="2df00-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-291">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-292">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="2df00-293">5080</span><span class="sxs-lookup"><span data-stu-id="2df00-293">5080</span></span></p></td>
<td><p><span data-ttu-id="2df00-294">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-295">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="2df00-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-296">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="2df00-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-297">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="2df00-298">448</span><span class="sxs-lookup"><span data-stu-id="2df00-298">448</span></span></p></td>
<td><p><span data-ttu-id="2df00-299">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-300">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2df00-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-301">Serveurs frontaux où réside le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="2df00-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="2df00-302">Service de l’agent réplicateur maître Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="2df00-303">445</span><span class="sxs-lookup"><span data-stu-id="2df00-303">445</span></span></p></td>
<td><p><span data-ttu-id="2df00-304">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-305">Utilisé pour envoyer des données de configuration à partir du magasin central de gestion vers les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2df00-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-306">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="2df00-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="2df00-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="2df00-308">1434</span><span class="sxs-lookup"><span data-stu-id="2df00-308">1434</span></span></p></td>
<td><p><span data-ttu-id="2df00-309">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="2df00-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-310">SQL Browser pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="2df00-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-311">Tous les serveurs internes</span><span class="sxs-lookup"><span data-stu-id="2df00-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-312">Divers</span><span class="sxs-lookup"><span data-stu-id="2df00-312">Various</span></span></p></td>
<td><p><span data-ttu-id="2df00-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="2df00-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="2df00-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2df00-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-315">Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="2df00-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="2df00-316">Utilisé par tous les serveurs qui terminent l’audio : serveurs frontaux (service de surveillance de conférence Lync Server, service d’annonce de conférence Lync Server et service de conférence audio/vidéo Lync Server) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="2df00-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-317">Serveurs Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="2df00-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2df00-318">443</span><span class="sxs-lookup"><span data-stu-id="2df00-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2df00-319">Utilisé par Lync Server 2013 pour se connecter à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="2df00-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-320">Directeurs</span><span class="sxs-lookup"><span data-stu-id="2df00-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="2df00-321">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-322">5060</span><span class="sxs-lookup"><span data-stu-id="2df00-322">5060</span></span></p></td>
<td><p><span data-ttu-id="2df00-323">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-324">Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="2df00-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-325">Directeurs</span><span class="sxs-lookup"><span data-stu-id="2df00-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="2df00-326">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-327">444</span><span class="sxs-lookup"><span data-stu-id="2df00-327">444</span></span></p></td>
<td><p><span data-ttu-id="2df00-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-328">HTTPS</span></span></p>
<p><span data-ttu-id="2df00-329">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-330">Communication entre serveurs frontaux et directeurs.</span><span class="sxs-lookup"><span data-stu-id="2df00-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="2df00-331">De plus, le certificat client doit être publié (sur les serveurs frontaux) ou validé si le certificat client a déjà été publié.</span><span class="sxs-lookup"><span data-stu-id="2df00-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-332">Directeurs</span><span class="sxs-lookup"><span data-stu-id="2df00-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="2df00-333">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-334">80</span><span class="sxs-lookup"><span data-stu-id="2df00-334">80</span></span></p></td>
<td><p><span data-ttu-id="2df00-335">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-p105">Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="2df00-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-338">Directeurs</span><span class="sxs-lookup"><span data-stu-id="2df00-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="2df00-339">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="2df00-340">443</span><span class="sxs-lookup"><span data-stu-id="2df00-340">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="2df00-342">Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="2df00-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-343">Directeurs</span><span class="sxs-lookup"><span data-stu-id="2df00-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="2df00-344">Service de Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="2df00-345">5061</span><span class="sxs-lookup"><span data-stu-id="2df00-345">5061</span></span></p></td>
<td><p><span data-ttu-id="2df00-346">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-347">Utilisé pour les communications internes entre serveurs et pour les connexions client.</span><span class="sxs-lookup"><span data-stu-id="2df00-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-348">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="2df00-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-349">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-350">5070</span><span class="sxs-lookup"><span data-stu-id="2df00-350">5070</span></span></p></td>
<td><p><span data-ttu-id="2df00-351">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-352">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="2df00-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-353">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="2df00-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-354">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-355">5067</span><span class="sxs-lookup"><span data-stu-id="2df00-355">5067</span></span></p></td>
<td><p><span data-ttu-id="2df00-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-357">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2df00-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-358">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="2df00-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-359">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-360">5068</span><span class="sxs-lookup"><span data-stu-id="2df00-360">5068</span></span></p></td>
<td><p><span data-ttu-id="2df00-361">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-362">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2df00-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-363">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="2df00-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="2df00-364">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="2df00-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="2df00-365">5070</span><span class="sxs-lookup"><span data-stu-id="2df00-365">5070</span></span></p></td>
<td><p><span data-ttu-id="2df00-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-367">Utilisé pour les demandes SIP des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="2df00-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-368">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2df00-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-369">SIP de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2df00-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="2df00-370">5041</span><span class="sxs-lookup"><span data-stu-id="2df00-370">5041</span></span></p></td>
<td><p><span data-ttu-id="2df00-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-372">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2df00-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-373">Conversation permanente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="2df00-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="2df00-374">881</span><span class="sxs-lookup"><span data-stu-id="2df00-374">881</span></span></p></td>
<td><p><span data-ttu-id="2df00-375">TCP (TLS) et TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-376">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2df00-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2df00-377">Service de transfert de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2df00-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="2df00-378">443</span><span class="sxs-lookup"><span data-stu-id="2df00-378">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2df00-380">Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX.</span><span class="sxs-lookup"><span data-stu-id="2df00-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="2df00-381">Bien que Lync Server n’utilise plus le port TCP 5060, pendant le déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou directeur utilisera pour se connecter au système PBX.</span><span class="sxs-lookup"><span data-stu-id="2df00-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="2df00-382">Pour plus d’informations, reportez-vous à l’applet de commande <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2df00-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="2df00-383">Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="2df00-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="2df00-384">Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé</span><span class="sxs-lookup"><span data-stu-id="2df00-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df00-385">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="2df00-385">Load Balancer</span></span></th>
<th><span data-ttu-id="2df00-386">Port</span><span class="sxs-lookup"><span data-stu-id="2df00-386">Port</span></span></th>
<th><span data-ttu-id="2df00-387">Protocole</span><span class="sxs-lookup"><span data-stu-id="2df00-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df00-388">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-389">5061</span><span class="sxs-lookup"><span data-stu-id="2df00-389">5061</span></span></p></td>
<td><p><span data-ttu-id="2df00-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-391">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-392">444</span><span class="sxs-lookup"><span data-stu-id="2df00-392">444</span></span></p></td>
<td><p><span data-ttu-id="2df00-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-394">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-395">135</span><span class="sxs-lookup"><span data-stu-id="2df00-395">135</span></span></p></td>
<td><p><span data-ttu-id="2df00-396">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="2df00-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-397">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-398">80</span><span class="sxs-lookup"><span data-stu-id="2df00-398">80</span></span></p></td>
<td><p><span data-ttu-id="2df00-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="2df00-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-400">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-401">8080</span><span class="sxs-lookup"><span data-stu-id="2df00-401">8080</span></span></p></td>
<td><p><span data-ttu-id="2df00-402">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="2df00-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-403">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-404">443</span><span class="sxs-lookup"><span data-stu-id="2df00-404">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-406">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-407">4443</span><span class="sxs-lookup"><span data-stu-id="2df00-407">4443</span></span></p></td>
<td><p><span data-ttu-id="2df00-408">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="2df00-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-409">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-410">5072</span><span class="sxs-lookup"><span data-stu-id="2df00-410">5072</span></span></p></td>
<td><p><span data-ttu-id="2df00-411">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-412">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-413">5073</span><span class="sxs-lookup"><span data-stu-id="2df00-413">5073</span></span></p></td>
<td><p><span data-ttu-id="2df00-414">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-415">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-416">5075</span><span class="sxs-lookup"><span data-stu-id="2df00-416">5075</span></span></p></td>
<td><p><span data-ttu-id="2df00-417">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-418">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-419">5076</span><span class="sxs-lookup"><span data-stu-id="2df00-419">5076</span></span></p></td>
<td><p><span data-ttu-id="2df00-420">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-421">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-422">5071</span><span class="sxs-lookup"><span data-stu-id="2df00-422">5071</span></span></p></td>
<td><p><span data-ttu-id="2df00-423">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-424">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-425">5080</span><span class="sxs-lookup"><span data-stu-id="2df00-425">5080</span></span></p></td>
<td><p><span data-ttu-id="2df00-426">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-427">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-428">448</span><span class="sxs-lookup"><span data-stu-id="2df00-428">448</span></span></p></td>
<td><p><span data-ttu-id="2df00-429">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-430">Programme d’équilibrage de la charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="2df00-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-431">5070</span><span class="sxs-lookup"><span data-stu-id="2df00-431">5070</span></span></p></td>
<td><p><span data-ttu-id="2df00-432">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-433">Programme d’équilibrage de la charge du serveur frontal (si le pool exécute également le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="2df00-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="2df00-434">5070</span><span class="sxs-lookup"><span data-stu-id="2df00-434">5070</span></span></p></td>
<td><p><span data-ttu-id="2df00-435">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-436">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-437">443</span><span class="sxs-lookup"><span data-stu-id="2df00-437">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-439">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-440">444</span><span class="sxs-lookup"><span data-stu-id="2df00-440">444</span></span></p></td>
<td><p><span data-ttu-id="2df00-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-442">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-443">5061</span><span class="sxs-lookup"><span data-stu-id="2df00-443">5061</span></span></p></td>
<td><p><span data-ttu-id="2df00-444">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-445">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-446">4443</span><span class="sxs-lookup"><span data-stu-id="2df00-446">4443</span></span></p></td>
<td><p><span data-ttu-id="2df00-447">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="2df00-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2df00-p107">Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="2df00-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="2df00-450">Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé</span><span class="sxs-lookup"><span data-stu-id="2df00-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df00-451">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="2df00-451">Load Balancer</span></span></th>
<th><span data-ttu-id="2df00-452">Port</span><span class="sxs-lookup"><span data-stu-id="2df00-452">Port</span></span></th>
<th><span data-ttu-id="2df00-453">Protocole</span><span class="sxs-lookup"><span data-stu-id="2df00-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df00-454">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-455">80</span><span class="sxs-lookup"><span data-stu-id="2df00-455">80</span></span></p></td>
<td><p><span data-ttu-id="2df00-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="2df00-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-457">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-458">443</span><span class="sxs-lookup"><span data-stu-id="2df00-458">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-460">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-461">8080</span><span class="sxs-lookup"><span data-stu-id="2df00-461">8080</span></span></p></td>
<td><p><span data-ttu-id="2df00-462">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="2df00-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-463">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="2df00-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-464">4443</span><span class="sxs-lookup"><span data-stu-id="2df00-464">4443</span></span></p></td>
<td><p><span data-ttu-id="2df00-465">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="2df00-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-466">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-467">443</span><span class="sxs-lookup"><span data-stu-id="2df00-467">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2df00-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-469">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="2df00-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="2df00-470">4443</span><span class="sxs-lookup"><span data-stu-id="2df00-470">4443</span></span></p></td>
<td><p><span data-ttu-id="2df00-471">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="2df00-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="2df00-472">Ports client requis</span><span class="sxs-lookup"><span data-stu-id="2df00-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df00-473">Composant</span><span class="sxs-lookup"><span data-stu-id="2df00-473">Component</span></span></th>
<th><span data-ttu-id="2df00-474">Port</span><span class="sxs-lookup"><span data-stu-id="2df00-474">Port</span></span></th>
<th><span data-ttu-id="2df00-475">Protocole</span><span class="sxs-lookup"><span data-stu-id="2df00-475">Protocol</span></span></th>
<th><span data-ttu-id="2df00-476">Notes</span><span class="sxs-lookup"><span data-stu-id="2df00-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df00-477">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-478">67/68</span><span class="sxs-lookup"><span data-stu-id="2df00-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="2df00-479">SERVICE</span><span class="sxs-lookup"><span data-stu-id="2df00-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-480">Utilisé par Lync Server pour rechercher le nom de domaine complet du serveur d’inscriptions (en d’autres points, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).</span><span class="sxs-lookup"><span data-stu-id="2df00-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-481">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-482">443</span><span class="sxs-lookup"><span data-stu-id="2df00-482">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-484">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="2df00-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-485">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-486">443</span><span class="sxs-lookup"><span data-stu-id="2df00-486">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-488">Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.</span><span class="sxs-lookup"><span data-stu-id="2df00-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-489">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-490">443</span><span class="sxs-lookup"><span data-stu-id="2df00-490">443</span></span></p></td>
<td><p><span data-ttu-id="2df00-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="2df00-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="2df00-492">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</span><span class="sxs-lookup"><span data-stu-id="2df00-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-493">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-494">3478</span><span class="sxs-lookup"><span data-stu-id="2df00-494">3478</span></span></p></td>
<td><p><span data-ttu-id="2df00-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="2df00-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="2df00-496">Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)</span><span class="sxs-lookup"><span data-stu-id="2df00-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-497">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-498">5061</span><span class="sxs-lookup"><span data-stu-id="2df00-498">5061</span></span></p></td>
<td><p><span data-ttu-id="2df00-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2df00-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="2df00-500">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="2df00-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-501">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="2df00-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="2df00-503">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-504">Utilisé pour le transfert de fichiers entre les clients Lync et les clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="2df00-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-505">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2df00-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2df00-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2df00-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-508">Plage de ports audio (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="2df00-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-509">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2df00-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2df00-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2df00-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="2df00-512">Plage de ports vidéo (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="2df00-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-513">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2df00-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2df00-515">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-516">Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</span><span class="sxs-lookup"><span data-stu-id="2df00-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df00-517">Clients</span><span class="sxs-lookup"><span data-stu-id="2df00-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="2df00-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="2df00-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="2df00-519">TCP</span><span class="sxs-lookup"><span data-stu-id="2df00-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-520">Partage d’application.</span><span class="sxs-lookup"><span data-stu-id="2df00-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df00-521">Téléphone de partie commune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="2df00-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="2df00-522">Téléphone de bureau Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="2df00-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="2df00-523">Téléphone IP HP 4110 (téléphone de partie commune)</span><span class="sxs-lookup"><span data-stu-id="2df00-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="2df00-524">Téléphone IP HP 4120 (téléphone de bureau)</span><span class="sxs-lookup"><span data-stu-id="2df00-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="2df00-525">Téléphone de partie commune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="2df00-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="2df00-526">Téléphone de bureau IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="2df00-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="2df00-527">Téléphone de bureau IP CX700</span><span class="sxs-lookup"><span data-stu-id="2df00-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="2df00-528">Téléphone de conférence IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="2df00-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="2df00-529">67/68</span><span class="sxs-lookup"><span data-stu-id="2df00-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="2df00-530">SERVICE</span><span class="sxs-lookup"><span data-stu-id="2df00-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="2df00-531">Utilisé par les appareils mentionnés pour rechercher le certificat Lync Server, le nom de domaine complet (FQDN) de mise en service et le nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="2df00-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2df00-532">**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres clientmediaportrangeenabled, ClientMediaPort et ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="2df00-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2df00-533">Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu de système d’exploitation requises sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="2df00-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2df00-534">Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).</span><span class="sxs-lookup"><span data-stu-id="2df00-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

