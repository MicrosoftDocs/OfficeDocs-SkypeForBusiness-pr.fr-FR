---
title: Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="c8587-102">Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8587-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8587-103">_**Dernière modification de la rubrique:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="c8587-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="c8587-104">Cette section fournit des recommandations sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans la rubrique [modèles d’utilisateur de Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="c8587-105">Plateforme matérielle testée</span><span class="sxs-lookup"><span data-stu-id="c8587-105">Tested Hardware Platform</span></span>

<span data-ttu-id="c8587-106">Tous les résultats de performance et recommandations de déploiement de cette section sont basés sur le test de performance sur les serveurs exécutant le matériel décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c8587-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="c8587-107">Nous vous recommandons d’utiliser un matériel similaire.</span><span class="sxs-lookup"><span data-stu-id="c8587-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="c8587-108">Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres.</span><span class="sxs-lookup"><span data-stu-id="c8587-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="c8587-109">Notez que ces recommandations en matière de matériel sont supérieures à celles des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8587-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="c8587-110">Matériel utilisé dans les tests de performances</span><span class="sxs-lookup"><span data-stu-id="c8587-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-111">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="c8587-111">Hardware component</span></span></th>
<th><span data-ttu-id="c8587-112">Recommandation</span><span class="sxs-lookup"><span data-stu-id="c8587-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-113">Processeur</span><span class="sxs-lookup"><span data-stu-id="c8587-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="c8587-114">Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="c8587-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="c8587-115">Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8587-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-116">Mémoire</span><span class="sxs-lookup"><span data-stu-id="c8587-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="c8587-117">32 gigaoctets (Go)</span><span class="sxs-lookup"><span data-stu-id="c8587-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-118">Disque</span><span class="sxs-lookup"><span data-stu-id="c8587-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8587-119">8 disques durs ou plus 10 000 tr/min avec au moins 72 Go d’espace disponible.</span><span class="sxs-lookup"><span data-stu-id="c8587-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="c8587-120">Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</span><span class="sxs-lookup"><span data-stu-id="c8587-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="c8587-121">-Ou</span><span class="sxs-lookup"><span data-stu-id="c8587-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c8587-122">Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</span><span class="sxs-lookup"><span data-stu-id="c8587-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-123">Réseau</span><span class="sxs-lookup"><span data-stu-id="c8587-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8587-124">1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</span><span class="sxs-lookup"><span data-stu-id="c8587-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="c8587-125">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="c8587-125">Summary of Results</span></span>

<span data-ttu-id="c8587-126">Le tableau suivant résume ces recommandations.</span><span class="sxs-lookup"><span data-stu-id="c8587-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-127">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="c8587-127">Server role</span></span></th>
<th><span data-ttu-id="c8587-128">Nombre maximal d’utilisateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="c8587-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-129">Pool frontal avec douze serveurs front-end et un serveur principal ou paire en miroir de serveurs dorsaux.</span><span class="sxs-lookup"><span data-stu-id="c8587-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="c8587-130">80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="c8587-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-131">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="c8587-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="c8587-132">Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant la taille maximale d’une conférence d’utilisateurs 250, et une seule conférence de grande envergure exécutée à la fois.</span><span class="sxs-lookup"><span data-stu-id="c8587-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c8587-133">De plus, vous pouvez prendre en charge des conférences de grande envergure entre les utilisateurs de 250 et de 1000 en déployant un pool frontal distinct avec deux serveurs front-end pour héberger les conférences de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="c8587-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="c8587-134">Pour plus d’informations, consultez <A href="lync-server-2013-supporting-large-meetings.md">prise en charge de grandes réunions à l’aide de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c8587-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-135">Un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c8587-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="c8587-136">12 000 utilisateurs distants concurrents</span><span class="sxs-lookup"><span data-stu-id="c8587-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-137">Un réalisateur</span><span class="sxs-lookup"><span data-stu-id="c8587-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="c8587-138">12 000 utilisateurs distants concurrents</span><span class="sxs-lookup"><span data-stu-id="c8587-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-139">Surveillance et archivage</span><span class="sxs-lookup"><span data-stu-id="c8587-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="c8587-140">Dans Lync Server 2013, les services front-end d’analyse et d’archivage s’exécutent désormais sur chaque serveur frontal, et non sur des rôles serveur distincts.</span><span class="sxs-lookup"><span data-stu-id="c8587-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="c8587-141">La surveillance et l’archivage requièrent un magasin de base de données chacun.</span><span class="sxs-lookup"><span data-stu-id="c8587-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="c8587-142">Si vous exécutez également Exchange 2013, vous pouvez conserver vos données d’archivage dans Exchange, au lieu d’une base de données SQL dédiée.</span><span class="sxs-lookup"><span data-stu-id="c8587-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-143">Un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c8587-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="c8587-144">Le serveur de médiation en fonction du serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante aux utilisateurs de la liste.</span><span class="sxs-lookup"><span data-stu-id="c8587-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="c8587-145">Pour un serveur de médiation autonome, voir la section «serveur de médiation» plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c8587-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-146">One Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="c8587-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c8587-147">Nous vous recommandons vivement de recourir à des serveurs Standard Edition pour héberger les utilisateurs, que vous utilisez toujours deux serveurs, associés à des recommandations en <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">matière de planification de haute disponibilité et de récupération d’urgence dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c8587-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="c8587-148">Chaque serveur dans la paire peut accueillir jusqu’à 2 500 utilisateurs et, si un serveur tombe en panne, le serveur restant peut prendre en charge les utilisateurs 5 000 dans le cas d’un basculement.</span><span class="sxs-lookup"><span data-stu-id="c8587-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="c8587-149">Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="c8587-150">Dans ce cas, envisagez d’ajouter d’autres serveurs Standard Edition ou de migrer vers Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c8587-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="c8587-151">serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c8587-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-152">Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c8587-153">Dans un pool frontal, vous devez disposer d’un serveur frontal pour chaque 6 660 hébergé dans le pool, en partant du principe que la technologie hyperthreading est activée sur tous les serveurs du pool et que le matériel du serveur répond aux recommandations des [plateformes matérielles pour Lync. Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="c8587-154">Le nombre maximal d’utilisateurs dans une liste frontale est de 80 000, en supposant que la technologie hyperthreading est activée sur tous les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c8587-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="c8587-155">Si vous avez plus d’utilisateurs 80 000 sur un site, vous pouvez déployer plusieurs pools front-end.</span><span class="sxs-lookup"><span data-stu-id="c8587-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="c8587-156">Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, incluez les utilisateurs sur les appareils de succursales Survivables et les serveurs de succursales Survivables dans les succursales associées à ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c8587-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="c8587-157">Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c8587-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="c8587-158">Par exemple, si vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions des utilisateurs 6000 doivent être transférées vers les quatre autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="c8587-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="c8587-159">Les quatre serveurs restants disposent chacun de 7500 utilisateurs, ce qui correspond à un nombre supérieur à celui recommandé.</span><span class="sxs-lookup"><span data-stu-id="c8587-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="c8587-160">Si, au lieu de cela, vous avez commencé à utiliser six serveurs front-end pour vos utilisateurs 30 000, le nombre total d’utilisateurs 5000 sera déplacé sur les cinq autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="c8587-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="c8587-161">Ces cinq serveurs seront chacun des utilisateurs de 6000, qui se trouve dans la plage recommandée.</span><span class="sxs-lookup"><span data-stu-id="c8587-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="c8587-162">Le nombre maximal d’utilisateurs dans une liste frontale est de 80 000.</span><span class="sxs-lookup"><span data-stu-id="c8587-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="c8587-163">Le nombre maximal de serveurs frontaux dans un pool est de 12.</span><span class="sxs-lookup"><span data-stu-id="c8587-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="c8587-164">Dans le cas d’un pool frontal avec des utilisateurs 80 000, douze serveurs frontaux sont suffisants pour les performances, dans les déploiements standard qui suivent les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="c8587-165">Les déploiements conçus pour prendre en charge le basculement de reprise après sinistre présupposent qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, dans lesquels chaque pool dispose d’un serveur frontal suffisant pour répondre aux besoins des utilisateurs dans les deux pools doit être en échec. sur l’autre.</span><span class="sxs-lookup"><span data-stu-id="c8587-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="c8587-166">Le nombre d’utilisateurs pris en charge avec une bonne performance par un pool frontal particulier peuvent différer de ces numéros pour les raisons suivantes:</span><span class="sxs-lookup"><span data-stu-id="c8587-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="c8587-167">Le matériel de votre serveur frontal ne répond pas aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="c8587-168">L’utilisation de votre organisation diffère considérablement de celle des modèles utilisateur, par exemple un trafic de conférences plus important.</span><span class="sxs-lookup"><span data-stu-id="c8587-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8587-169">Dans Lync Server 2013, les bases de données de présence sont désormais hébergées sur des serveurs frontaux, contrairement à Lync Server 2010 où elles étaient hébergées sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c8587-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="c8587-170">En d’autres termes, il n’est pas possible de violer les performances et la capacité de votre serveur frontal grâce aux recommandations indiquées dans cette section et dans les <A href="lync-server-2013-server-hardware-platforms.md">plates-formes matérielles pour Lync server 2013</A>, quel que soit le nombre d’utilisateurs hébergés par vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c8587-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="c8587-171">Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, en fonction du modèle utilisateur, tel qu’il est défini dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-172">Bande passante moyenne par utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8587-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="c8587-173">Besoins en bande passante par serveur frontal avec les utilisateurs 6 660</span><span class="sxs-lookup"><span data-stu-id="c8587-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-174">1,3 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="c8587-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="c8587-175">13 Mbits/s</span><span class="sxs-lookup"><span data-stu-id="c8587-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c8587-176">Pour améliorer les performances multimédias de la fonctionnalité de conférence A/V et de médiation du serveur de médiation sur votre serveur frontal, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c8587-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="c8587-177">RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c8587-178">Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c8587-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c8587-179">Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c8587-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="c8587-180">Nombre maximal de conférences</span><span class="sxs-lookup"><span data-stu-id="c8587-180">Conferencing Maximums</span></span>

<span data-ttu-id="c8587-181">Dans la plupart des cas, il est possible que 5% des utilisateurs d’un groupe puissent participer à une conférence en une seule fois, un groupe d’utilisateurs 80 000 peut avoir environ 4 000 utilisateurs dans les conférences en même temps.</span><span class="sxs-lookup"><span data-stu-id="c8587-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="c8587-182">Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants.</span><span class="sxs-lookup"><span data-stu-id="c8587-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="c8587-183">Il n’y a pas de limite fixe pour le nombre réel de conférences autorisées, et l’utilisation réelle détermine la performance réelle.</span><span class="sxs-lookup"><span data-stu-id="c8587-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="c8587-184">Par exemple, si votre organisation possède de nombreuses conférences en mode mixte que celles supposées du modèle utilisateur, il se peut que vous deviez déployer des serveurs frontaux ou des serveurs de conférence A/V à partir des recommandations de ce document.</span><span class="sxs-lookup"><span data-stu-id="c8587-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="c8587-185">Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="c8587-186">La taille de conférence maximale prise en charge hébergée par un pool frontal Lync Server 2013 standard, qui héberge également les utilisateurs est 250 participants.</span><span class="sxs-lookup"><span data-stu-id="c8587-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="c8587-187">Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées.</span><span class="sxs-lookup"><span data-stu-id="c8587-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="c8587-188">Par exemple, dans une liste de douze serveurs frontaux et d’utilisateurs 80 000, pendant la Conférence 250-utilisateur, Lync Server prend en charge 3 750 utilisateurs qui participent à des conférences plus petites.</span><span class="sxs-lookup"><span data-stu-id="c8587-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="c8587-189">Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou le serveur Standard Edition Server, Lync Server prend en charge au moins 125 d’autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur hébergeant une conférence 250-utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c8587-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="c8587-190">Pour permettre à des conférences avec des utilisateurs de 250 et 1000, vous pouvez configurer une liste frontale distincte pour qu’elle héberge ces conférences.</span><span class="sxs-lookup"><span data-stu-id="c8587-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="c8587-191">Ce pool frontal n’hébergera aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c8587-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="c8587-192">Pour plus d’informations, consultez [prise en charge de grandes réunions à l’aide de Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="c8587-193">Si votre organisation possède de nombreuses conférences en mode mixte que celles supposées du modèle utilisateur, il est possible que vous deviez déployer des serveurs frontaux supplémentaires par rapport aux recommandations de ce document (jusqu’à un maximum de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="c8587-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="c8587-194">Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="c8587-195">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c8587-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-196">Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c8587-197">Vous devez déployer un serveur Edge pour tous les utilisateurs de 12 000 distants qui accèdent à un site en même temps.</span><span class="sxs-lookup"><span data-stu-id="c8587-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c8587-198">Au minimum, nous vous conseillons d’utiliser deux serveurs Edge pour une disponibilité élevée.</span><span class="sxs-lookup"><span data-stu-id="c8587-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="c8587-199">Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c8587-200">Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, incluez les utilisateurs sur les appareils de succursales Survivables et les serveurs de succursales Survivables dans les succursales associées à un pool frontal sur ce site.</span><span class="sxs-lookup"><span data-stu-id="c8587-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-201">Pour améliorer les performances du service Edge de conférence A/V sur votre serveur Edge, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="c8587-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="c8587-202">RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c8587-203">Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c8587-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c8587-204">Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c8587-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="c8587-205">directeur</span><span class="sxs-lookup"><span data-stu-id="c8587-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-206">Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c8587-207">Si vous déployez le rôle de serveur Directeur, nous vous recommandons de déployer un directeur pour tous les utilisateurs de 12 000 distants qui accèdent à un site en même temps.</span><span class="sxs-lookup"><span data-stu-id="c8587-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c8587-208">Nous recommandons au minimum deux directeurs pour une disponibilité élevée.</span><span class="sxs-lookup"><span data-stu-id="c8587-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="c8587-209">Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c8587-210">Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, incluez les utilisateurs hébergés sur des appareils de succursales Survivables et des serveurs de succursales survivant dans les succursales associées à un pool frontal sur ce site.</span><span class="sxs-lookup"><span data-stu-id="c8587-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="c8587-211">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c8587-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-212">Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c8587-213">Si vous collocate un serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante aux utilisateurs de la liste.</span><span class="sxs-lookup"><span data-stu-id="c8587-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="c8587-214">Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, dont le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, dont vous disposez, le nombre de pairs de passerelle les contrôles, le trafic horaire occupé par le biais de ces passerelles et le pourcentage d’appels avec des éléments multimédias qui contournent le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c8587-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="c8587-215">Les tableaux suivants décrivent le nombre d’appels simultanés qu’un serveur de médiation peut gérer, en partant du principe que le matériel requis pour les serveurs de médiation répond à la configuration requise dans les [plates-formes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) et ce Hyper-Threading. est activé.</span><span class="sxs-lookup"><span data-stu-id="c8587-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="c8587-216">Pour plus d’informations sur la modularité du serveur de médiation, voir [estimation de l’utilisation de la voix et du trafic pour Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) et [recommandations de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="c8587-217">Toutes les tables suivantes présupposent que l’utilisation est résumée dans les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="c8587-218">Capacité du serveur de médiation autonome: 70% des utilisateurs internes et 30% des utilisateurs externes avec la capacité de non-contournement de l’appel (transcodage de média effectué par le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="c8587-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-219">Matériel serveur</span><span class="sxs-lookup"><span data-stu-id="c8587-219">Server hardware</span></span></th>
<th><span data-ttu-id="c8587-220">Nombre maximal d’appels</span><span class="sxs-lookup"><span data-stu-id="c8587-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="c8587-221">Nombre maximal de lignes T1</span><span class="sxs-lookup"><span data-stu-id="c8587-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="c8587-222">Nombre maximal de lignes E1</span><span class="sxs-lookup"><span data-stu-id="c8587-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-223">Biprocesseur, six cœurs, processeur 2,26 GHz multithreads <strong>avec technologie Hyper-Threading désactivée</strong>, 32 Go de mémoire et une carte réseau double port.</span><span class="sxs-lookup"><span data-stu-id="c8587-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c8587-224">1100</span><span class="sxs-lookup"><span data-stu-id="c8587-224">1100</span></span></p></td>
<td><p><span data-ttu-id="c8587-225">46</span><span class="sxs-lookup"><span data-stu-id="c8587-225">46</span></span></p></td>
<td><p><span data-ttu-id="c8587-226">35</span><span class="sxs-lookup"><span data-stu-id="c8587-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-227">Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et une carte réseau double port.</span><span class="sxs-lookup"><span data-stu-id="c8587-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c8587-228">1500</span><span class="sxs-lookup"><span data-stu-id="c8587-228">1500</span></span></p></td>
<td><p><span data-ttu-id="c8587-229">63</span><span class="sxs-lookup"><span data-stu-id="c8587-229">63</span></span></p></td>
<td><p><span data-ttu-id="c8587-230">47</span><span class="sxs-lookup"><span data-stu-id="c8587-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c8587-231">Bien que les serveurs dotés de 32 Go de mémoire aient été utilisés pour le test de performance, les serveurs dotés de 16 Go de mémoire sont pris en charge pour le serveur de médiation autonome et permettent de fournir les performances indiquées dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c8587-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="c8587-232">Capacité du serveur de médiation (serveur de médiation en fonction du serveur frontal) 70% des utilisateurs internes et de 30% des utilisateurs externes, sans ignorer la capacité d’appel (traitement multimédia effectué par le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="c8587-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-233">Matériel serveur</span><span class="sxs-lookup"><span data-stu-id="c8587-233">Server hardware</span></span></th>
<th><span data-ttu-id="c8587-234">Nombre maximal d’appels</span><span class="sxs-lookup"><span data-stu-id="c8587-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-235">Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et 2 cartes réseau de 1 Go.</span><span class="sxs-lookup"><span data-stu-id="c8587-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="c8587-236">150</span><span class="sxs-lookup"><span data-stu-id="c8587-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c8587-237">Ce nombre est beaucoup plus petit que les numéros du serveur de médiation autonome dans la mesure où le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les utilisateurs de 6600 sur le serveur, en plus du transcodage nécessaire pour les appels vocaux.</span><span class="sxs-lookup"><span data-stu-id="c8587-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c8587-238">Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="c8587-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="c8587-239">RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c8587-240">Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c8587-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c8587-241">Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c8587-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="c8587-242">serveur principal</span><span class="sxs-lookup"><span data-stu-id="c8587-242">Back End Server</span></span>

<span data-ttu-id="c8587-243">Dans Lync Server 2013, les bases de données de présence sont situées sur les serveurs frontaux au lieu du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c8587-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="c8587-244">Cela a entraîné une nécessité plus simple pour chaque serveur principal de Lync Server 2013, qui équivaut à la configuration matérielle requise pour le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c8587-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="c8587-245">Différences entre ce niveau et Lync Server 2010, où le serveur principal est requis pour être un serveur de qualité nettement supérieur à 25 disques.</span><span class="sxs-lookup"><span data-stu-id="c8587-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="c8587-246">Toutefois, la charge de travail des serveurs dorsaux est toujours telle que vous ne devriez pas être satisfait aux recommandations en matière de matériel indiquées dans cette section et dans les [plates-formes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c8587-247">Pour garantir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer la mise en miroir du serveur.</span><span class="sxs-lookup"><span data-stu-id="c8587-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="c8587-248">Pour plus d’informations, voir [disponibilité du serveur principal dans Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c8587-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="c8587-249">Surveillance et archivage</span><span class="sxs-lookup"><span data-stu-id="c8587-249">Monitoring and Archiving</span></span>

<span data-ttu-id="c8587-250">Dans Lync Server 2013, si vous déployez la surveillance ou l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, au lieu de rôles de serveur distincts.</span><span class="sxs-lookup"><span data-stu-id="c8587-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="c8587-251">La surveillance et l’archivage de chacune utilise toujours leur propre magasin de base de données, indépendamment du magasin principal.</span><span class="sxs-lookup"><span data-stu-id="c8587-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="c8587-252">Par ailleurs, si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange plutôt que dans un magasin SQL dédié.</span><span class="sxs-lookup"><span data-stu-id="c8587-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="c8587-253">Le tableau ci-dessous indique approximativement la quantité de stockage de base de données nécessaire par utilisateur par jour pour les données de surveillance et d’archivage.</span><span class="sxs-lookup"><span data-stu-id="c8587-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="c8587-254"><strong>CDR (surveillance)</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c8587-255"><strong>QoE (surveillance)</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c8587-256"><strong>Archivage</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-257">Espace disque requis par utilisateur par jour</span><span class="sxs-lookup"><span data-stu-id="c8587-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="c8587-258">49 Ko</span><span class="sxs-lookup"><span data-stu-id="c8587-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="c8587-259">28 Ko</span><span class="sxs-lookup"><span data-stu-id="c8587-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="c8587-260">57 Ko</span><span class="sxs-lookup"><span data-stu-id="c8587-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8587-261">Microsoft a utilisé le matériel décrit dans le tableau ci-dessous pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances.</span><span class="sxs-lookup"><span data-stu-id="c8587-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="c8587-262">Le test collectait les données de deux pools front-end, chacun contenant des utilisateurs 80 000.</span><span class="sxs-lookup"><span data-stu-id="c8587-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="c8587-263">Matériel utilisé pour le test des performances d’archivage et de la surveillance</span><span class="sxs-lookup"><span data-stu-id="c8587-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8587-264">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="c8587-264">Hardware component</span></span></th>
<th><span data-ttu-id="c8587-265">Recommandation</span><span class="sxs-lookup"><span data-stu-id="c8587-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-266">Processeur</span><span class="sxs-lookup"><span data-stu-id="c8587-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="c8587-267">Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="c8587-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-268">Mémoire</span><span class="sxs-lookup"><span data-stu-id="c8587-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="c8587-269">48 Go</span><span class="sxs-lookup"><span data-stu-id="c8587-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-270">Disque</span><span class="sxs-lookup"><span data-stu-id="c8587-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="c8587-271">25 disques durs avec une vitesse de 10 000 tr/min et 300 Go sur chaque disque, avec la configuration suivante</span><span class="sxs-lookup"><span data-stu-id="c8587-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8587-272"><strong>Lecteur</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="c8587-273"><strong>Configuration RAID</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c8587-274"><strong>Nombre de disques</strong></span><span class="sxs-lookup"><span data-stu-id="c8587-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-275">Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque</span><span class="sxs-lookup"><span data-stu-id="c8587-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="c8587-276">1+0</span><span class="sxs-lookup"><span data-stu-id="c8587-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="c8587-277">Seiz</span><span class="sxs-lookup"><span data-stu-id="c8587-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-278">Fichier journal de la base de données d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="c8587-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="c8587-279">1</span><span class="sxs-lookup"><span data-stu-id="c8587-279">1</span></span></p></td>
<td><p><span data-ttu-id="c8587-280">2</span><span class="sxs-lookup"><span data-stu-id="c8587-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-281">Fichier journal de la base de données QoE</span><span class="sxs-lookup"><span data-stu-id="c8587-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="c8587-282">1</span><span class="sxs-lookup"><span data-stu-id="c8587-282">1</span></span></p></td>
<td><p><span data-ttu-id="c8587-283">2</span><span class="sxs-lookup"><span data-stu-id="c8587-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8587-284">Fichier journal de la base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="c8587-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="c8587-285">1</span><span class="sxs-lookup"><span data-stu-id="c8587-285">1</span></span></p></td>
<td><p><span data-ttu-id="c8587-286">2</span><span class="sxs-lookup"><span data-stu-id="c8587-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8587-287">Réseau</span><span class="sxs-lookup"><span data-stu-id="c8587-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8587-288">1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</span><span class="sxs-lookup"><span data-stu-id="c8587-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8587-289">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c8587-289">In This Section</span></span>

  - [<span data-ttu-id="c8587-290">Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8587-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="c8587-291">Recommandations en matière de déploiement pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8587-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

