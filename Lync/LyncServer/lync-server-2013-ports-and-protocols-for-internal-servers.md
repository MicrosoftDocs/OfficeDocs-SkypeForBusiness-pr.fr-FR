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
ms.openlocfilehash: 8f730a0af21abfbff8058aa51c1163c1dae1ff3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="af267-102">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af267-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af267-103">_**Dernière modification de la rubrique :** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="af267-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="af267-104">Cette section récapitule les ports et les protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af267-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af267-105">Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="af267-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="af267-106">Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu.</span><span class="sxs-lookup"><span data-stu-id="af267-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="af267-107">Le IMMCU est un composant de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="af267-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="af267-108">La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="af267-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="af267-109">La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="af267-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="af267-110">Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.</span><span class="sxs-lookup"><span data-stu-id="af267-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="af267-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="af267-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af267-112">Le pare-feu Windows doit être en cours d’exécution avant de démarrer les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="af267-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="af267-113">Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af267-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="af267-114">Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.</span><span class="sxs-lookup"><span data-stu-id="af267-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="af267-115">Ports de serveurs requis (par rôle serveur)</span><span class="sxs-lookup"><span data-stu-id="af267-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="af267-116">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="af267-116">Server role</span></span></th>
<th><span data-ttu-id="af267-117">Nom du service</span><span class="sxs-lookup"><span data-stu-id="af267-117">Service name</span></span></th>
<th><span data-ttu-id="af267-118">Port</span><span class="sxs-lookup"><span data-stu-id="af267-118">Port</span></span></th>
<th><span data-ttu-id="af267-119">Protocole</span><span class="sxs-lookup"><span data-stu-id="af267-119">Protocol</span></span></th>
<th><span data-ttu-id="af267-120">Notes</span><span class="sxs-lookup"><span data-stu-id="af267-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af267-121">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="af267-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="af267-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="af267-123">1434</span><span class="sxs-lookup"><span data-stu-id="af267-123">1434</span></span></p></td>
<td><p><span data-ttu-id="af267-124">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="af267-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-125">SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="af267-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-126">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-127">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-128">5060</span><span class="sxs-lookup"><span data-stu-id="af267-128">5060</span></span></p></td>
<td><p><span data-ttu-id="af267-129">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-130">Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="af267-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-131">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-132">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-133">5061</span><span class="sxs-lookup"><span data-stu-id="af267-133">5061</span></span></p></td>
<td><p><span data-ttu-id="af267-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-p102">Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="af267-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-137">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-138">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-139">444</span><span class="sxs-lookup"><span data-stu-id="af267-139">444</span></span></p></td>
<td><p><span data-ttu-id="af267-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-140">HTTPS</span></span></p>
<p><span data-ttu-id="af267-141">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-142">Utilisé pour les communications HTTPs entre le focus (le composant Lync Server qui gère l’état des conférences) et les serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="af267-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="af267-143">Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliances et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="af267-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-144">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-145">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-146">135</span><span class="sxs-lookup"><span data-stu-id="af267-146">135</span></span></p></td>
<td><p><span data-ttu-id="af267-147">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="af267-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="af267-148">Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="af267-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-149">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-150">Service de conférence par messagerie instantanée Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="af267-151">5062</span><span class="sxs-lookup"><span data-stu-id="af267-151">5062</span></span></p></td>
<td><p><span data-ttu-id="af267-152">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-153">Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="af267-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-154">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-155">Service de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="af267-156">8057</span><span class="sxs-lookup"><span data-stu-id="af267-156">8057</span></span></p></td>
<td><p><span data-ttu-id="af267-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-158">Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="af267-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-159">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-160">Service de compatibilité de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-161">8058</span><span class="sxs-lookup"><span data-stu-id="af267-161">8058</span></span></p></td>
<td><p><span data-ttu-id="af267-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-163">Utilisé pour l’écoute des connexions PSOM (persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af267-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-164">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-165">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="af267-166">5063</span><span class="sxs-lookup"><span data-stu-id="af267-166">5063</span></span></p></td>
<td><p><span data-ttu-id="af267-167">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-168">Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="af267-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-169">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-170">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="af267-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="af267-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="af267-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af267-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-173">Plage de ports multimédias utilisée pour les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="af267-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-174">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-175">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-176">80</span><span class="sxs-lookup"><span data-stu-id="af267-176">80</span></span></p></td>
<td><p><span data-ttu-id="af267-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="af267-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="af267-178">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="af267-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-179">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-180">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-181">443</span><span class="sxs-lookup"><span data-stu-id="af267-181">443</span></span></p></td>
<td><p><span data-ttu-id="af267-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="af267-183">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="af267-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-184">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-185">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-186">8080</span><span class="sxs-lookup"><span data-stu-id="af267-186">8080</span></span></p></td>
<td><p><span data-ttu-id="af267-187">TCP et HTTP</span><span class="sxs-lookup"><span data-stu-id="af267-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="af267-188">Utilisé par les composants Web pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="af267-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-189">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-190">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="af267-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="af267-191">4443</span><span class="sxs-lookup"><span data-stu-id="af267-191">4443</span></span></p></td>
<td><p><span data-ttu-id="af267-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="af267-193">HTTPs (des proxys inverses) et les communications inter-pool frontaux HTTPs pour la connexion au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="af267-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-194">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-195">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="af267-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="af267-196">8060</span><span class="sxs-lookup"><span data-stu-id="af267-196">8060</span></span></p></td>
<td><p><span data-ttu-id="af267-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-198">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-199">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="af267-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="af267-200">8061</span><span class="sxs-lookup"><span data-stu-id="af267-200">8061</span></span></p></td>
<td><p><span data-ttu-id="af267-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-202">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-203">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="af267-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="af267-204">5086</span><span class="sxs-lookup"><span data-stu-id="af267-204">5086</span></span></p></td>
<td><p><span data-ttu-id="af267-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-206">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="af267-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-207">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-208">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="af267-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="af267-209">5087</span><span class="sxs-lookup"><span data-stu-id="af267-209">5087</span></span></p></td>
<td><p><span data-ttu-id="af267-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-211">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="af267-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-212">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-213">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="af267-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="af267-214">443</span><span class="sxs-lookup"><span data-stu-id="af267-214">443</span></span></p></td>
<td><p><span data-ttu-id="af267-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-216">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-217">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="af267-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="af267-218">5064</span><span class="sxs-lookup"><span data-stu-id="af267-218">5064</span></span></p></td>
<td><p><span data-ttu-id="af267-219">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-220">Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="af267-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-221">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-222">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="af267-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="af267-223">5072</span><span class="sxs-lookup"><span data-stu-id="af267-223">5072</span></span></p></td>
<td><p><span data-ttu-id="af267-224">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-225">Utilisé pour les demandes SIP entrantes pour le service de surveillance (Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="af267-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-226">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="af267-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="af267-227">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-228">5070</span><span class="sxs-lookup"><span data-stu-id="af267-228">5070</span></span></p></td>
<td><p><span data-ttu-id="af267-229">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-230">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="af267-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-231">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="af267-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="af267-232">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-233">5067</span><span class="sxs-lookup"><span data-stu-id="af267-233">5067</span></span></p></td>
<td><p><span data-ttu-id="af267-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-235">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="af267-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-236">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="af267-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="af267-237">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-238">5068</span><span class="sxs-lookup"><span data-stu-id="af267-238">5068</span></span></p></td>
<td><p><span data-ttu-id="af267-239">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-240">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="af267-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-241">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="af267-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="af267-242">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-243">5081</span><span class="sxs-lookup"><span data-stu-id="af267-243">5081</span></span></p></td>
<td><p><span data-ttu-id="af267-244">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-245">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="af267-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-246">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="af267-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="af267-247">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-248">5082</span><span class="sxs-lookup"><span data-stu-id="af267-248">5082</span></span></p></td>
<td><p><span data-ttu-id="af267-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-250">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="af267-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-251">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-252">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="af267-253">5065</span><span class="sxs-lookup"><span data-stu-id="af267-253">5065</span></span></p></td>
<td><p><span data-ttu-id="af267-254">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-255">Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="af267-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-256">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-257">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="af267-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="af267-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="af267-259">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-260">Plage de ports multimédias utilisée pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="af267-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-261">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-262">Service d’annonce de conférence Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="af267-263">5073</span><span class="sxs-lookup"><span data-stu-id="af267-263">5073</span></span></p></td>
<td><p><span data-ttu-id="af267-264">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-265">Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Lync Server (c’est-à-dire pour les conférences rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="af267-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-266">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-267">service de parcage d’appel Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="af267-268">5075</span><span class="sxs-lookup"><span data-stu-id="af267-268">5075</span></span></p></td>
<td><p><span data-ttu-id="af267-269">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-270">Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="af267-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-271">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-272">Service de test audio Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="af267-273">5076</span><span class="sxs-lookup"><span data-stu-id="af267-273">5076</span></span></p></td>
<td><p><span data-ttu-id="af267-274">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-275">Utilisé pour les demandes SIP entrantes du service de test audio.</span><span class="sxs-lookup"><span data-stu-id="af267-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-276">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-277">Non applicable</span><span class="sxs-lookup"><span data-stu-id="af267-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="af267-278">5066</span><span class="sxs-lookup"><span data-stu-id="af267-278">5066</span></span></p></td>
<td><p><span data-ttu-id="af267-279">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-280">Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</span><span class="sxs-lookup"><span data-stu-id="af267-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-281">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-282">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="af267-283">5071</span><span class="sxs-lookup"><span data-stu-id="af267-283">5071</span></span></p></td>
<td><p><span data-ttu-id="af267-284">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-285">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="af267-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-286">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-287">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="af267-288">8404</span><span class="sxs-lookup"><span data-stu-id="af267-288">8404</span></span></p></td>
<td><p><span data-ttu-id="af267-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-290">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="af267-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-291">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-292">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="af267-293">5080</span><span class="sxs-lookup"><span data-stu-id="af267-293">5080</span></span></p></td>
<td><p><span data-ttu-id="af267-294">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-295">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="af267-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-296">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="af267-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-297">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="af267-298">448</span><span class="sxs-lookup"><span data-stu-id="af267-298">448</span></span></p></td>
<td><p><span data-ttu-id="af267-299">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-300">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af267-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-301">Serveurs frontaux où réside le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="af267-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="af267-302">Service de l’agent réplicateur maître Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="af267-303">445</span><span class="sxs-lookup"><span data-stu-id="af267-303">445</span></span></p></td>
<td><p><span data-ttu-id="af267-304">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-305">Utilisé pour envoyer des données de configuration à partir du magasin central de gestion vers les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af267-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-306">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="af267-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="af267-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="af267-308">1434</span><span class="sxs-lookup"><span data-stu-id="af267-308">1434</span></span></p></td>
<td><p><span data-ttu-id="af267-309">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="af267-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-310">SQL Browser pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="af267-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-311">Tous les serveurs internes</span><span class="sxs-lookup"><span data-stu-id="af267-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="af267-312">Divers</span><span class="sxs-lookup"><span data-stu-id="af267-312">Various</span></span></p></td>
<td><p><span data-ttu-id="af267-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="af267-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="af267-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af267-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-315">Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="af267-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="af267-316">Utilisé par tous les serveurs qui terminent l’audio : serveurs frontaux (service de surveillance de conférence Lync Server, service d’annonce de conférence Lync Server et service de conférence audio/vidéo Lync Server) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="af267-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-317">Serveurs Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="af267-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af267-318">443</span><span class="sxs-lookup"><span data-stu-id="af267-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="af267-319">Utilisé par Lync Server 2013 pour se connecter à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="af267-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-320">Directeurs</span><span class="sxs-lookup"><span data-stu-id="af267-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="af267-321">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-322">5060</span><span class="sxs-lookup"><span data-stu-id="af267-322">5060</span></span></p></td>
<td><p><span data-ttu-id="af267-323">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-324">Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="af267-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-325">Directeurs</span><span class="sxs-lookup"><span data-stu-id="af267-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="af267-326">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-327">444</span><span class="sxs-lookup"><span data-stu-id="af267-327">444</span></span></p></td>
<td><p><span data-ttu-id="af267-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-328">HTTPS</span></span></p>
<p><span data-ttu-id="af267-329">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-330">Communication entre serveurs frontaux et directeurs.</span><span class="sxs-lookup"><span data-stu-id="af267-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="af267-331">De plus, le certificat client doit être publié (sur les serveurs frontaux) ou validé si le certificat client a déjà été publié.</span><span class="sxs-lookup"><span data-stu-id="af267-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-332">Directeurs</span><span class="sxs-lookup"><span data-stu-id="af267-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="af267-333">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-334">80</span><span class="sxs-lookup"><span data-stu-id="af267-334">80</span></span></p></td>
<td><p><span data-ttu-id="af267-335">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-p105">Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="af267-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-338">Directeurs</span><span class="sxs-lookup"><span data-stu-id="af267-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="af267-339">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="af267-340">443</span><span class="sxs-lookup"><span data-stu-id="af267-340">443</span></span></p></td>
<td><p><span data-ttu-id="af267-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="af267-342">Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="af267-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-343">Directeurs</span><span class="sxs-lookup"><span data-stu-id="af267-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="af267-344">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="af267-345">5061</span><span class="sxs-lookup"><span data-stu-id="af267-345">5061</span></span></p></td>
<td><p><span data-ttu-id="af267-346">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-347">Utilisé pour les communications internes entre serveurs et pour les connexions client.</span><span class="sxs-lookup"><span data-stu-id="af267-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-348">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="af267-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-349">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-350">5070</span><span class="sxs-lookup"><span data-stu-id="af267-350">5070</span></span></p></td>
<td><p><span data-ttu-id="af267-351">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-352">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="af267-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-353">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="af267-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-354">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-355">5067</span><span class="sxs-lookup"><span data-stu-id="af267-355">5067</span></span></p></td>
<td><p><span data-ttu-id="af267-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-357">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="af267-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-358">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="af267-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-359">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-360">5068</span><span class="sxs-lookup"><span data-stu-id="af267-360">5068</span></span></p></td>
<td><p><span data-ttu-id="af267-361">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-362">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="af267-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-363">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="af267-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="af267-364">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="af267-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="af267-365">5070</span><span class="sxs-lookup"><span data-stu-id="af267-365">5070</span></span></p></td>
<td><p><span data-ttu-id="af267-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-367">Utilisé pour les demandes SIP des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="af267-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-368">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="af267-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="af267-369">SIP de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="af267-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="af267-370">5041</span><span class="sxs-lookup"><span data-stu-id="af267-370">5041</span></span></p></td>
<td><p><span data-ttu-id="af267-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-372">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="af267-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="af267-373">Conversation permanente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="af267-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="af267-374">881</span><span class="sxs-lookup"><span data-stu-id="af267-374">881</span></span></p></td>
<td><p><span data-ttu-id="af267-375">TCP (TLS) et TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-376">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="af267-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="af267-377">Service de transfert de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="af267-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="af267-378">443</span><span class="sxs-lookup"><span data-stu-id="af267-378">443</span></span></p></td>
<td><p><span data-ttu-id="af267-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="af267-380">Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX.</span><span class="sxs-lookup"><span data-stu-id="af267-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="af267-381">Bien que Lync Server n’utilise plus le port TCP 5060, pendant le déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou directeur utilisera pour se connecter au système PBX.</span><span class="sxs-lookup"><span data-stu-id="af267-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="af267-382">Pour plus d’informations, reportez-vous à l’applet de commande <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="af267-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="af267-383">Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="af267-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="af267-384">Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé</span><span class="sxs-lookup"><span data-stu-id="af267-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af267-385">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="af267-385">Load Balancer</span></span></th>
<th><span data-ttu-id="af267-386">Port</span><span class="sxs-lookup"><span data-stu-id="af267-386">Port</span></span></th>
<th><span data-ttu-id="af267-387">Protocole</span><span class="sxs-lookup"><span data-stu-id="af267-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af267-388">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-389">5061</span><span class="sxs-lookup"><span data-stu-id="af267-389">5061</span></span></p></td>
<td><p><span data-ttu-id="af267-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-391">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-392">444</span><span class="sxs-lookup"><span data-stu-id="af267-392">444</span></span></p></td>
<td><p><span data-ttu-id="af267-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-394">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-395">135</span><span class="sxs-lookup"><span data-stu-id="af267-395">135</span></span></p></td>
<td><p><span data-ttu-id="af267-396">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="af267-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-397">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-398">80</span><span class="sxs-lookup"><span data-stu-id="af267-398">80</span></span></p></td>
<td><p><span data-ttu-id="af267-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="af267-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-400">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-401">8080</span><span class="sxs-lookup"><span data-stu-id="af267-401">8080</span></span></p></td>
<td><p><span data-ttu-id="af267-402">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="af267-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-403">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-404">443</span><span class="sxs-lookup"><span data-stu-id="af267-404">443</span></span></p></td>
<td><p><span data-ttu-id="af267-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-406">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-407">4443</span><span class="sxs-lookup"><span data-stu-id="af267-407">4443</span></span></p></td>
<td><p><span data-ttu-id="af267-408">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="af267-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-409">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-410">5072</span><span class="sxs-lookup"><span data-stu-id="af267-410">5072</span></span></p></td>
<td><p><span data-ttu-id="af267-411">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-412">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-413">5073</span><span class="sxs-lookup"><span data-stu-id="af267-413">5073</span></span></p></td>
<td><p><span data-ttu-id="af267-414">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-415">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-416">5075</span><span class="sxs-lookup"><span data-stu-id="af267-416">5075</span></span></p></td>
<td><p><span data-ttu-id="af267-417">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-418">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-419">5076</span><span class="sxs-lookup"><span data-stu-id="af267-419">5076</span></span></p></td>
<td><p><span data-ttu-id="af267-420">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-421">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-422">5071</span><span class="sxs-lookup"><span data-stu-id="af267-422">5071</span></span></p></td>
<td><p><span data-ttu-id="af267-423">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-424">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-425">5080</span><span class="sxs-lookup"><span data-stu-id="af267-425">5080</span></span></p></td>
<td><p><span data-ttu-id="af267-426">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-427">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-428">448</span><span class="sxs-lookup"><span data-stu-id="af267-428">448</span></span></p></td>
<td><p><span data-ttu-id="af267-429">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-430">Programme d’équilibrage de la charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="af267-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-431">5070</span><span class="sxs-lookup"><span data-stu-id="af267-431">5070</span></span></p></td>
<td><p><span data-ttu-id="af267-432">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-433">Programme d’équilibrage de la charge du serveur frontal (si le pool exécute également le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="af267-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="af267-434">5070</span><span class="sxs-lookup"><span data-stu-id="af267-434">5070</span></span></p></td>
<td><p><span data-ttu-id="af267-435">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-436">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-437">443</span><span class="sxs-lookup"><span data-stu-id="af267-437">443</span></span></p></td>
<td><p><span data-ttu-id="af267-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-439">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-440">444</span><span class="sxs-lookup"><span data-stu-id="af267-440">444</span></span></p></td>
<td><p><span data-ttu-id="af267-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-442">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-443">5061</span><span class="sxs-lookup"><span data-stu-id="af267-443">5061</span></span></p></td>
<td><p><span data-ttu-id="af267-444">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-445">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-446">4443</span><span class="sxs-lookup"><span data-stu-id="af267-446">4443</span></span></p></td>
<td><p><span data-ttu-id="af267-447">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="af267-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af267-p107">Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="af267-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="af267-450">Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé</span><span class="sxs-lookup"><span data-stu-id="af267-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af267-451">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="af267-451">Load Balancer</span></span></th>
<th><span data-ttu-id="af267-452">Port</span><span class="sxs-lookup"><span data-stu-id="af267-452">Port</span></span></th>
<th><span data-ttu-id="af267-453">Protocole</span><span class="sxs-lookup"><span data-stu-id="af267-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af267-454">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-455">80</span><span class="sxs-lookup"><span data-stu-id="af267-455">80</span></span></p></td>
<td><p><span data-ttu-id="af267-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="af267-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-457">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-458">443</span><span class="sxs-lookup"><span data-stu-id="af267-458">443</span></span></p></td>
<td><p><span data-ttu-id="af267-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-460">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-461">8080</span><span class="sxs-lookup"><span data-stu-id="af267-461">8080</span></span></p></td>
<td><p><span data-ttu-id="af267-462">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="af267-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-463">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af267-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-464">4443</span><span class="sxs-lookup"><span data-stu-id="af267-464">4443</span></span></p></td>
<td><p><span data-ttu-id="af267-465">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="af267-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-466">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-467">443</span><span class="sxs-lookup"><span data-stu-id="af267-467">443</span></span></p></td>
<td><p><span data-ttu-id="af267-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="af267-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-469">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="af267-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="af267-470">4443</span><span class="sxs-lookup"><span data-stu-id="af267-470">4443</span></span></p></td>
<td><p><span data-ttu-id="af267-471">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="af267-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="af267-472">Ports client requis</span><span class="sxs-lookup"><span data-stu-id="af267-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af267-473">Composant</span><span class="sxs-lookup"><span data-stu-id="af267-473">Component</span></span></th>
<th><span data-ttu-id="af267-474">Port</span><span class="sxs-lookup"><span data-stu-id="af267-474">Port</span></span></th>
<th><span data-ttu-id="af267-475">Protocole</span><span class="sxs-lookup"><span data-stu-id="af267-475">Protocol</span></span></th>
<th><span data-ttu-id="af267-476">Notes</span><span class="sxs-lookup"><span data-stu-id="af267-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af267-477">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-478">67/68</span><span class="sxs-lookup"><span data-stu-id="af267-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="af267-479">SERVICE</span><span class="sxs-lookup"><span data-stu-id="af267-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="af267-480">Utilisé par Lync Server pour rechercher le nom de domaine complet du serveur d’inscriptions (en d’autres points, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).</span><span class="sxs-lookup"><span data-stu-id="af267-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-481">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-482">443</span><span class="sxs-lookup"><span data-stu-id="af267-482">443</span></span></p></td>
<td><p><span data-ttu-id="af267-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-484">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="af267-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-485">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-486">443</span><span class="sxs-lookup"><span data-stu-id="af267-486">443</span></span></p></td>
<td><p><span data-ttu-id="af267-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="af267-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-488">Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.</span><span class="sxs-lookup"><span data-stu-id="af267-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-489">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-490">443</span><span class="sxs-lookup"><span data-stu-id="af267-490">443</span></span></p></td>
<td><p><span data-ttu-id="af267-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="af267-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="af267-492">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</span><span class="sxs-lookup"><span data-stu-id="af267-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-493">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-494">3478</span><span class="sxs-lookup"><span data-stu-id="af267-494">3478</span></span></p></td>
<td><p><span data-ttu-id="af267-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="af267-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="af267-496">Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)</span><span class="sxs-lookup"><span data-stu-id="af267-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-497">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-498">5061</span><span class="sxs-lookup"><span data-stu-id="af267-498">5061</span></span></p></td>
<td><p><span data-ttu-id="af267-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="af267-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="af267-500">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="af267-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-501">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="af267-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="af267-503">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-504">Utilisé pour le transfert de fichiers entre les clients Lync et les clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="af267-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-505">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="af267-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="af267-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af267-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-508">Plage de ports audio (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="af267-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-509">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="af267-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="af267-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af267-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="af267-512">Plage de ports vidéo (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="af267-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-513">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="af267-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="af267-515">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-516">Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</span><span class="sxs-lookup"><span data-stu-id="af267-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af267-517">Clients</span><span class="sxs-lookup"><span data-stu-id="af267-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="af267-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="af267-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="af267-519">TCP</span><span class="sxs-lookup"><span data-stu-id="af267-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="af267-520">Partage d’application.</span><span class="sxs-lookup"><span data-stu-id="af267-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af267-521">Téléphone de partie commune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="af267-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="af267-522">Téléphone de bureau Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="af267-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="af267-523">Téléphone IP HP 4110 (téléphone de partie commune)</span><span class="sxs-lookup"><span data-stu-id="af267-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="af267-524">Téléphone IP HP 4120 (téléphone de bureau)</span><span class="sxs-lookup"><span data-stu-id="af267-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="af267-525">Téléphone de partie commune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="af267-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="af267-526">Téléphone de bureau IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="af267-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="af267-527">Téléphone de bureau IP CX700</span><span class="sxs-lookup"><span data-stu-id="af267-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="af267-528">Téléphone de conférence IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="af267-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="af267-529">67/68</span><span class="sxs-lookup"><span data-stu-id="af267-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="af267-530">SERVICE</span><span class="sxs-lookup"><span data-stu-id="af267-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="af267-531">Utilisé par les appareils mentionnés pour rechercher le certificat Lync Server, le nom de domaine complet (FQDN) de mise en service et le nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="af267-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af267-532">**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres clientmediaportrangeenabled, ClientMediaPort et ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="af267-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af267-533">Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu de système d’exploitation requises sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="af267-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="af267-534">Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).</span><span class="sxs-lookup"><span data-stu-id="af267-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

