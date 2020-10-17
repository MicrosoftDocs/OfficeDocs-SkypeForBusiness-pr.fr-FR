---
title: 'Lync Server 2013 : planification de la capacité pour le serveur de conversation permanente'
description: 'Lync Server 2013 : planification de la capacité pour le serveur de conversation permanente.'
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
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544490"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6ce4e-103">Planification de la capacité pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ce4e-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ce4e-104">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6ce4e-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6ce4e-105">Le serveur de conversation permanente peut effectuer une conversation en temps réel multi-utilisateur pouvant être conservée pour la récupération et la recherche futures.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="6ce4e-106">Contrairement à la messagerie instantanée de groupe enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session de serveur de conversation permanente reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, les fichiers, les URL et d’autres données qui font partie d’une conversation en cours.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="6ce4e-107">La planification de la capacité est un élément important de la préparation du déploiement du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="6ce4e-108">Cette rubrique fournit des informations sur les topologies de serveur de conversation permanente prises en charge et les tables de planification de la capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="6ce4e-109">Il décrit également comment gérer au mieux les déploiements de serveurs de conversation permanente qui nécessitent une plus grande capacité aux heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="6ce4e-110">Pour télécharger le serveur de conversation permanente, voir « Microsoft Lync Server 13 persistent Chat Server » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) .</span><span class="sxs-lookup"><span data-stu-id="6ce4e-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="6ce4e-111">Pour plus d’informations sur l’installation du serveur de conversation permanente, voir [Installing persistent Chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) et [Configuring persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6ce4e-112">Les outils de support, tels que l’outil de planification Lync Server, peuvent vous aider à planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="6ce4e-113">Pour plus d’informations sur l’outil de planification, voir [démarrage du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="6ce4e-114">Topologies prises en charge par le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="6ce4e-115">Vous pouvez déployer un serveur de conversation permanente dans des pools à serveur unique ou à plusieurs serveurs, ainsi qu’avec une topologie à pool unique ou à pool multiple.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="6ce4e-116">Nous pouvons également prendre en charge le serveur de conversation permanente sur le serveur Standard Edition pour les nouveaux déploiements Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="6ce4e-117">Toutefois, les performances et l’évolutivité seront affectées, et étant donné qu’il n’existe aucune option de haute disponibilité pour ce nouveau déploiement, nous pensons que vous l’utiliserez principalement à des fins de preuve de concept, d’évaluation, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ce4e-118">Pour plus d’informations sur les deux topologies, voir <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent Chat Server in Lync server 2013</A> dans cette documentation Set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent Chat Server in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="6ce4e-119">Topologie à serveur unique</span><span class="sxs-lookup"><span data-stu-id="6ce4e-119">Single-Server Topology</span></span>

<span data-ttu-id="6ce4e-120">La configuration minimale et le déploiement le plus simple pour le serveur de conversation permanente est une seule topologie de serveur frontal de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="6ce4e-121">Ce déploiement nécessite un serveur unique qui exécute le serveur de conversation permanente (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est requise, la base de données SQL Server pour stocker les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ce4e-122">Vous ne pouvez pas ajouter d’autres serveurs à un pool de serveurs de conversation permanente qui est démarré en tant que déploiement à serveur unique dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="6ce4e-123">Nous vous recommandons d’utiliser la topologie de pools à plusieurs serveurs, même si vous utilisez un serveur unique.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="6ce4e-124">Cela vous permettra de pouvoir ajouter d’autres serveurs ultérieurement, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="6ce4e-125">La figure suivante illustre tous les composants requis et facultatifs d’une topologie pour un seul serveur frontal de serveur de conversation permanente avec conformité.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="6ce4e-126">**Serveur de conversations permanentes unique**</span><span class="sxs-lookup"><span data-stu-id="6ce4e-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="6ce4e-127">![Topologie à serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à serveur unique avec service de conformité")</span><span class="sxs-lookup"><span data-stu-id="6ce4e-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="6ce4e-128">Topologie à plusieurs serveurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-128">Multiple-Server Topology</span></span>

<span data-ttu-id="6ce4e-129">Pour augmenter la capacité et la fiabilité, vous pouvez déployer une topologie à plusieurs serveurs, comme décrit dans la rubrique [Planning for persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="6ce4e-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="6ce4e-130">La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant un serveur de conversation permanente (les configurations de haute disponibilité et de récupération d’urgence autorisent jusqu’à huit, mais seulement quatre peuvent être actives et les quatre autres en attente).</span><span class="sxs-lookup"><span data-stu-id="6ce4e-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="6ce4e-131">Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, soit un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="6ce4e-132">Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, à ceci près que plusieurs serveurs hébergent le serveur de conversation permanente et peuvent être plus évolutifs.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="6ce4e-133">Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="6ce4e-134">La figure suivante illustre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="6ce4e-135">**Plusieurs serveurs de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="6ce4e-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="6ce4e-136">![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")</span><span class="sxs-lookup"><span data-stu-id="6ce4e-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="6ce4e-137">Dans un déploiement de serveur de conversation permanente à quatre serveurs, où 80 000 utilisateurs peuvent être simultanément connectés à et utilisant la conversation permanente, la charge est distribuée uniformément à 20 000 utilisateurs par serveur.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="6ce4e-138">Si un serveur devient indisponible, les utilisateurs qui sont connectés à ce serveur perdront leur accès au serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="6ce4e-139">Les utilisateurs déconnectés seront automatiquement transférés sur les serveurs restants jusqu’au rétablissement du serveur indisponible.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="6ce4e-140">En fonction de la quantité de trafic de conversation permanente sur le réseau, ce transfert peut prendre quelques minutes ou plus.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="6ce4e-141">Étant donné que chacun des autres serveurs peut héberger jusqu’à 30 000 utilisateurs, nous vous recommandons de restaurer le serveur indisponible aussi rapidement que possible afin d’éviter les problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="6ce4e-142">Dans le cas contraire, vous pouvez créer un autre serveur de conversation permanente à l’aide du générateur de topologies ou de l’applet de commande Windows PowerShell, **Set-applet cspersistentchatactiveserver**.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="6ce4e-143">Planification de la capacité du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="6ce4e-144">Les tableaux suivants peuvent vous aider à planifier la capacité du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="6ce4e-145">Ils modélisent comment la modification de différents paramètres du serveur de conversation permanente affecte les capacités de capacité.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="6ce4e-146">Planification de la capacité maximale pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="6ce4e-147">Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="6ce4e-148">Exemple de capacité maximale du pool de serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-149">Instances actives du service de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-150"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-151">Instances du service de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-152"><em>8 (4 doit être inactif ; seul un maximum de 4 peut être actif)</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-153">Utilisateurs actifs connectés</span><span class="sxs-lookup"><span data-stu-id="6ce4e-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-154"><em>80 000</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-155">Nombre total d’utilisateurs approvisionnés</span><span class="sxs-lookup"><span data-stu-id="6ce4e-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-156">150 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-157">Nombre de points de terminaison</span><span class="sxs-lookup"><span data-stu-id="6ce4e-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-158">120 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ce4e-159">Dans l’exemple précédent, le plan doit prendre en charge le nombre maximal d’utilisateurs autorisé par le serveur de conversation permanente : quatre serveurs/instances du service de conversation permanente (il peut avoir quatre serveurs passifs plus passifs exécutant le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="6ce4e-160">Planification de la capacité pour la gestion de l’accès aux salles de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="6ce4e-161">L’exemple de tableau suivant peut vous aider à planifier la gestion de l’accès aux salles de conversation permanente dans un pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="6ce4e-162">Exemple de gestion de l’accès à la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-162">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="6ce4e-163">Petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-164">Salles de conversation moyennes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-165">Grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-166">Total</span><span class="sxs-lookup"><span data-stu-id="6ce4e-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-167">Taille des salles de conversation (nombre d’utilisateurs connectés)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-168">30 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-169">150 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-170">16 000 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-171">Salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-172">32 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-173">1 067</span><span class="sxs-lookup"><span data-stu-id="6ce4e-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-174">10 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-174">10</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-175">33 077</span><span class="sxs-lookup"><span data-stu-id="6ce4e-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-176">% de salles Auditorium</span><span class="sxs-lookup"><span data-stu-id="6ce4e-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-177">1 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-177">1%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-178">1 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-178">1%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-179">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-180">% de salles ouvertes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-181">3 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-181">3%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-182">3 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-182">3%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-183">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-184">Salles ouvertes (pas d’appartenance explicite)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-185">960</span><span class="sxs-lookup"><span data-stu-id="6ce4e-185">960</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-186">32</span><span class="sxs-lookup"><span data-stu-id="6ce4e-186">32</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-187">5 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-187">5</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-188">997</span><span class="sxs-lookup"><span data-stu-id="6ce4e-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-189">Salles non ouvertes (salles standard avec appartenance explicite)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-190">31 040</span><span class="sxs-lookup"><span data-stu-id="6ce4e-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-191">1,035</span><span class="sxs-lookup"><span data-stu-id="6ce4e-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-192">5 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-192">5</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-193">32 080</span><span class="sxs-lookup"><span data-stu-id="6ce4e-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-194">Salles Auditorium (entrée autres présentateurs supplémentaires)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-195">0</span><span class="sxs-lookup"><span data-stu-id="6ce4e-195">0</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-196">32</span><span class="sxs-lookup"><span data-stu-id="6ce4e-196">32</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-197">5 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-198">Salles gérées par l’appartenance directe</span><span class="sxs-lookup"><span data-stu-id="6ce4e-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-199">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-199">50%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-200">10 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-200">10%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-201">0 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-202">Salles gérées par groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-203">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-203">50%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-204">90 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-204">90%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-205">100 %</span><span class="sxs-lookup"><span data-stu-id="6ce4e-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-206">Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles ouvertes (non spécifié explicitement)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-207">0</span><span class="sxs-lookup"><span data-stu-id="6ce4e-207">0</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-208">0</span><span class="sxs-lookup"><span data-stu-id="6ce4e-208">0</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-209">0</span><span class="sxs-lookup"><span data-stu-id="6ce4e-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-210">Utilisateurs de la liste d’appartenance de chaque salle de conversation pour les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-211">0,30</span><span class="sxs-lookup"><span data-stu-id="6ce4e-211">30</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-212">150</span><span class="sxs-lookup"><span data-stu-id="6ce4e-212">150</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-213">16 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-214">Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-215">3</span><span class="sxs-lookup"><span data-stu-id="6ce4e-215">3</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-216">5 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-216">5</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-217">10 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-218">Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires de la salle de conversation (pour les salles ouvertes et non ouvertes)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-219">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-219">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-220">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-220">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-221">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-222">Utilisateurs et groupes d’utilisateurs dans la liste présentateurs de la salle de conversation de type Auditorium (pour les salles ouvertes et non ouvertes)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-223">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-223">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-224">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-224">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-225">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-226">Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-227">465 600</span><span class="sxs-lookup"><span data-stu-id="6ce4e-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-228">15 520</span><span class="sxs-lookup"><span data-stu-id="6ce4e-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-229">Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-230">46 560</span><span class="sxs-lookup"><span data-stu-id="6ce4e-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-231">4656</span><span class="sxs-lookup"><span data-stu-id="6ce4e-231">4656</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-232">50</span><span class="sxs-lookup"><span data-stu-id="6ce4e-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-233">Entités basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les salles de conversation de type Auditorium</span><span class="sxs-lookup"><span data-stu-id="6ce4e-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-234">0</span><span class="sxs-lookup"><span data-stu-id="6ce4e-234">0</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-235">192</span><span class="sxs-lookup"><span data-stu-id="6ce4e-235">192</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-236">50</span><span class="sxs-lookup"><span data-stu-id="6ce4e-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-237">Entités de gestionnaire basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-238">192 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-239">6 400</span><span class="sxs-lookup"><span data-stu-id="6ce4e-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-240">60</span><span class="sxs-lookup"><span data-stu-id="6ce4e-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-241">Utilisateurs actifs par salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-242"><em>0,30</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-244"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-245">Salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-246"><em>an</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-249"><em>Seiz</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-250">Groupes d’utilisateurs dans chaque liste d’appartenance à une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-252"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-253"><em>0,15</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-254">Salles gérées par groupes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-258">Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-259">155 200</span><span class="sxs-lookup"><span data-stu-id="6ce4e-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-260">5173</span><span class="sxs-lookup"><span data-stu-id="6ce4e-260">5173</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-261">68</span><span class="sxs-lookup"><span data-stu-id="6ce4e-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-262">Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-263">465 600</span><span class="sxs-lookup"><span data-stu-id="6ce4e-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-264">77 600</span><span class="sxs-lookup"><span data-stu-id="6ce4e-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-265">72 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-266">Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-267">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-267">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-268">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-268">6</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-269">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-270">Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-271">192 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-272">6400</span><span class="sxs-lookup"><span data-stu-id="6ce4e-272">6400</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-273">60</span><span class="sxs-lookup"><span data-stu-id="6ce4e-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-274">Entrées de contrôle d’accès</span><span class="sxs-lookup"><span data-stu-id="6ce4e-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-275">704 160</span><span class="sxs-lookup"><span data-stu-id="6ce4e-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-276">26 768</span><span class="sxs-lookup"><span data-stu-id="6ce4e-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-277">160</span><span class="sxs-lookup"><span data-stu-id="6ce4e-277">160</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-278">731 088</span><span class="sxs-lookup"><span data-stu-id="6ce4e-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-279">Nombre maximum d’entrées de contrôle d’accès</span><span class="sxs-lookup"><span data-stu-id="6ce4e-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="6ce4e-280">2 millions</span><span class="sxs-lookup"><span data-stu-id="6ce4e-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ce4e-281">Dans l’exemple précédent, lorsque vous déployez les serveurs de conversation permanente conformément aux instructions recommandées, ils peuvent gérer jusqu’à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec la conformité activée.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="6ce4e-282">Cet exemple montre les salles de conversation classées comme petites (30 utilisateurs actifs à tout moment), moyennes (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs).</span><span class="sxs-lookup"><span data-stu-id="6ce4e-282">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="6ce4e-283">Le nombre de salles de conversation d’une certaine taille est calculé en fonction du nombre total :</span><span class="sxs-lookup"><span data-stu-id="6ce4e-283">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="6ce4e-284">D’utilisateurs actifs dans le système</span><span class="sxs-lookup"><span data-stu-id="6ce4e-284">Active users in the system</span></span>

  - <span data-ttu-id="6ce4e-285">D’utilisateurs actifs dans les salles de conversation de la taille donnée</span><span class="sxs-lookup"><span data-stu-id="6ce4e-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="6ce4e-286">Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="6ce4e-287">Pour chaque salle de conversation, la table de planification de la capacité précédente spécifie le nombre d’entrées de contrôle d’accès qui sont associées à la salle de conversation, y compris les entrées affectées directement à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-287">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="6ce4e-288">Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-288">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="6ce4e-289">Vous pouvez également contrôler l’accès au niveau de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-289">You can also control access at the category level.</span></span> <span data-ttu-id="6ce4e-290">Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique).</span><span class="sxs-lookup"><span data-stu-id="6ce4e-290">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="6ce4e-291">Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-291">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ce4e-292">Lors de la planification de votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisé est de 2 millions.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-292">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="6ce4e-293">Si les entrées de contrôle d’accès calculé dépassent 2 millions, les performances du serveur peuvent se dégrader de manière significative.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-293">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="6ce4e-294">Pour éviter ce problème, dans la mesure du possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-294">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="6ce4e-295">Planification de capacité pour la gestion de l’accès à la salle de conversation par invitation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="6ce4e-296">Vous pouvez utiliser le tableau de planification de la capacité suivant pour comprendre le nombre d’invitations que le serveur de conversation permanente crée et stocke dans la base de données de conversation permanente lorsqu’il est configuré pour envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="6ce4e-297">Vous gérez les invitations de la catégorie à l’aide de la page **paramètres de catégorie de salle de conversation** dans le panneau de configuration Lync Server, ou à l’aide de l’applet de commande Windows PowerShell, **Set-applet cspersistentchatcategory**.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="6ce4e-298">Vous pouvez gérer les invitations d’une salle de conversation (en fonction de ce que la catégorie autorise) à l’aide de la page de **gestion des salles** lancée à partir du client Lync, ou à l’aide d’une applet de commande Windows PowerShell, **Set-applet cspersistentchatroom**.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="6ce4e-299">Les exemples de données du tableau suivant supposent que, sur la page des paramètres de la **salle de conversation** de 50% de toutes les salles de conversation, l’option **invitations** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ce4e-300">Si la valeur calculée pour le nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur peuvent se dégrader de manière significative.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="6ce4e-301">Pour éviter ce problème, veillez à réduire le nombre de salles de conversation configurées pour envoyer des invitations ou à limiter le nombre d’utilisateurs pouvant rejoindre des salles de conversation configurées pour envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="6ce4e-302">Exemple d’accès à la salle de conversation par invitation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-302">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="6ce4e-303">Petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-304">Salles de conversation moyennes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-305">Grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="6ce4e-306">Total</span><span class="sxs-lookup"><span data-stu-id="6ce4e-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-307">Utilisateurs pouvant accéder à la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-308">30 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-309">150 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-310">16 000 par salle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-311">Pourcentage de salles ayant des invitations</span><span class="sxs-lookup"><span data-stu-id="6ce4e-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-312">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-312">50%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-313">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-313">50%</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-314">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-315">Salles de conversation configurées pour envoyer des invitations</span><span class="sxs-lookup"><span data-stu-id="6ce4e-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-316"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-318"><em>disque</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-319">Utilisateurs pouvant accéder à la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="6ce4e-322"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="6ce4e-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-323">Invitations générées par le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-324">960 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-325">120 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-326">80 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-327">1 160 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-328">Nombre maximal autorisé d’invitations</span><span class="sxs-lookup"><span data-stu-id="6ce4e-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="6ce4e-329">2 millions</span><span class="sxs-lookup"><span data-stu-id="6ce4e-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-330">Modèle 1-démarrer avec le nombre prévu de messages par salle et par jour</span><span class="sxs-lookup"><span data-stu-id="6ce4e-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-331">Taux de conversation par salle (par jour)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-332">50</span><span class="sxs-lookup"><span data-stu-id="6ce4e-332">50</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-333">500</span><span class="sxs-lookup"><span data-stu-id="6ce4e-333">500</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-334">100</span><span class="sxs-lookup"><span data-stu-id="6ce4e-334">100</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-335">650</span><span class="sxs-lookup"><span data-stu-id="6ce4e-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-336">Taux de conversation (par seconde) dans toutes les salles</span><span class="sxs-lookup"><span data-stu-id="6ce4e-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-337">55,56</span><span class="sxs-lookup"><span data-stu-id="6ce4e-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-338">18,52</span><span class="sxs-lookup"><span data-stu-id="6ce4e-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-339">0,03</span><span class="sxs-lookup"><span data-stu-id="6ce4e-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-340">74</span><span class="sxs-lookup"><span data-stu-id="6ce4e-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-341">Modèle 2-Démarrer avec le nombre de messages publiés par utilisateur et par jour</span><span class="sxs-lookup"><span data-stu-id="6ce4e-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-342">Taux de conversation par utilisateur et par jour</span><span class="sxs-lookup"><span data-stu-id="6ce4e-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-343">15 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-343">15</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-344">5 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-344">5</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-345">0,1</span><span class="sxs-lookup"><span data-stu-id="6ce4e-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-346">vingtaine</span><span class="sxs-lookup"><span data-stu-id="6ce4e-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-347">Taux de conversation par salle (par jour)</span><span class="sxs-lookup"><span data-stu-id="6ce4e-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-348">38</span><span class="sxs-lookup"><span data-stu-id="6ce4e-348">38</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-349">375</span><span class="sxs-lookup"><span data-stu-id="6ce4e-349">375</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-350">800</span><span class="sxs-lookup"><span data-stu-id="6ce4e-350">800</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-351">1 213</span><span class="sxs-lookup"><span data-stu-id="6ce4e-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-352">Taux de conversation (par seconde) dans toutes les salles</span><span class="sxs-lookup"><span data-stu-id="6ce4e-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-353">41,67</span><span class="sxs-lookup"><span data-stu-id="6ce4e-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-354">13,89</span><span class="sxs-lookup"><span data-stu-id="6ce4e-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-355">0,28</span><span class="sxs-lookup"><span data-stu-id="6ce4e-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-356">56</span><span class="sxs-lookup"><span data-stu-id="6ce4e-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="6ce4e-357">Modèle utilisateur des performances du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="6ce4e-358">Le tableau suivant décrit le modèle utilisateur pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="6ce4e-359">Elle fournit la base des exigences de planification de la capacité et représente une organisation classique avec 80 000 utilisateurs simultanés sur quatre serveurs.</span><span class="sxs-lookup"><span data-stu-id="6ce4e-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="6ce4e-360">Modèle utilisateur des performances du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-361">Nombre d’utilisateurs actifs connectés</span><span class="sxs-lookup"><span data-stu-id="6ce4e-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-362">80 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-363">Nombre d’instances de service du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6ce4e-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-364">4 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-365">Taille des petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-366">30 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-367">Taille des moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-368">150 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-369">Taille des grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-370">16 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6ce4e-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-371">Nombre total de salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-372">33 077</span><span class="sxs-lookup"><span data-stu-id="6ce4e-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-373">Nombre de petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-374">32 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-375">Nombre de moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-376">1 067</span><span class="sxs-lookup"><span data-stu-id="6ce4e-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-377">Nombre de grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-378">10 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-379">Nombre total de salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-380">16 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-381">Nombre total de petites salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-382">12 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-383">Nombre total de moyennes salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-384">n°2</span><span class="sxs-lookup"><span data-stu-id="6ce4e-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-385">Nombre total de grandes salles de conversation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-386">n°2</span><span class="sxs-lookup"><span data-stu-id="6ce4e-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-387">Nombre de salles jointes par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-388">heures/24</span><span class="sxs-lookup"><span data-stu-id="6ce4e-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-389">Taux maximal d’utilisateurs joints</span><span class="sxs-lookup"><span data-stu-id="6ce4e-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-390">10/seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-391">Taux de conversation total</span><span class="sxs-lookup"><span data-stu-id="6ce4e-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-392">24/seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-393">Taux de conversation pour les petites salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-394">22.22/seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-395">Taux de conversation pour les moyennes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-396">1.67/seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-397">Taux de conversation pour les grandes salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-398">~ 0,15/seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-399">Pourcentage des salles de conversation configurées pour les invitations</span><span class="sxs-lookup"><span data-stu-id="6ce4e-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-400">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-401">Pourcentage des appartenances directes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-402">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-403">Pourcentage des appartenances aux groupes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-404">50%</span><span class="sxs-lookup"><span data-stu-id="6ce4e-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-405">Nombre moyen d’affiliations ancêtres dans les services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ce4e-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-406">100 - 200</span><span class="sxs-lookup"><span data-stu-id="6ce4e-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-407">Nombre de contacts abonnés par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-408">80</span><span class="sxs-lookup"><span data-stu-id="6ce4e-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-409">Nombre moyen de points de terminaison par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-410">1,5</span><span class="sxs-lookup"><span data-stu-id="6ce4e-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-411">Nombre moyen de salles de conversation visibles par point de terminaison</span><span class="sxs-lookup"><span data-stu-id="6ce4e-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-412">1,5</span><span class="sxs-lookup"><span data-stu-id="6ce4e-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-413">Nombre moyen de salles de conversation visibles par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-414">2,25 (50% pour une salle de 1 et 50% pour 2 salles); Jusqu’à 6 salles ouvertes, une par moniteur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-415">Nombre de participants interrogés par intervalle</span><span class="sxs-lookup"><span data-stu-id="6ce4e-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-416">25 par salle de conversation visible</span><span class="sxs-lookup"><span data-stu-id="6ce4e-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-417">Durée de la fréquence d’interrogation</span><span class="sxs-lookup"><span data-stu-id="6ce4e-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-418">5 minutes</span><span class="sxs-lookup"><span data-stu-id="6ce4e-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-419">Nombre de participants interrogés par seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-420">15 000</span><span class="sxs-lookup"><span data-stu-id="6ce4e-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce4e-421">Nombre de changements du statut de présence par heure et par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6ce4e-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-422">6 </span><span class="sxs-lookup"><span data-stu-id="6ce4e-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce4e-423">Nombre de changements du statut de présence par seconde</span><span class="sxs-lookup"><span data-stu-id="6ce4e-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="6ce4e-424">133,33</span><span class="sxs-lookup"><span data-stu-id="6ce4e-424">133.33</span></span></p></td>
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

