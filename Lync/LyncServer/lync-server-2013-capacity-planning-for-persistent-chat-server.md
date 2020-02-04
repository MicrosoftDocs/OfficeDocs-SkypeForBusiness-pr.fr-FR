---
title: 'Lync Server 2013 : planification de la capacité pour le serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="1ae7e-102">Planification de la capacité pour le serveur de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ae7e-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae7e-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="1ae7e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="1ae7e-104">Le serveur de chat permanent peut exécuter une discussion en temps réel avec plusieurs utilisateurs, qui peut être persistante lors de la récupération et de la recherche ultérieures.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="1ae7e-105">À la différence de la messagerie instantanée de groupe enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session serveur de chat permanent reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, les fichiers, les URL et les autres données faisant partie d’un conversation en cours.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="1ae7e-106">La planification de la capacité est une partie importante de la préparation du déploiement d’un serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="1ae7e-107">Cette rubrique fournit des détails sur les topologies du serveur de chat permanent prises en charge et les tables de planification de capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="1ae7e-108">Il explique également comment gérer au mieux les déploiements de serveurs de chat permanent qui nécessitent une plus grande capacité aux heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="1ae7e-109">Pour télécharger le serveur Chat permanent, voir « Microsoft Lync Server 13 persistent Chat Server [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="1ae7e-110">Pour plus d’informations sur l’installation d’un serveur de chat permanent, voir [installer le serveur Chat permanent dans Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) et [configurer le serveur Chat permanent dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1ae7e-111">Les outils d’assistance, tels que l’outil de planification de Lync Server, peuvent vous aider à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="1ae7e-112">Pour plus d’informations sur l’outil de planification, voir [commencer le processus de planification de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="1ae7e-113">Topologies prises en charge par le serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="1ae7e-114">Vous pouvez déployer le serveur de chat permanent dans les pools serveur unique ou serveur multiples, avec une topologie à pool unique ou à plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="1ae7e-115">Nous prenons désormais en charge le serveur Chat permanent sur un serveur Standard Edition Server pour les nouveaux déploiements de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="1ae7e-116">Toutefois, les performances et l’évolutivité seront affectées, et comme il n’existe aucune option de haute disponibilité pour ce nouveau déploiement, nous pensons que vous utiliserez principalement cette méthode dans le cadre de la preuve de concept, d’évaluation, etc.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ae7e-117">Pour plus d’informations sur les deux topologies, reportez-vous à la section <A href="lync-server-2013-planning-for-persistent-chat-server.md">planification du serveur de chat permanent dans Lync server 2013</A> dans cette documentation Set et <A href="lync-server-2013-deploying-persistent-chat-server.md">déploiement du serveur de conversation permanent dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="1ae7e-118">Topologie à serveur unique</span><span class="sxs-lookup"><span data-stu-id="1ae7e-118">Single-Server Topology</span></span>

<span data-ttu-id="1ae7e-119">La configuration minimum et le déploiement le plus simple pour le serveur de chat permanent est une topologie de serveur frontal de chat permanent unique.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="1ae7e-120">Ce déploiement nécessite un serveur unique exécutant chat permanent (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et si la conformité est requise, la base de données SQL Server pour stocker le données de conformité.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ae7e-121">Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de chat permanent démarré comme déploiement d’un serveur unique dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="1ae7e-122">Nous vous recommandons d’utiliser la topologie de pool multiserveur, même si vous utilisez un serveur unique.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="1ae7e-123">C’est pourquoi vous pourrez ajouter d’autres serveurs ultérieurement, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="1ae7e-124">La figure suivante montre tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontal de chat permanent avec conformité.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="1ae7e-125">**Serveur de chat permanent unique**</span><span class="sxs-lookup"><span data-stu-id="1ae7e-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="1ae7e-126">![Topologie de serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie de serveur unique avec service de conformité")</span><span class="sxs-lookup"><span data-stu-id="1ae7e-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="1ae7e-127">Topologie de plusieurs serveurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-127">Multiple-Server Topology</span></span>

<span data-ttu-id="1ae7e-128">Afin d’offrir une plus grande capacité et une fiabilité accrue, vous pouvez déployer une topologie multiserveur, comme décrit dans [planification pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="1ae7e-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="1ae7e-129">La topologie multiserveur peut inclure jusqu’à quatre ordinateurs actifs exécutant chat permanent (les configurations de haute disponibilité et de récupération d’urgence peuvent prendre jusqu’à 8, mais seules quatre peuvent être actives et les quatre autres en veille).</span><span class="sxs-lookup"><span data-stu-id="1ae7e-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="1ae7e-130">Chaque serveur peut prendre en charge autant d’utilisateurs simultanés qu' 20 000, soit un total d' 80 000 utilisateurs simultanés connectés à un pool de serveurs de chat permanent doté de 4 serveurs.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="1ae7e-131">Une topologie multiserveur est la même que celle de la topologie sur un serveur, à l’exception de l’hébergement de plusieurs serveurs et de la possibilité d’augmenter leur taille.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="1ae7e-132">Plusieurs ordinateurs exécutant un serveur Chat permanent doivent résider dans le même domaine de services de domaine Active Directory que Lync Server et le service de conformité.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="1ae7e-133">La figure suivante montre tous les composants d’une topologie multiserveur avec plusieurs ordinateurs exécutant une conversation permanente serveur, le service de conformité facultatif et une base de données de conformité séparée.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="1ae7e-134">**Plusieurs serveurs de chat permanent**</span><span class="sxs-lookup"><span data-stu-id="1ae7e-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="1ae7e-135">![Topologie de plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie de plusieurs serveurs")</span><span class="sxs-lookup"><span data-stu-id="1ae7e-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="1ae7e-136">Dans le cas d’un déploiement sur un serveur de chat permanent à quatre serveurs, où les utilisateurs de 80 000 peuvent se connecter à un serveur et utiliser une conversation permanente, le chargement est distribué de façon égale auprès des utilisateurs 20 000 par serveur.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="1ae7e-137">Si un serveur devient indisponible, les utilisateurs qui se connectent à ce serveur perdront leur accès au serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="1ae7e-138">Ces utilisateurs déconnectés sont alors automatiquement transférés vers les serveurs restants jusqu’à ce que le serveur indisponible soit restauré.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="1ae7e-139">En fonction de la quantité de trafic de chat permanent sur le réseau, ce transfert peut prendre quelques minutes ou plus.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="1ae7e-140">Étant donné que chacun des serveurs restants peut héberger autant d’utilisateurs qu' 30 000, nous vous recommandons de restaurer le serveur non disponible aussi rapidement que possible pour éviter les problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="1ae7e-141">Dans le cas contraire, vous pouvez rendre un autre serveur de chat permanent disponible via le générateur de topologie ou la cmdlet Windows PowerShell **Set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="1ae7e-142">Planification de la capacité du serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="1ae7e-143">Les tableaux suivants peuvent vous aider à planifier la capacité du serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="1ae7e-144">Ils déterminent la manière dont les paramètres du serveur de conversation persistante affectent les capacités de capacité.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="1ae7e-145">Planification de votre capacité maximale pour le serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="1ae7e-146">Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="1ae7e-147">Exemple de capacité maximale du pool de serveurs chat chat</span><span class="sxs-lookup"><span data-stu-id="1ae7e-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-148">Instances de service de chat permanent actives</span><span class="sxs-lookup"><span data-stu-id="1ae7e-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-150">Instances de service de chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-151"><em>8 (4 doit être inactif ; seul un maximum de 4 peut être actif)</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-152">Utilisateurs actifs connectés</span><span class="sxs-lookup"><span data-stu-id="1ae7e-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-154">Nombre total d’utilisateurs approvisionnés</span><span class="sxs-lookup"><span data-stu-id="1ae7e-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-155">150,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-156">Nombre de points de terminaison</span><span class="sxs-lookup"><span data-stu-id="1ae7e-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-157">120,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1ae7e-158">Dans l’exemple ci-dessus, le plan doit prendre en charge le nombre maximal d’utilisateurs pouvant être conservés par un serveur de chat permanent : quatre serveurs/instances du service de chat permanent (peuvent comporter 4 serveurs plus passifs pour une disponibilité élevée et une reprise après sinistre) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="1ae7e-159">Planification de la capacité pour gérer l’accès aux salles de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="1ae7e-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="1ae7e-160">L’exemple de tableau suivant peut vous aider à planifier la gestion de l’accès aux salles de conversation permanentes dans un pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="1ae7e-161">Exemple de gestion de l’accès aux salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-161">Managing Chat Room Access Sample</span></span>

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
<th></th>
<th><span data-ttu-id="1ae7e-162">Salles de conversation de petite taille</span><span class="sxs-lookup"><span data-stu-id="1ae7e-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-163">Salles de conversation de taille moyenne</span><span class="sxs-lookup"><span data-stu-id="1ae7e-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-164">Salles de conversation de grande taille</span><span class="sxs-lookup"><span data-stu-id="1ae7e-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-165">Total</span><span class="sxs-lookup"><span data-stu-id="1ae7e-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-166">Taille des salles de conversation (nombre d’utilisateurs connectés)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-167">30 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-168">150 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-169">16 000 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-170">Salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-171">32,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-172">1,067</span><span class="sxs-lookup"><span data-stu-id="1ae7e-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-173">0,10</span><span class="sxs-lookup"><span data-stu-id="1ae7e-173">10</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-174">33,077</span><span class="sxs-lookup"><span data-stu-id="1ae7e-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-175">% de salles auditorium</span><span class="sxs-lookup"><span data-stu-id="1ae7e-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-176">1 %</span><span class="sxs-lookup"><span data-stu-id="1ae7e-176">1%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-177">1 %</span><span class="sxs-lookup"><span data-stu-id="1ae7e-177">1%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-178">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-179">% de salles ouvertes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-180">3%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-180">3%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-181">3%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-181">3%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-182">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-183">Salles ouvertes (aucune appartenance explicite)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-184">960</span><span class="sxs-lookup"><span data-stu-id="1ae7e-184">960</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-185">32</span><span class="sxs-lookup"><span data-stu-id="1ae7e-185">32</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-186">5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-186">5</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-187">997</span><span class="sxs-lookup"><span data-stu-id="1ae7e-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-188">Salles non ouvertes (salles standard avec appartenance explicite)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-189">31,040</span><span class="sxs-lookup"><span data-stu-id="1ae7e-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-190">1.035</span><span class="sxs-lookup"><span data-stu-id="1ae7e-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-191">5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-191">5</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-192">32,080</span><span class="sxs-lookup"><span data-stu-id="1ae7e-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-193">Salles auditorium (entrée de présentateurs supplémentaires)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-194">0,4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-194">0</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-195">32</span><span class="sxs-lookup"><span data-stu-id="1ae7e-195">32</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-196">5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-197">Salles gérées par appartenance directe</span><span class="sxs-lookup"><span data-stu-id="1ae7e-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-198">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-198">50%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-199">10%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-199">10%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-200">0%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-201">Salles gérées par groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-202">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-202">50%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-203">90%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-203">90%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-204">100%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-205">Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles ouvertes (non spécifiés explicitement)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-206">0,4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-206">0</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-207">0,4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-207">0</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-208">0,4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-209">Utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-210">trente</span><span class="sxs-lookup"><span data-stu-id="1ae7e-210">30</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-211">150</span><span class="sxs-lookup"><span data-stu-id="1ae7e-211">150</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-212">16,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-213">Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-214">3</span><span class="sxs-lookup"><span data-stu-id="1ae7e-214">3</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-215">5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-215">5</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-216">0,10</span><span class="sxs-lookup"><span data-stu-id="1ae7e-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-217">Utilisateurs et groupes d’utilisateurs dans la liste des gestionnaires de chaque salle de conversation (pour les salles ouvertes et non ouvertes)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-218">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-218">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-219">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-219">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-220">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-221">Utilisateurs et groupes d’utilisateurs dans la liste des présentateurs de chaque salle de conversation auditorium (pour les salles ouvertes et non ouvertes)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-222">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-222">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-223">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-223">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-224">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-225">Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-226">465,600</span><span class="sxs-lookup"><span data-stu-id="1ae7e-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-227">15,520</span><span class="sxs-lookup"><span data-stu-id="1ae7e-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-228">Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-229">46,560</span><span class="sxs-lookup"><span data-stu-id="1ae7e-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-230">4656</span><span class="sxs-lookup"><span data-stu-id="1ae7e-230">4656</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-231">50</span><span class="sxs-lookup"><span data-stu-id="1ae7e-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-232">Entités basées sur les utilisateurs et groupes d’utilisateurs dans toutes les salles de conversation auditorium</span><span class="sxs-lookup"><span data-stu-id="1ae7e-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-233">0,4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-233">0</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-234">192</span><span class="sxs-lookup"><span data-stu-id="1ae7e-234">192</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-235">50</span><span class="sxs-lookup"><span data-stu-id="1ae7e-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-236">Entités de gestionnaires basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-237">192,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-238">6,400</span><span class="sxs-lookup"><span data-stu-id="1ae7e-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-239">60</span><span class="sxs-lookup"><span data-stu-id="1ae7e-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-240">Utilisateurs actifs par salle de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-241"><em>trente</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-243"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-244">Salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-245"><em>midi</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-248"><em>Seiz</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-249">Groupes d’utilisateurs dans chaque liste d’appartenance à une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-250"><em>0,10</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-251"><em>0,10</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-252"><em>0,15</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-253">Salles gérées par groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-257">Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-258">155,200</span><span class="sxs-lookup"><span data-stu-id="1ae7e-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-259">5173</span><span class="sxs-lookup"><span data-stu-id="1ae7e-259">5173</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-260">68</span><span class="sxs-lookup"><span data-stu-id="1ae7e-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-261">Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-262">465,600</span><span class="sxs-lookup"><span data-stu-id="1ae7e-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-263">77,600</span><span class="sxs-lookup"><span data-stu-id="1ae7e-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-264">72,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-265">Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-266">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-266">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-267">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-267">6</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-268">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-269">Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-270">192,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-271">6400</span><span class="sxs-lookup"><span data-stu-id="1ae7e-271">6400</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-272">60</span><span class="sxs-lookup"><span data-stu-id="1ae7e-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-273">Entrées de contrôle d’accès</span><span class="sxs-lookup"><span data-stu-id="1ae7e-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-274">704,160</span><span class="sxs-lookup"><span data-stu-id="1ae7e-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-275">26,768</span><span class="sxs-lookup"><span data-stu-id="1ae7e-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-276">160</span><span class="sxs-lookup"><span data-stu-id="1ae7e-276">160</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-277">731,088</span><span class="sxs-lookup"><span data-stu-id="1ae7e-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-278">Nombre maximum d’entrées de contrôle d’accès</span><span class="sxs-lookup"><span data-stu-id="1ae7e-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="1ae7e-279">2,000,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1ae7e-280">Dans l’exemple ci-dessus, lorsque vous déployez les serveurs de chat permanent conformément aux recommandations recommandées, les utilisateurs peuvent gérer jusqu’à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec conformité activée.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="1ae7e-281">Cet exemple indique les catégories des salles de conversation : petite (30 utilisateurs actifs à tout moment), moyenne (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs).</span><span class="sxs-lookup"><span data-stu-id="1ae7e-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="1ae7e-282">Le nombre de salles de conversation d’une taille précise est calculé en fonction du nombre total de :</span><span class="sxs-lookup"><span data-stu-id="1ae7e-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="1ae7e-283">D’utilisateurs actifs dans le système</span><span class="sxs-lookup"><span data-stu-id="1ae7e-283">Active users in the system</span></span>

  - <span data-ttu-id="1ae7e-284">D’utilisateurs actifs dans les salles de conversation de la taille donnée</span><span class="sxs-lookup"><span data-stu-id="1ae7e-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="1ae7e-285">Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="1ae7e-p111">Pour chaque salle de conversation, le tableau de planification de capacité précédent spécifie le nombre d’entrées de contrôle d’accès associées à la salle de conversation, dont les entrées affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique). Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ae7e-p112">En planifiant votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisées est de 2 millions. Si le nombre d’entrées de contrôle d’accès calculé dépasse 2 millions, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, quand cela s’avère possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="1ae7e-294">Planification de la capacité pour gérer l’accès aux salles de conversation par invitation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="1ae7e-295">Vous pouvez utiliser le tableau de planification des capacités suivant pour comprendre le nombre d’invitations créées et stockées par le serveur Chat permanent dans la base de données de chat permanent lorsque celui-ci est configuré pour envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="1ae7e-296">Pour gérer les invitations à une catégorie, vous devez utiliser la page **paramètres des catégories de salle de conversation** du panneau de configuration de Lync Server, ou à l’aide de l’applet de commande Windows PowerShell **Set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="1ae7e-297">Vous pouvez gérer les invitations d’une salle de conversation (en fonction de ce que la catégorie autorise) à l’aide de la page de **gestion des salles** lancée par le client Lync, ou à l’aide d’une cmdlet Windows PowerShell, **Set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="1ae7e-298">Les exemples de données du tableau ci-après supposent que l’option **Invitations** est définie sur **Oui** dans la page **Paramètres de la salle de conversation** pour 50 % de toutes les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ae7e-299">Si la valeur calculée du nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur pourraient se dégrader de manière significative.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="1ae7e-300">Pour éviter ce problème, assurez-vous de réduire le nombre de salles de conversation configurées pour envoyer des invitations ou limiter le nombre d’utilisateurs qui peuvent rejoindre des salles de conversation configurées pour envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="1ae7e-301">Exemple d’accès à une salle de conversation par exemple d’invitation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-301">Chat Room Access by Invitation Sample</span></span>

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
<th></th>
<th><span data-ttu-id="1ae7e-302">Salles de conversation de petite taille</span><span class="sxs-lookup"><span data-stu-id="1ae7e-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-303">Salles de conversation de taille moyenne</span><span class="sxs-lookup"><span data-stu-id="1ae7e-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-304">Salles de conversation de grande taille</span><span class="sxs-lookup"><span data-stu-id="1ae7e-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="1ae7e-305">Total</span><span class="sxs-lookup"><span data-stu-id="1ae7e-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-306">Utilisateurs pouvant accéder à la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-307">30 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-308">150 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-309">16 000 par salle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-310">Pourcentage de salles qui ont des invitations</span><span class="sxs-lookup"><span data-stu-id="1ae7e-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-311">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-311">50%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-312">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-312">50%</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-313">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-314">Salles de conversation configurées pour envoyer des invitations</span><span class="sxs-lookup"><span data-stu-id="1ae7e-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-315"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-318">Utilisateurs pouvant accéder à la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="1ae7e-321"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="1ae7e-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-322">Invitations générées par un serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-323">960,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-324">120,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-325">80,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-327">Nombre maximal autorisé d’invitations</span><span class="sxs-lookup"><span data-stu-id="1ae7e-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="1ae7e-328">2,000,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-329">Modèle 1 - Démarrer avec le nombre attendu de messages par salle par jour</span><span class="sxs-lookup"><span data-stu-id="1ae7e-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-330">Taux de conversation par salle (par jour)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-331">50</span><span class="sxs-lookup"><span data-stu-id="1ae7e-331">50</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-332">500</span><span class="sxs-lookup"><span data-stu-id="1ae7e-332">500</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-333">100</span><span class="sxs-lookup"><span data-stu-id="1ae7e-333">100</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-334">650</span><span class="sxs-lookup"><span data-stu-id="1ae7e-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-335">Taux de conversation (par seconde) de toutes les salles</span><span class="sxs-lookup"><span data-stu-id="1ae7e-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-336">55.56</span><span class="sxs-lookup"><span data-stu-id="1ae7e-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-337">18.52</span><span class="sxs-lookup"><span data-stu-id="1ae7e-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-338">0.03</span><span class="sxs-lookup"><span data-stu-id="1ae7e-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-339">74</span><span class="sxs-lookup"><span data-stu-id="1ae7e-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-340">Modèle 2 - Démarrer avec le nombre de messages publiés par utilisateur par jour</span><span class="sxs-lookup"><span data-stu-id="1ae7e-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-341">Taux de conversation par utilisateur par jour</span><span class="sxs-lookup"><span data-stu-id="1ae7e-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-342">0,15</span><span class="sxs-lookup"><span data-stu-id="1ae7e-342">15</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-343">5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-343">5</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-344">0.1</span><span class="sxs-lookup"><span data-stu-id="1ae7e-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-345">CX3-20</span><span class="sxs-lookup"><span data-stu-id="1ae7e-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-346">Taux de conversation par salle (par jour)</span><span class="sxs-lookup"><span data-stu-id="1ae7e-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-347">38</span><span class="sxs-lookup"><span data-stu-id="1ae7e-347">38</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-348">375</span><span class="sxs-lookup"><span data-stu-id="1ae7e-348">375</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-349">800</span><span class="sxs-lookup"><span data-stu-id="1ae7e-349">800</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-350">1,213</span><span class="sxs-lookup"><span data-stu-id="1ae7e-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-351">Taux de conversation (par seconde) de toutes les salles</span><span class="sxs-lookup"><span data-stu-id="1ae7e-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-352">41.67</span><span class="sxs-lookup"><span data-stu-id="1ae7e-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-353">13.89</span><span class="sxs-lookup"><span data-stu-id="1ae7e-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-354">0.28</span><span class="sxs-lookup"><span data-stu-id="1ae7e-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-355">56</span><span class="sxs-lookup"><span data-stu-id="1ae7e-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="1ae7e-356">Modèle d’utilisateur de performance serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="1ae7e-357">Le tableau suivant décrit le modèle utilisateur pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="1ae7e-358">Il fournit les bases des conditions de planification de la capacité requises et représente une organisation type avec 80 000 utilisateurs simultanés sur quatre serveurs.</span><span class="sxs-lookup"><span data-stu-id="1ae7e-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="1ae7e-359">Modèle d’utilisateur de performance serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-360">Nombre d’utilisateurs actifs connectés</span><span class="sxs-lookup"><span data-stu-id="1ae7e-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-361">80,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-362">Nombre d’instances de service de chat permanent</span><span class="sxs-lookup"><span data-stu-id="1ae7e-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-363">4</span><span class="sxs-lookup"><span data-stu-id="1ae7e-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-364">Taille des petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-365">30 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-366">Taille des moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-367">150 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-368">Taille des grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-369">16 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ae7e-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-370">Nombre total de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-371">33,077</span><span class="sxs-lookup"><span data-stu-id="1ae7e-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-372">Nombre de petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-373">32,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-374">Nombre de moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-375">1,067</span><span class="sxs-lookup"><span data-stu-id="1ae7e-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-376">Nombre de grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-377">0,10</span><span class="sxs-lookup"><span data-stu-id="1ae7e-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-378">Nombre total de salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-379">Seiz</span><span class="sxs-lookup"><span data-stu-id="1ae7e-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-380">Nombre total de petites salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-381">midi</span><span class="sxs-lookup"><span data-stu-id="1ae7e-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-382">Nombre total de moyennes salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-383">deuxième</span><span class="sxs-lookup"><span data-stu-id="1ae7e-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-384">Nombre total de grandes salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-385">deuxième</span><span class="sxs-lookup"><span data-stu-id="1ae7e-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-386">Nombre de salles jointes par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-387">24</span><span class="sxs-lookup"><span data-stu-id="1ae7e-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-388">Taux maximal d’utilisateurs joints</span><span class="sxs-lookup"><span data-stu-id="1ae7e-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-389">10/seconde</span><span class="sxs-lookup"><span data-stu-id="1ae7e-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-390">Taux de conversation total</span><span class="sxs-lookup"><span data-stu-id="1ae7e-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-391">24/seconde</span><span class="sxs-lookup"><span data-stu-id="1ae7e-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-392">Taux de conversation pour les petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="1ae7e-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-394">Taux de conversation pour les moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="1ae7e-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-396">Taux de conversation pour les grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="1ae7e-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-398">Pourcentage des salles de conversation configurées pour les invitations</span><span class="sxs-lookup"><span data-stu-id="1ae7e-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-399">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-400">Pourcentage des appartenances directes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-401">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-402">Pourcentage des appartenances aux groupes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-403">50%</span><span class="sxs-lookup"><span data-stu-id="1ae7e-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-404">Nombre moyen d’affiliations d’ancêtre dans les services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="1ae7e-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="1ae7e-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-406">Nombre de contacts abonnés par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-407">80</span><span class="sxs-lookup"><span data-stu-id="1ae7e-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-408">Nombre moyen de points de terminaison par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-409">1.5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-410">Nombre moyen de salles de conversation visibles par point de terminaison</span><span class="sxs-lookup"><span data-stu-id="1ae7e-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-411">1.5</span><span class="sxs-lookup"><span data-stu-id="1ae7e-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-412">Nombre moyen de salles de conversation visibles par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-413">2,25 (50 % pour une salle et 50 % pour 2 salles) ; jusqu’à 6 salles ouvertes, une par moniteur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-414">Nombre de participants interrogés par intervalle</span><span class="sxs-lookup"><span data-stu-id="1ae7e-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-415">25 par salle de conversation visible</span><span class="sxs-lookup"><span data-stu-id="1ae7e-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-416">Durée de la fréquence d’interrogation</span><span class="sxs-lookup"><span data-stu-id="1ae7e-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-417">5 minutes</span><span class="sxs-lookup"><span data-stu-id="1ae7e-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-418">Nombre de participants interrogés par seconde</span><span class="sxs-lookup"><span data-stu-id="1ae7e-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-419">15,000</span><span class="sxs-lookup"><span data-stu-id="1ae7e-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae7e-420">Nombre de changements du statut de présence par heure et par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ae7e-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-421">6</span><span class="sxs-lookup"><span data-stu-id="1ae7e-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae7e-422">Nombre de changements du statut de présence par seconde</span><span class="sxs-lookup"><span data-stu-id="1ae7e-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="1ae7e-423">133.33</span><span class="sxs-lookup"><span data-stu-id="1ae7e-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

