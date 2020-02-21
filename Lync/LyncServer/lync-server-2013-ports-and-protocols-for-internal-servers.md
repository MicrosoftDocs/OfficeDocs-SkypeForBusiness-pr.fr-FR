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
ms.openlocfilehash: 42f40265cf7b8fff7fd6cbf3d4f67a2fb9f558fa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="43e0e-102">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43e0e-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43e0e-103">_**Dernière modification de la rubrique :** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="43e0e-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="43e0e-104">Cette section récapitule les ports et les protocoles utilisés par les serveurs, les programmes d’équilibrage de charge et les clients dans un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43e0e-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43e0e-105">Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="43e0e-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="43e0e-106">Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu.</span><span class="sxs-lookup"><span data-stu-id="43e0e-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="43e0e-107">Le IMMCU est un composant de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="43e0e-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="43e0e-108">La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="43e0e-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="43e0e-109">La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="43e0e-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="43e0e-110">Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.</span><span class="sxs-lookup"><span data-stu-id="43e0e-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="43e0e-111">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="43e0e-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43e0e-112">Le pare-feu Windows doit être en cours d’exécution avant de démarrer les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="43e0e-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="43e0e-113">Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43e0e-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="43e0e-114">Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.</span><span class="sxs-lookup"><span data-stu-id="43e0e-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="43e0e-115">Ports de serveurs requis (par rôle serveur)</span><span class="sxs-lookup"><span data-stu-id="43e0e-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="43e0e-116">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="43e0e-116">Server role</span></span></th>
<th><span data-ttu-id="43e0e-117">Nom du service</span><span class="sxs-lookup"><span data-stu-id="43e0e-117">Service name</span></span></th>
<th><span data-ttu-id="43e0e-118">Port</span><span class="sxs-lookup"><span data-stu-id="43e0e-118">Port</span></span></th>
<th><span data-ttu-id="43e0e-119">Protocole</span><span class="sxs-lookup"><span data-stu-id="43e0e-119">Protocol</span></span></th>
<th><span data-ttu-id="43e0e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="43e0e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-121">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="43e0e-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="43e0e-123">1434</span><span class="sxs-lookup"><span data-stu-id="43e0e-123">1434</span></span></p></td>
<td><p><span data-ttu-id="43e0e-124">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="43e0e-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-125">SQL Browser pour la copie répliquée locale de la base de données du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="43e0e-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-126">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-127">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-128">5060</span><span class="sxs-lookup"><span data-stu-id="43e0e-128">5060</span></span></p></td>
<td><p><span data-ttu-id="43e0e-129">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-130">Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="43e0e-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-131">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-132">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-133">5061</span><span class="sxs-lookup"><span data-stu-id="43e0e-133">5061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-p102">Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS). Également utilisé pour les communications avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="43e0e-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-137">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-138">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-139">444</span><span class="sxs-lookup"><span data-stu-id="43e0e-139">444</span></span></p></td>
<td><p><span data-ttu-id="43e0e-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-140">HTTPS</span></span></p>
<p><span data-ttu-id="43e0e-141">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-142">Utilisé pour les communications HTTPs entre le focus (le composant Lync Server qui gère l’état des conférences) et les serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="43e0e-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="43e0e-143">Ce port est également utilisé pour les communications TCP entre les serveurs Survivable Branch Appliances et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="43e0e-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-144">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-145">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-146">135</span><span class="sxs-lookup"><span data-stu-id="43e0e-146">135</span></span></p></td>
<td><p><span data-ttu-id="43e0e-147">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="43e0e-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-148">Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="43e0e-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-149">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-150">Service de conférence par messagerie instantanée Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-151">5062</span><span class="sxs-lookup"><span data-stu-id="43e0e-151">5062</span></span></p></td>
<td><p><span data-ttu-id="43e0e-152">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-153">Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="43e0e-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-154">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-155">Service de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-156">8057</span><span class="sxs-lookup"><span data-stu-id="43e0e-156">8057</span></span></p></td>
<td><p><span data-ttu-id="43e0e-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-158">Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="43e0e-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-159">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-160">Service de compatibilité de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-161">8058</span><span class="sxs-lookup"><span data-stu-id="43e0e-161">8058</span></span></p></td>
<td><p><span data-ttu-id="43e0e-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-163">Utilisé pour l’écoute des connexions PSOM (persistent Shared Object Model) à partir du client Live Meeting et des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43e0e-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-164">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-165">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-166">5063</span><span class="sxs-lookup"><span data-stu-id="43e0e-166">5063</span></span></p></td>
<td><p><span data-ttu-id="43e0e-167">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-168">Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="43e0e-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-169">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-170">Service de conférence audio/vidéo Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="43e0e-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="43e0e-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43e0e-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-173">Plage de ports multimédias utilisée pour les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="43e0e-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-174">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-175">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-176">80</span><span class="sxs-lookup"><span data-stu-id="43e0e-176">80</span></span></p></td>
<td><p><span data-ttu-id="43e0e-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="43e0e-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-178">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS) lorsque HTTPS n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-179">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-180">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-181">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-181">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="43e0e-183">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="43e0e-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-184">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-185">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-186">8080</span><span class="sxs-lookup"><span data-stu-id="43e0e-186">8080</span></span></p></td>
<td><p><span data-ttu-id="43e0e-187">TCP et HTTP</span><span class="sxs-lookup"><span data-stu-id="43e0e-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-188">Utilisé par les composants Web pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="43e0e-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-189">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-190">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="43e0e-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-191">4443</span><span class="sxs-lookup"><span data-stu-id="43e0e-191">4443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="43e0e-193">HTTPs (des proxys inverses) et les communications inter-pool frontaux HTTPs pour la connexion au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="43e0e-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-194">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-195">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="43e0e-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-196">8060</span><span class="sxs-lookup"><span data-stu-id="43e0e-196">8060</span></span></p></td>
<td><p><span data-ttu-id="43e0e-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-198">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-199">Composant serveur Web</span><span class="sxs-lookup"><span data-stu-id="43e0e-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-200">8061</span><span class="sxs-lookup"><span data-stu-id="43e0e-200">8061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-202">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-203">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="43e0e-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-204">5086</span><span class="sxs-lookup"><span data-stu-id="43e0e-204">5086</span></span></p></td>
<td><p><span data-ttu-id="43e0e-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-206">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="43e0e-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-207">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-208">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="43e0e-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-209">5087</span><span class="sxs-lookup"><span data-stu-id="43e0e-209">5087</span></span></p></td>
<td><p><span data-ttu-id="43e0e-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-211">Port SIP utilisé par les processus internes des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="43e0e-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-212">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-213">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="43e0e-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="43e0e-214">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-214">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-216">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-217">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="43e0e-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-218">5064</span><span class="sxs-lookup"><span data-stu-id="43e0e-218">5064</span></span></p></td>
<td><p><span data-ttu-id="43e0e-219">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-220">Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="43e0e-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-221">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-222">Service de surveillance de conférence Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="43e0e-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-223">5072</span><span class="sxs-lookup"><span data-stu-id="43e0e-223">5072</span></span></p></td>
<td><p><span data-ttu-id="43e0e-224">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-225">Utilisé pour les demandes SIP entrantes pour le service de surveillance (Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="43e0e-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-226">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-227">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-228">5070</span><span class="sxs-lookup"><span data-stu-id="43e0e-228">5070</span></span></p></td>
<td><p><span data-ttu-id="43e0e-229">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-230">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="43e0e-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-231">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-232">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-233">5067</span><span class="sxs-lookup"><span data-stu-id="43e0e-233">5067</span></span></p></td>
<td><p><span data-ttu-id="43e0e-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-235">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="43e0e-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-236">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-237">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-238">5068</span><span class="sxs-lookup"><span data-stu-id="43e0e-238">5068</span></span></p></td>
<td><p><span data-ttu-id="43e0e-239">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-240">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="43e0e-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-241">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-242">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-243">5081</span><span class="sxs-lookup"><span data-stu-id="43e0e-243">5081</span></span></p></td>
<td><p><span data-ttu-id="43e0e-244">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-245">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="43e0e-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-246">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="43e0e-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-247">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-248">5082</span><span class="sxs-lookup"><span data-stu-id="43e0e-248">5082</span></span></p></td>
<td><p><span data-ttu-id="43e0e-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-250">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="43e0e-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-251">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-252">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-253">5065</span><span class="sxs-lookup"><span data-stu-id="43e0e-253">5065</span></span></p></td>
<td><p><span data-ttu-id="43e0e-254">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-255">Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="43e0e-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-256">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-257">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="43e0e-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="43e0e-259">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-260">Plage de ports multimédias utilisée pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="43e0e-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-261">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-262">Service d’annonce de conférence Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-263">5073</span><span class="sxs-lookup"><span data-stu-id="43e0e-263">5073</span></span></p></td>
<td><p><span data-ttu-id="43e0e-264">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-265">Utilisé pour les demandes SIP entrantes du service d’annonce de conférence Lync Server (c’est-à-dire pour les conférences rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="43e0e-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-266">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-267">service de parcage d’appel Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-268">5075</span><span class="sxs-lookup"><span data-stu-id="43e0e-268">5075</span></span></p></td>
<td><p><span data-ttu-id="43e0e-269">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-270">Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="43e0e-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-271">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-272">Service de test audio Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-273">5076</span><span class="sxs-lookup"><span data-stu-id="43e0e-273">5076</span></span></p></td>
<td><p><span data-ttu-id="43e0e-274">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-275">Utilisé pour les demandes SIP entrantes du service de test audio.</span><span class="sxs-lookup"><span data-stu-id="43e0e-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-276">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-277">Non applicable</span><span class="sxs-lookup"><span data-stu-id="43e0e-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="43e0e-278">5066</span><span class="sxs-lookup"><span data-stu-id="43e0e-278">5066</span></span></p></td>
<td><p><span data-ttu-id="43e0e-279">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-280">Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</span><span class="sxs-lookup"><span data-stu-id="43e0e-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-281">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-282">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-283">5071</span><span class="sxs-lookup"><span data-stu-id="43e0e-283">5071</span></span></p></td>
<td><p><span data-ttu-id="43e0e-284">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-285">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="43e0e-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-286">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-287">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-288">8404</span><span class="sxs-lookup"><span data-stu-id="43e0e-288">8404</span></span></p></td>
<td><p><span data-ttu-id="43e0e-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-290">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="43e0e-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-291">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-292">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-293">5080</span><span class="sxs-lookup"><span data-stu-id="43e0e-293">5080</span></span></p></td>
<td><p><span data-ttu-id="43e0e-294">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-295">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="43e0e-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-296">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="43e0e-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-297">Service de stratégie de bande passante Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-298">448</span><span class="sxs-lookup"><span data-stu-id="43e0e-298">448</span></span></p></td>
<td><p><span data-ttu-id="43e0e-299">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-300">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43e0e-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-301">Serveurs frontaux où réside le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="43e0e-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="43e0e-302">Service de l’agent réplicateur maître Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-303">445</span><span class="sxs-lookup"><span data-stu-id="43e0e-303">445</span></span></p></td>
<td><p><span data-ttu-id="43e0e-304">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-305">Utilisé pour envoyer des données de configuration à partir du magasin central de gestion vers les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43e0e-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-306">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="43e0e-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="43e0e-308">1434</span><span class="sxs-lookup"><span data-stu-id="43e0e-308">1434</span></span></p></td>
<td><p><span data-ttu-id="43e0e-309">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="43e0e-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-310">SQL Browser pour la copie répliquée locale des données du magasin central de gestion dans l’instance SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="43e0e-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-311">Tous les serveurs internes</span><span class="sxs-lookup"><span data-stu-id="43e0e-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-312">Divers</span><span class="sxs-lookup"><span data-stu-id="43e0e-312">Various</span></span></p></td>
<td><p><span data-ttu-id="43e0e-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="43e0e-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="43e0e-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43e0e-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-315">Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="43e0e-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="43e0e-316">Utilisé par tous les serveurs qui terminent l’audio : serveurs frontaux (service de surveillance de conférence Lync Server, service d’annonce de conférence Lync Server et service de conférence audio/vidéo Lync Server) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="43e0e-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-317">Serveurs Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="43e0e-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43e0e-318">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43e0e-319">Utilisé par Lync Server 2013 pour se connecter à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="43e0e-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-320">Directeurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="43e0e-321">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-322">5060</span><span class="sxs-lookup"><span data-stu-id="43e0e-322">5060</span></span></p></td>
<td><p><span data-ttu-id="43e0e-323">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-324">Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="43e0e-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-325">Directeurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="43e0e-326">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-327">444</span><span class="sxs-lookup"><span data-stu-id="43e0e-327">444</span></span></p></td>
<td><p><span data-ttu-id="43e0e-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-328">HTTPS</span></span></p>
<p><span data-ttu-id="43e0e-329">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-330">Communication entre serveurs frontaux et directeurs.</span><span class="sxs-lookup"><span data-stu-id="43e0e-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="43e0e-331">De plus, le certificat client doit être publié (sur les serveurs frontaux) ou validé si le certificat client a déjà été publié.</span><span class="sxs-lookup"><span data-stu-id="43e0e-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-332">Directeurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="43e0e-333">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-334">80</span><span class="sxs-lookup"><span data-stu-id="43e0e-334">80</span></span></p></td>
<td><p><span data-ttu-id="43e0e-335">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-p105">Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="43e0e-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-338">Directeurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="43e0e-339">Service de compatibilité Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-340">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-340">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="43e0e-342">Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs web (URL utilisées par les composants web IIS).</span><span class="sxs-lookup"><span data-stu-id="43e0e-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-343">Directeurs</span><span class="sxs-lookup"><span data-stu-id="43e0e-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="43e0e-344">Service frontal Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-345">5061</span><span class="sxs-lookup"><span data-stu-id="43e0e-345">5061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-346">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-347">Utilisé pour les communications internes entre serveurs et pour les connexions client.</span><span class="sxs-lookup"><span data-stu-id="43e0e-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-348">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="43e0e-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-349">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-350">5070</span><span class="sxs-lookup"><span data-stu-id="43e0e-350">5070</span></span></p></td>
<td><p><span data-ttu-id="43e0e-351">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-352">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="43e0e-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-353">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="43e0e-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-354">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-355">5067</span><span class="sxs-lookup"><span data-stu-id="43e0e-355">5067</span></span></p></td>
<td><p><span data-ttu-id="43e0e-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-357">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="43e0e-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-358">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="43e0e-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-359">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-360">5068</span><span class="sxs-lookup"><span data-stu-id="43e0e-360">5068</span></span></p></td>
<td><p><span data-ttu-id="43e0e-361">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-362">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="43e0e-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-363">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="43e0e-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="43e0e-364">Service de médiation Lync Server</span><span class="sxs-lookup"><span data-stu-id="43e0e-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-365">5070</span><span class="sxs-lookup"><span data-stu-id="43e0e-365">5070</span></span></p></td>
<td><p><span data-ttu-id="43e0e-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-367">Utilisé pour les demandes SIP des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="43e0e-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-368">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43e0e-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-369">SIP de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43e0e-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-370">5041</span><span class="sxs-lookup"><span data-stu-id="43e0e-370">5041</span></span></p></td>
<td><p><span data-ttu-id="43e0e-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-372">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43e0e-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-373">Conversation permanente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="43e0e-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-374">881</span><span class="sxs-lookup"><span data-stu-id="43e0e-374">881</span></span></p></td>
<td><p><span data-ttu-id="43e0e-375">TCP (TLS) et TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-376">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43e0e-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="43e0e-377">Service de transfert de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="43e0e-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="43e0e-378">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-378">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="43e0e-380">Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX.</span><span class="sxs-lookup"><span data-stu-id="43e0e-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="43e0e-381">Bien que Lync Server n’utilise plus le port TCP 5060, pendant le déploiement du contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP que le serveur frontal ou directeur utilisera pour se connecter au système PBX.</span><span class="sxs-lookup"><span data-stu-id="43e0e-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="43e0e-382">Pour plus d’informations, reportez-vous à l’applet de commande <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="43e0e-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="43e0e-383">Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="43e0e-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="43e0e-384">Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé</span><span class="sxs-lookup"><span data-stu-id="43e0e-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43e0e-385">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="43e0e-385">Load Balancer</span></span></th>
<th><span data-ttu-id="43e0e-386">Port</span><span class="sxs-lookup"><span data-stu-id="43e0e-386">Port</span></span></th>
<th><span data-ttu-id="43e0e-387">Protocole</span><span class="sxs-lookup"><span data-stu-id="43e0e-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-388">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-389">5061</span><span class="sxs-lookup"><span data-stu-id="43e0e-389">5061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-391">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-392">444</span><span class="sxs-lookup"><span data-stu-id="43e0e-392">444</span></span></p></td>
<td><p><span data-ttu-id="43e0e-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-394">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-395">135</span><span class="sxs-lookup"><span data-stu-id="43e0e-395">135</span></span></p></td>
<td><p><span data-ttu-id="43e0e-396">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="43e0e-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-397">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-398">80</span><span class="sxs-lookup"><span data-stu-id="43e0e-398">80</span></span></p></td>
<td><p><span data-ttu-id="43e0e-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="43e0e-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-400">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-401">8080</span><span class="sxs-lookup"><span data-stu-id="43e0e-401">8080</span></span></p></td>
<td><p><span data-ttu-id="43e0e-402">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="43e0e-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-403">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-404">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-404">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-406">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-407">4443</span><span class="sxs-lookup"><span data-stu-id="43e0e-407">4443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-408">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="43e0e-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-409">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-410">5072</span><span class="sxs-lookup"><span data-stu-id="43e0e-410">5072</span></span></p></td>
<td><p><span data-ttu-id="43e0e-411">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-412">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-413">5073</span><span class="sxs-lookup"><span data-stu-id="43e0e-413">5073</span></span></p></td>
<td><p><span data-ttu-id="43e0e-414">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-415">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-416">5075</span><span class="sxs-lookup"><span data-stu-id="43e0e-416">5075</span></span></p></td>
<td><p><span data-ttu-id="43e0e-417">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-418">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-419">5076</span><span class="sxs-lookup"><span data-stu-id="43e0e-419">5076</span></span></p></td>
<td><p><span data-ttu-id="43e0e-420">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-421">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-422">5071</span><span class="sxs-lookup"><span data-stu-id="43e0e-422">5071</span></span></p></td>
<td><p><span data-ttu-id="43e0e-423">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-424">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-425">5080</span><span class="sxs-lookup"><span data-stu-id="43e0e-425">5080</span></span></p></td>
<td><p><span data-ttu-id="43e0e-426">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-427">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-428">448</span><span class="sxs-lookup"><span data-stu-id="43e0e-428">448</span></span></p></td>
<td><p><span data-ttu-id="43e0e-429">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-430">Programme d’équilibrage de la charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="43e0e-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-431">5070</span><span class="sxs-lookup"><span data-stu-id="43e0e-431">5070</span></span></p></td>
<td><p><span data-ttu-id="43e0e-432">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-433">Programme d’équilibrage de la charge du serveur frontal (si le pool exécute également le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="43e0e-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-434">5070</span><span class="sxs-lookup"><span data-stu-id="43e0e-434">5070</span></span></p></td>
<td><p><span data-ttu-id="43e0e-435">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-436">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-437">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-437">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-439">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-440">444</span><span class="sxs-lookup"><span data-stu-id="43e0e-440">444</span></span></p></td>
<td><p><span data-ttu-id="43e0e-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-442">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-443">5061</span><span class="sxs-lookup"><span data-stu-id="43e0e-443">5061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-444">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-445">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-446">4443</span><span class="sxs-lookup"><span data-stu-id="43e0e-446">4443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-447">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="43e0e-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="43e0e-p107">Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="43e0e-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="43e0e-450">Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé</span><span class="sxs-lookup"><span data-stu-id="43e0e-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43e0e-451">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="43e0e-451">Load Balancer</span></span></th>
<th><span data-ttu-id="43e0e-452">Port</span><span class="sxs-lookup"><span data-stu-id="43e0e-452">Port</span></span></th>
<th><span data-ttu-id="43e0e-453">Protocole</span><span class="sxs-lookup"><span data-stu-id="43e0e-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-454">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-455">80</span><span class="sxs-lookup"><span data-stu-id="43e0e-455">80</span></span></p></td>
<td><p><span data-ttu-id="43e0e-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="43e0e-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-457">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-458">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-458">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-460">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-461">8080</span><span class="sxs-lookup"><span data-stu-id="43e0e-461">8080</span></span></p></td>
<td><p><span data-ttu-id="43e0e-462">TCP - Récupération client/périphérique du certificat racine depuis le serveur frontal – clients et périphériques authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="43e0e-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-463">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="43e0e-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-464">4443</span><span class="sxs-lookup"><span data-stu-id="43e0e-464">4443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-465">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="43e0e-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-466">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-467">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-467">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="43e0e-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-469">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="43e0e-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="43e0e-470">4443</span><span class="sxs-lookup"><span data-stu-id="43e0e-470">4443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-471">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="43e0e-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="43e0e-472">Ports client requis</span><span class="sxs-lookup"><span data-stu-id="43e0e-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43e0e-473">Composant</span><span class="sxs-lookup"><span data-stu-id="43e0e-473">Component</span></span></th>
<th><span data-ttu-id="43e0e-474">Port</span><span class="sxs-lookup"><span data-stu-id="43e0e-474">Port</span></span></th>
<th><span data-ttu-id="43e0e-475">Protocole</span><span class="sxs-lookup"><span data-stu-id="43e0e-475">Protocol</span></span></th>
<th><span data-ttu-id="43e0e-476">Notes</span><span class="sxs-lookup"><span data-stu-id="43e0e-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-477">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-478">67/68</span><span class="sxs-lookup"><span data-stu-id="43e0e-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="43e0e-479">SERVICE</span><span class="sxs-lookup"><span data-stu-id="43e0e-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-480">Utilisé par Lync Server pour rechercher le nom de domaine complet du serveur d’inscriptions (en d’autres points, si DNS SRV échoue et que les paramètres manuels ne sont pas configurés).</span><span class="sxs-lookup"><span data-stu-id="43e0e-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-481">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-482">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-482">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-484">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="43e0e-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-485">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-486">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-486">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-488">Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence web.</span><span class="sxs-lookup"><span data-stu-id="43e0e-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-489">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-490">443</span><span class="sxs-lookup"><span data-stu-id="43e0e-490">443</span></span></p></td>
<td><p><span data-ttu-id="43e0e-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="43e0e-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-492">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</span><span class="sxs-lookup"><span data-stu-id="43e0e-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-493">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-494">3478</span><span class="sxs-lookup"><span data-stu-id="43e0e-494">3478</span></span></p></td>
<td><p><span data-ttu-id="43e0e-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="43e0e-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-496">Utilisé pour l’accès des utilisateurs externes aux sessions A/V et aux médias (UDP)</span><span class="sxs-lookup"><span data-stu-id="43e0e-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-497">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-498">5061</span><span class="sxs-lookup"><span data-stu-id="43e0e-498">5061</span></span></p></td>
<td><p><span data-ttu-id="43e0e-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="43e0e-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="43e0e-500">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="43e0e-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-501">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="43e0e-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="43e0e-503">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-504">Utilisé pour le transfert de fichiers entre les clients Lync et les clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="43e0e-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-505">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="43e0e-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="43e0e-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43e0e-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-508">Plage de ports audio (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="43e0e-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-509">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="43e0e-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="43e0e-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43e0e-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-512">Plage de ports vidéo (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="43e0e-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-513">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="43e0e-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="43e0e-515">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-516">Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</span><span class="sxs-lookup"><span data-stu-id="43e0e-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e0e-517">Clients</span><span class="sxs-lookup"><span data-stu-id="43e0e-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="43e0e-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="43e0e-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="43e0e-519">TCP</span><span class="sxs-lookup"><span data-stu-id="43e0e-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-520">Partage d’application.</span><span class="sxs-lookup"><span data-stu-id="43e0e-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e0e-521">Téléphone de partie commune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="43e0e-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="43e0e-522">Téléphone de bureau Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="43e0e-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="43e0e-523">Téléphone IP HP 4110 (téléphone de partie commune)</span><span class="sxs-lookup"><span data-stu-id="43e0e-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="43e0e-524">Téléphone IP HP 4120 (téléphone de bureau)</span><span class="sxs-lookup"><span data-stu-id="43e0e-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="43e0e-525">Téléphone de partie commune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="43e0e-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="43e0e-526">Téléphone de bureau IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="43e0e-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="43e0e-527">Téléphone de bureau IP CX700</span><span class="sxs-lookup"><span data-stu-id="43e0e-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="43e0e-528">Téléphone de conférence IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="43e0e-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="43e0e-529">67/68</span><span class="sxs-lookup"><span data-stu-id="43e0e-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="43e0e-530">SERVICE</span><span class="sxs-lookup"><span data-stu-id="43e0e-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="43e0e-531">Utilisé par les appareils mentionnés pour rechercher le certificat Lync Server, le nom de domaine complet (FQDN) de mise en service et le nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="43e0e-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="43e0e-532">**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de commande CsConferencingConfiguration (paramètres paramètres clientmediaportrangeenabled, ClientMediaPort et ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="43e0e-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43e0e-533">Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu de système d’exploitation requises sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="43e0e-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="43e0e-534">Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).</span><span class="sxs-lookup"><span data-stu-id="43e0e-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

