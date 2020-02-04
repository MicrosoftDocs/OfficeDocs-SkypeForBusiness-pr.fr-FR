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
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ba7fc-102">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba7fc-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba7fc-103">_**Dernière modification de la rubrique :** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="ba7fc-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="ba7fc-104">Cette section résume les ports et les protocoles utilisés par les serveurs, les équilibreurs de charge et les clients dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ba7fc-105">Les clients Lync et Communicator intervenant dans le cadre d’une communication une à une, sont souvent désignés sous le nom d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="ba7fc-106">Techniquement, les deux clients communiquent en une seule conversation avec l’unité de contrôle multipoint (IMMCU) de messagerie instantanée au milieu.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="ba7fc-107">IMMCU est un composant du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="ba7fc-108">Le placement du IMMCU dans le flux de travail de communication requis autorise l’enregistrement des détails des appels et d’autres fonctionnalités que le serveur frontal autorise.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="ba7fc-109">La communication provient d’un port source dynamique du client vers le port de serveur frontal TLS/TCP/5061 (en partant du principe que l’utilisation de la sécurité de couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="ba7fc-110">Par conception, la communication d’égal à égal (et la messagerie instantanée à plusieurs parties) est possible uniquement lorsque Lync Server et IMMCU est actif et disponible.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ba7fc-111">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="ba7fc-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba7fc-112">Le pare-feu Windows doit être en cours d’exécution avant que vous ne démarriez les services Lync Server sur un serveur, car c’est le cas lorsque Lync Server ouvre les ports requis dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="ba7fc-113">Pour plus d’informations sur la configuration du pare-feu pour les composants Edge, voir [déterminer les exigences en matière de port et de pare-feu A/V externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="ba7fc-114">Le tableau suivant répertorie les ports qui doivent être ouverts sur chaque rôle serveur interne.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="ba7fc-115">Ports de serveurs requis (par rôle serveur)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="ba7fc-116">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-116">Server role</span></span></th>
<th><span data-ttu-id="ba7fc-117">Nom du service</span><span class="sxs-lookup"><span data-stu-id="ba7fc-117">Service name</span></span></th>
<th><span data-ttu-id="ba7fc-118">Port</span><span class="sxs-lookup"><span data-stu-id="ba7fc-118">Port</span></span></th>
<th><span data-ttu-id="ba7fc-119">Protocole</span><span class="sxs-lookup"><span data-stu-id="ba7fc-119">Protocol</span></span></th>
<th><span data-ttu-id="ba7fc-120">Remarques</span><span class="sxs-lookup"><span data-stu-id="ba7fc-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-121">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="ba7fc-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-123">1434</span><span class="sxs-lookup"><span data-stu-id="ba7fc-123">1434</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-124">UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-125">Navigateur SQL pour la copie locale répliquée de la base de données centrale de la Banque d’administration.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-126">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-127">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-128">5060</span><span class="sxs-lookup"><span data-stu-id="ba7fc-128">5060</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-129">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-130">Utilisé facultativement par les serveurs Standard Edition Server et les serveurs frontaux pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-131">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-132">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-133">5061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-133">5061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-135">Utilisé par les serveurs Standard Edition Server et les pools frontaux pour toutes les communications SIP internes entre serveurs (MTLS), pour les communications SIP entre serveurs et clients (TLS) et pour les communications SIP entre serveurs frontaux et serveurs de médiation (MTLS).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="ba7fc-136">Également utilisé pour communiquer avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-137">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-138">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-139">444</span><span class="sxs-lookup"><span data-stu-id="ba7fc-139">444</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-140">HTTPS</span></span></p>
<p><span data-ttu-id="ba7fc-141">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-142">Utilisé pour la communication HTTPs entre le focus (composant serveur Lync qui gère l’état de la Conférence) et les serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="ba7fc-143">Ce port est également utilisé pour la communication TCP entre les appareils succursales Survivables et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-144">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-145">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-146">135</span><span class="sxs-lookup"><span data-stu-id="ba7fc-146">135</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-147">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-148">Utilisé pour les opérations DCOM, telles que le déplacement des utilisateurs, la synchronisation du réplicateur d’utilisateurs et la synchronisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-149">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-150">Service de conférence par messagerie instantanée Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-151">5062</span><span class="sxs-lookup"><span data-stu-id="ba7fc-151">5062</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-152">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-153">Utilisé pour les demandes SIP entrantes dans le cadre de conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-154">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-155">Service de conférence Web Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-156">8057</span><span class="sxs-lookup"><span data-stu-id="ba7fc-156">8057</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-158">Utilisé pour l’écoute des connexions PSOM (Persistent Shared Object Model) à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-159">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-160">Service de compatibilité des conférences Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-161">8058</span><span class="sxs-lookup"><span data-stu-id="ba7fc-161">8058</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-163">Utilisé pour écouter les connexions PSOM (persistent Shared Object mode) du client Live Meeting et des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-164">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-165">Service de visioconférence Lync Server audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="ba7fc-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-166">5063</span><span class="sxs-lookup"><span data-stu-id="ba7fc-166">5063</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-167">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-168">Utilisé pour les demandes SIP entrantes dans le cadre de conférences audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-169">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-170">Service de visioconférence Lync Server audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="ba7fc-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="ba7fc-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-173">Plage de ports multimédias utilisée pour les conférences vidéo.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-174">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-175">Service de compatibilité Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-176">80</span><span class="sxs-lookup"><span data-stu-id="ba7fc-176">80</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-178">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS) lorsque HTTPS n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-179">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-180">Service de compatibilité Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-181">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-181">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-183">Utilisé pour les communications à partir des serveurs frontaux vers les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-184">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-185">Service de compatibilité Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-186">8080</span><span class="sxs-lookup"><span data-stu-id="ba7fc-186">8080</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-187">TCP et HTTP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-188">Utilisé par les composants web pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-189">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-190">Composant de serveur web</span><span class="sxs-lookup"><span data-stu-id="ba7fc-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-191">4443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-191">4443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-193">Communications HTTPS (du proxy inverse) et HTTPS inter-pool frontal pour connexion à la découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-194">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-195">Composant de serveur web</span><span class="sxs-lookup"><span data-stu-id="ba7fc-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-196">8060</span><span class="sxs-lookup"><span data-stu-id="ba7fc-196">8060</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-198">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-199">Composant de serveur web</span><span class="sxs-lookup"><span data-stu-id="ba7fc-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-200">8061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-200">8061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-202">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-203">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="ba7fc-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-204">5086</span><span class="sxs-lookup"><span data-stu-id="ba7fc-204">5086</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-206">Port SIP utilisé pour les processus internes des services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-207">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-208">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="ba7fc-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-209">5087</span><span class="sxs-lookup"><span data-stu-id="ba7fc-209">5087</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-211">Port SIP utilisé pour les processus internes des services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-212">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-213">Composant des services de mobilité</span><span class="sxs-lookup"><span data-stu-id="ba7fc-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-214">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-214">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-216">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-217">Service de surveillance des conférences de Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-218">5064</span><span class="sxs-lookup"><span data-stu-id="ba7fc-218">5064</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-219">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-220">Utilisé pour les demandes SIP entrantes dans le cadre de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-221">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-222">Service de surveillance des conférences de Lync Server (Conférence rendez-vous)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-223">5072</span><span class="sxs-lookup"><span data-stu-id="ba7fc-223">5072</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-224">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-225">Utilisé pour les demandes SIP entrantes pour le service d’assistance téléphonique (Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-226">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-227">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-228">5070</span><span class="sxs-lookup"><span data-stu-id="ba7fc-228">5070</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-229">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-230">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-231">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-232">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-233">5067</span><span class="sxs-lookup"><span data-stu-id="ba7fc-233">5067</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-235">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-236">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-237">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-238">5068</span><span class="sxs-lookup"><span data-stu-id="ba7fc-238">5068</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-239">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-240">Utilisé pour les demandes SIP entrantes de la passerelle PSTN vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-241">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-242">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-243">5081</span><span class="sxs-lookup"><span data-stu-id="ba7fc-243">5081</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-244">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-245">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-246">Serveurs frontaux qui exécutent également un serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-247">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-248">5082</span><span class="sxs-lookup"><span data-stu-id="ba7fc-248">5082</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-250">Utilisé pour les demandes SIP sortantes du serveur de médiation vers la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-251">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-252">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-253">5065</span><span class="sxs-lookup"><span data-stu-id="ba7fc-253">5065</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-254">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-255">Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-256">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-257">Service de partage d’application Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="ba7fc-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-259">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-260">Plage de ports multimédias utilisée pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-261">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-262">Service d’annonce Lync Server Conferencing</span><span class="sxs-lookup"><span data-stu-id="ba7fc-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-263">5073</span><span class="sxs-lookup"><span data-stu-id="ba7fc-263">5073</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-264">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-265">Utilisé pour les demandes SIP entrantes pour le service d’annonce Lync Server Conferencing (c’est-à-dire pour la Conférence rendez-vous).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-266">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-267">service de parcage d’appel Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-268">5075</span><span class="sxs-lookup"><span data-stu-id="ba7fc-268">5075</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-269">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-270">Utilisé pour les demandes SIP entrantes de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-271">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-272">Service de test audio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-273">5076</span><span class="sxs-lookup"><span data-stu-id="ba7fc-273">5076</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-274">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-275">Utilisé pour les demandes SIP entrantes du service de test audio.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-276">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-277">Non applicable</span><span class="sxs-lookup"><span data-stu-id="ba7fc-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-278">5066</span><span class="sxs-lookup"><span data-stu-id="ba7fc-278">5066</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-279">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-280">Utilisé pour la passerelle Enhanced 9-1-1 (E9-1-1) sortante.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-281">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-282">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-283">5071</span><span class="sxs-lookup"><span data-stu-id="ba7fc-283">5071</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-284">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-285">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-286">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-287">service Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-288">8404</span><span class="sxs-lookup"><span data-stu-id="ba7fc-288">8404</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-290">Utilisé pour les demandes SIP entrantes de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-291">serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-292">Service de stratégie de bande passante de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-293">5080</span><span class="sxs-lookup"><span data-stu-id="ba7fc-293">5080</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-294">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-295">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante, lui-même utilisé pour le trafic TURN Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-296">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ba7fc-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-297">Service de stratégie de bande passante de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-298">448</span><span class="sxs-lookup"><span data-stu-id="ba7fc-298">448</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-299">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-300">Utilisé pour le contrôle d’admission des appels par le service de stratégie de bande passante de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-301">Serveurs frontaux dans lesquels réside le magasin de gestion central</span><span class="sxs-lookup"><span data-stu-id="ba7fc-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-302">Service de l’agent réplicateur de serveurs maîtres de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-303">445</span><span class="sxs-lookup"><span data-stu-id="ba7fc-303">445</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-304">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-305">Utilisé pour transmettre les données de configuration du magasin central de gestion à des serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-306">Tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="ba7fc-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-308">1434</span><span class="sxs-lookup"><span data-stu-id="ba7fc-308">1434</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-309">UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-310">Navigateur SQL pour la copie locale répliquée des données du magasin de gestion central dans l’instance SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="ba7fc-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-311">Tous les serveurs internes</span><span class="sxs-lookup"><span data-stu-id="ba7fc-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-312">Divers</span><span class="sxs-lookup"><span data-stu-id="ba7fc-312">Various</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="ba7fc-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-315">Plage de ports multimédias utilisée pour les conférences audio sur tous les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="ba7fc-316">Utilisé par tous les serveurs qui terminent les appels audio : serveurs front-end (pour le service de surveillance des conférences de Lync Server, service d’annonce de conférence Lync Server et service de visioconférence Lync Server) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-317">Serveurs Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba7fc-318">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba7fc-319">Utilisé par Lync Server 2013 pour la connexion à Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-320">directeurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-321">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-322">5060</span><span class="sxs-lookup"><span data-stu-id="ba7fc-322">5060</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-323">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-324">Utilisé facultativement pour les itinéraires statiques vers des services approuvés, comme les serveurs de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-325">directeurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-326">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-327">444</span><span class="sxs-lookup"><span data-stu-id="ba7fc-327">444</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-328">HTTPS</span></span></p>
<p><span data-ttu-id="ba7fc-329">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-330">Communication entre serveurs frontaux et directeurs.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="ba7fc-331">Par ailleurs, le certificat client est publié (pour les serveurs frontaux) ou validé si le certificat client a déjà été publié.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-332">directeurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-333">Service de compatibilité Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-334">80</span><span class="sxs-lookup"><span data-stu-id="ba7fc-334">80</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-335">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-p105">Utilisé pour les communications initiales entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS). En fonctionnement normal, bascule vers le trafic HTTPS en utilisant le port 443 et le type de protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-338">Directeurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-339">Service de compatibilité Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-340">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-340">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-342">Utilisé pour les communications entre les directeurs et les noms de domaine complets des batteries de serveurs Web (URL utilisées par les composants Web IIS).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-343">directeurs</span><span class="sxs-lookup"><span data-stu-id="ba7fc-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-344">Service frontal de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-345">5061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-345">5061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-346">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-347">Utilisé pour les communications internes entre serveurs et pour les connexions client.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-348">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="ba7fc-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-349">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-350">5070</span><span class="sxs-lookup"><span data-stu-id="ba7fc-350">5070</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-351">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-352">Utilisé par le serveur de médiation pour les demandes entrantes du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-353">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="ba7fc-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-354">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-355">5067</span><span class="sxs-lookup"><span data-stu-id="ba7fc-355">5067</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-357">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-358">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="ba7fc-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-359">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-360">5068</span><span class="sxs-lookup"><span data-stu-id="ba7fc-360">5068</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-361">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-362">Utilisé pour les demandes SIP entrantes de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-363">Serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="ba7fc-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-364">Service médiation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba7fc-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-365">5070</span><span class="sxs-lookup"><span data-stu-id="ba7fc-365">5070</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-367">Utilisé pour les demandes SIP des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-368">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-369">SIP de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-370">5041</span><span class="sxs-lookup"><span data-stu-id="ba7fc-370">5041</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-372">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-373">Windows Communication Foundation (WCF) de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-374">881</span><span class="sxs-lookup"><span data-stu-id="ba7fc-374">881</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-375">TCP (TLS) et TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-376">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-377">Service de transfert de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ba7fc-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-378">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-378">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ba7fc-380">Certains scénarios de contrôle d’appel distant requièrent une connexion TCP entre le serveur frontal ou le directeur et le PBX.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="ba7fc-381">Même si Lync Server n’utilise plus 5060 port TCP, lors du déploiement d’un contrôle d’appel distant, vous créez une configuration de serveur approuvé, qui associe le nom de domaine complet du serveur de ligne RCC au port TCP utilisé par le serveur frontal ou le directeur pour se connecter au système PBX.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="ba7fc-382">Pour plus d’informations, voir l’applet de connexion <STRONG>CsTrustedApplicationComputer</STRONG> dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="ba7fc-383">Pour les pools utilisant uniquement l’équilibrage de la charge matérielle (et non pas l’équilibrage de charge DNS), le tableau suivant indique les ports qui doivent ouvrir les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="ba7fc-384">Ports des programmes d’équilibrage de la charge matérielle si uniquement l’équilibrage de la charge matérielle est utilisé</span><span class="sxs-lookup"><span data-stu-id="ba7fc-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba7fc-385">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="ba7fc-385">Load Balancer</span></span></th>
<th><span data-ttu-id="ba7fc-386">Port</span><span class="sxs-lookup"><span data-stu-id="ba7fc-386">Port</span></span></th>
<th><span data-ttu-id="ba7fc-387">Protocole</span><span class="sxs-lookup"><span data-stu-id="ba7fc-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-388">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-389">5061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-389">5061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-391">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-392">444</span><span class="sxs-lookup"><span data-stu-id="ba7fc-392">444</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-394">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-395">135</span><span class="sxs-lookup"><span data-stu-id="ba7fc-395">135</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-396">DCOM et appel de procédure distante (RPC)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-397">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-398">80</span><span class="sxs-lookup"><span data-stu-id="ba7fc-398">80</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-400">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-401">8080</span><span class="sxs-lookup"><span data-stu-id="ba7fc-401">8080</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-402">TCP : récupération client/appareil du certificat racine à partir du serveur frontal, notamment clients et appareils authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="ba7fc-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-403">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-404">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-404">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-406">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-407">4443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-407">4443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-408">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-409">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-410">5072</span><span class="sxs-lookup"><span data-stu-id="ba7fc-410">5072</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-411">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-412">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-413">5073</span><span class="sxs-lookup"><span data-stu-id="ba7fc-413">5073</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-414">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-415">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-416">5075</span><span class="sxs-lookup"><span data-stu-id="ba7fc-416">5075</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-417">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-418">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-419">5076</span><span class="sxs-lookup"><span data-stu-id="ba7fc-419">5076</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-420">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-421">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-422">5071</span><span class="sxs-lookup"><span data-stu-id="ba7fc-422">5071</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-423">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-424">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-425">5080</span><span class="sxs-lookup"><span data-stu-id="ba7fc-425">5080</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-426">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-427">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-428">448</span><span class="sxs-lookup"><span data-stu-id="ba7fc-428">448</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-429">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-430">Programme d’équilibrage de charge du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="ba7fc-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-431">5070</span><span class="sxs-lookup"><span data-stu-id="ba7fc-431">5070</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-432">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-433">Programme d’équilibrage de charge du serveur frontal (si le pool exécute également le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-434">5070</span><span class="sxs-lookup"><span data-stu-id="ba7fc-434">5070</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-435">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-436">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-437">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-437">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-439">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-440">444</span><span class="sxs-lookup"><span data-stu-id="ba7fc-440">444</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-442">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-443">5061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-443">5061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-444">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-445">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-446">4443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-446">4443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-447">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba7fc-p107">Vos pools frontaux et pools directeurs qui font appel à l’équilibrage de charge DNS doivent également déployer un programme d’équilibrage de la charge matérielle. Le tableau suivant affiche les ports qui doivent être ouverts sur ces programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="ba7fc-450">Ports des programmes d’équilibrage de la charge matérielle si l’équilibrage de charge DNS est utilisé</span><span class="sxs-lookup"><span data-stu-id="ba7fc-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba7fc-451">Programme d’équilibrage de charge</span><span class="sxs-lookup"><span data-stu-id="ba7fc-451">Load Balancer</span></span></th>
<th><span data-ttu-id="ba7fc-452">Port</span><span class="sxs-lookup"><span data-stu-id="ba7fc-452">Port</span></span></th>
<th><span data-ttu-id="ba7fc-453">Protocole</span><span class="sxs-lookup"><span data-stu-id="ba7fc-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-454">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-455">80</span><span class="sxs-lookup"><span data-stu-id="ba7fc-455">80</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-457">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-458">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-458">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-460">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-461">8080</span><span class="sxs-lookup"><span data-stu-id="ba7fc-461">8080</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-462">TCP : récupération client/appareil du certificat racine à partir du serveur frontal, notamment clients et appareils authentifiés par NTLM</span><span class="sxs-lookup"><span data-stu-id="ba7fc-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-463">Programme d’équilibrage de charge du serveur frontal</span><span class="sxs-lookup"><span data-stu-id="ba7fc-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-464">4443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-464">4443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-465">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-466">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-467">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-467">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ba7fc-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-469">Programme d’équilibrage de charge du directeur</span><span class="sxs-lookup"><span data-stu-id="ba7fc-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-470">4443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-470">4443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-471">HTTPS (du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="ba7fc-472">Ports client requis</span><span class="sxs-lookup"><span data-stu-id="ba7fc-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba7fc-473">Composant</span><span class="sxs-lookup"><span data-stu-id="ba7fc-473">Component</span></span></th>
<th><span data-ttu-id="ba7fc-474">Port</span><span class="sxs-lookup"><span data-stu-id="ba7fc-474">Port</span></span></th>
<th><span data-ttu-id="ba7fc-475">Protocole</span><span class="sxs-lookup"><span data-stu-id="ba7fc-475">Protocol</span></span></th>
<th><span data-ttu-id="ba7fc-476">Remarques</span><span class="sxs-lookup"><span data-stu-id="ba7fc-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-477">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-478">67/68</span><span class="sxs-lookup"><span data-stu-id="ba7fc-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-480">Utilisé par Lync Server pour rechercher le nom de domaine complet (FQDN) du Bureau d’enregistrement (autrement dit, en cas d’échec de la configuration du service DNS SRV et de paramètres manuels).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-481">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-482">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-482">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-484">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-485">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-486">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-486">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-488">Utilisé pour que les utilisateurs externes puissent accéder aux sessions de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-489">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-490">443</span><span class="sxs-lookup"><span data-stu-id="ba7fc-490">443</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-492">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (TCP).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-493">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-494">3478</span><span class="sxs-lookup"><span data-stu-id="ba7fc-494">3478</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-496">Utilisé pour que les utilisateurs externes puissent accéder aux sessions A/V et multimédias (UDP).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-497">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-498">5061</span><span class="sxs-lookup"><span data-stu-id="ba7fc-498">5061</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-500">Utilisé pour le trafic SIP client à serveur pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-501">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="ba7fc-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-503">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-504">Utilisé pour le transfert de fichiers entre clients Lync et clients précédents (clients de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 et Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-505">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ba7fc-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-508">Plage de ports audio (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-509">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ba7fc-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-512">Plage de ports vidéo (au moins 20 ports requis).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-513">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ba7fc-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-515">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-516">Transfert de fichiers d’égal à égal. Pour le transfert de fichiers de conférence, les clients utilisent le modèle PSOM.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7fc-517">Clients</span><span class="sxs-lookup"><span data-stu-id="ba7fc-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ba7fc-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-519">TCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-520">Partage d’application.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7fc-521">Téléphone de partie commune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="ba7fc-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="ba7fc-522">Téléphone de bureau Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="ba7fc-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="ba7fc-523">Téléphone IP HP 4110 (téléphone de partie commune)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="ba7fc-524">Téléphone IP HP 4120 (téléphone de bureau)</span><span class="sxs-lookup"><span data-stu-id="ba7fc-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="ba7fc-525">Téléphone de partie commune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="ba7fc-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="ba7fc-526">Téléphone de bureau IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="ba7fc-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="ba7fc-527">Téléphone de bureau IP CX700</span><span class="sxs-lookup"><span data-stu-id="ba7fc-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="ba7fc-528">Téléphone de conférence IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="ba7fc-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-529">67/68</span><span class="sxs-lookup"><span data-stu-id="ba7fc-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="ba7fc-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ba7fc-531">Utilisé par les périphériques répertoriés pour trouver le certificat de serveur Lync, le nom de domaine complet de mise en service et le nom de domaine complet du Bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba7fc-532">**\*** Pour configurer des ports spécifiques pour ces types de médias, utilisez l’applet de applet de CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort et les paramètres ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba7fc-533">Les programmes Set pour les clients Lync créent automatiquement les exceptions de pare-feu du système d’exploitation requises sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="ba7fc-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ba7fc-534">Les ports utilisés pour l’accès des utilisateurs externes sont nécessaires dans tout scénario où le client doit franchir le pare-feu de l’organisation (par exemple, les communications externes ou les réunions hébergées par d’autres organisations).</span><span class="sxs-lookup"><span data-stu-id="ba7fc-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

