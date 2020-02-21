---
title: Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7665a8edb5e77514633de5e66a063ab509fdd821
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="c95dc-102">Planification de la capacité pour Lync Server 2013 à l’aide des modèles utilisateur</span><span class="sxs-lookup"><span data-stu-id="c95dc-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c95dc-103">_**Dernière modification de la rubrique :** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="c95dc-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="c95dc-104">Cette section fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="c95dc-105">Plateforme matérielle testée</span><span class="sxs-lookup"><span data-stu-id="c95dc-105">Tested Hardware Platform</span></span>

<span data-ttu-id="c95dc-106">Tous les résultats de performances et les recommandations de déploiement de cette section sont basés sur les tests de performances sur les serveurs qui exécutent le matériel décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c95dc-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="c95dc-107">Nous vous recommandons d’utiliser un matériel similaire.</span><span class="sxs-lookup"><span data-stu-id="c95dc-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="c95dc-108">Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres.</span><span class="sxs-lookup"><span data-stu-id="c95dc-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="c95dc-109">Notez que ces recommandations matérielles sont plus élevées que celles des versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c95dc-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="c95dc-110">Matériel utilisé dans les tests de performances</span><span class="sxs-lookup"><span data-stu-id="c95dc-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-111">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="c95dc-111">Hardware component</span></span></th>
<th><span data-ttu-id="c95dc-112">Recommandé</span><span class="sxs-lookup"><span data-stu-id="c95dc-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-113">UC</span><span class="sxs-lookup"><span data-stu-id="c95dc-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="c95dc-114">Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="c95dc-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="c95dc-115">Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c95dc-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-116">Mémoire</span><span class="sxs-lookup"><span data-stu-id="c95dc-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="c95dc-117">32 Go</span><span class="sxs-lookup"><span data-stu-id="c95dc-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-118">Disque</span><span class="sxs-lookup"><span data-stu-id="c95dc-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c95dc-119">8 disques durs 10 000-RPM avec au moins 72 Go d’espace disque disponible.</span><span class="sxs-lookup"><span data-stu-id="c95dc-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="c95dc-120">Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</span><span class="sxs-lookup"><span data-stu-id="c95dc-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="c95dc-121">-Des</span><span class="sxs-lookup"><span data-stu-id="c95dc-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c95dc-122">Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tours/minute.</span><span class="sxs-lookup"><span data-stu-id="c95dc-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-123">Réseau</span><span class="sxs-lookup"><span data-stu-id="c95dc-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c95dc-124">1 carte réseau double port, 1 Gbps ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</span><span class="sxs-lookup"><span data-stu-id="c95dc-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="c95dc-125">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="c95dc-125">Summary of Results</span></span>

<span data-ttu-id="c95dc-126">Le tableau suivant résume ces recommandations.</span><span class="sxs-lookup"><span data-stu-id="c95dc-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-127">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="c95dc-127">Server role</span></span></th>
<th><span data-ttu-id="c95dc-128">Nombre maximal d’utilisateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="c95dc-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-129">Pool frontal avec douze serveurs frontaux et un serveur principal ou une paire de serveurs principaux en miroir.</span><span class="sxs-lookup"><span data-stu-id="c95dc-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="c95dc-130">80 000 utilisateurs uniques connectés simultanément, plus 50% de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40% d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="c95dc-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-131">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="c95dc-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="c95dc-132">Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de conférence de 250 utilisateurs, et une seule de ces grandes conférences en cours d’exécution à la fois.</span><span class="sxs-lookup"><span data-stu-id="c95dc-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c95dc-133">En outre, vous pouvez prendre en charge des conférences importantes entre 250 et 1000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les grandes conférences.</span><span class="sxs-lookup"><span data-stu-id="c95dc-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="c95dc-134">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-supporting-large-meetings.md">prise en charge de grandes réunions à l’aide de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c95dc-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-135">Un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c95dc-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="c95dc-136">12 000 utilisateurs distants simultanés</span><span class="sxs-lookup"><span data-stu-id="c95dc-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-137">Un directeur</span><span class="sxs-lookup"><span data-stu-id="c95dc-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="c95dc-138">12 000 utilisateurs distants simultanés</span><span class="sxs-lookup"><span data-stu-id="c95dc-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-139">Surveillance et archivage</span><span class="sxs-lookup"><span data-stu-id="c95dc-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="c95dc-140">Dans Lync Server 2013, les services frontaux de surveillance et d’archivage s’exécutent désormais sur chaque serveur frontal, et non sur des rôles serveur distincts.</span><span class="sxs-lookup"><span data-stu-id="c95dc-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="c95dc-141">La surveillance et l’archivage nécessitent toujours leurs propres magasins de base de données.</span><span class="sxs-lookup"><span data-stu-id="c95dc-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="c95dc-142">Si vous exécutez également Exchange 2013, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.</span><span class="sxs-lookup"><span data-stu-id="c95dc-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-143">Un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c95dc-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="c95dc-144">Le serveur de médiation colocalisé avec le serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante pour les utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c95dc-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="c95dc-145">Pour un serveur de médiation autonome, consultez la section « serveur de médiation » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c95dc-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-146">Un serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="c95dc-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c95dc-147">Si vous utilisez des serveurs Standard Edition pour héberger des utilisateurs, nous vous recommandons vivement d’utiliser deux serveurs, associés à l’aide des recommandations de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c95dc-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="c95dc-148">Chaque serveur de la paire peut héberger jusqu’à 2 500 utilisateurs et, si un serveur échoue, le serveur restant peut prendre en charge 5 000 utilisateurs dans un scénario de basculement.</span><span class="sxs-lookup"><span data-stu-id="c95dc-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="c95dc-149">Si votre déploiement inclut une quantité importante de trafic audio ou vidéo, les performances du serveur peuvent être affectées à plus de 2 500 utilisateurs par serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="c95dc-150">Dans ce cas, vous devez envisager d’ajouter des serveurs Standard Edition ou de passer à Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c95dc-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="c95dc-151">serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c95dc-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-152">Les pools étirés ne sont pas pris en charge pour ce rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c95dc-153">Dans un pool frontal, vous devez disposer d’un serveur frontal pour tous les 6 660 utilisateurs hébergés dans le pool, en supposant que la technologie Hyper-Threading est activée sur tous les serveurs du pool et que le matériel du serveur répond aux recommandations dans les [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="c95dc-154">Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000, en supposant que la technologie Hyper-Threading est activée sur tous les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c95dc-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="c95dc-155">Si vous avez plus de 80 000 utilisateurs sur un site, vous pouvez déployer plusieurs pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="c95dc-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="c95dc-156">Lorsque vous comptez le nombre d’utilisateurs d’un pool frontal, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c95dc-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="c95dc-157">Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement aux autres serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c95dc-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="c95dc-158">Par exemple, si vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur est indisponible, les connexions de 6000 doivent être transférées vers les quatre autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="c95dc-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="c95dc-159">Les quatre serveurs restants auront chacun 7500 utilisateurs, ce qui est plus grand que recommandé.</span><span class="sxs-lookup"><span data-stu-id="c95dc-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="c95dc-160">Si, au lieu de cela, vous avez commencé avec six serveurs frontaux pour vos utilisateurs de 30 000 et que l’autre est devenu indisponible, un total de 5000 utilisateurs seront déplacés vers les cinq serveurs restants.</span><span class="sxs-lookup"><span data-stu-id="c95dc-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="c95dc-161">Ces cinq serveurs sont tous les utilisateurs de l’hôte 6000, qui se trouvent dans la plage recommandée.</span><span class="sxs-lookup"><span data-stu-id="c95dc-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="c95dc-162">Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000.</span><span class="sxs-lookup"><span data-stu-id="c95dc-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="c95dc-163">Le nombre maximal de serveurs frontaux dans un pool est de 12.</span><span class="sxs-lookup"><span data-stu-id="c95dc-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="c95dc-164">Pour un pool frontal avec des utilisateurs 80 000, douze serveurs frontaux sont suffisants pour les performances, dans des déploiements classiques qui suivent les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="c95dc-165">Les déploiements conçus pour prendre en charge le basculement de récupération d’urgence supposent qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, où chaque pool dispose de serveurs frontaux suffisants pour accueillir les utilisateurs des deux pools en cas de défaillance d’un pool. vers l’autre.</span><span class="sxs-lookup"><span data-stu-id="c95dc-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="c95dc-166">Le nombre d’utilisateurs pris en charge avec de bonnes performances par un pool frontal particulier peut différer de ces chiffres pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="c95dc-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="c95dc-167">Le matériel de vos serveurs frontaux ne répond pas aux recommandations des [plateformes matérielles de serveur pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="c95dc-168">L’utilisation de votre organisation diffère de manière significative de celle des modèles utilisateur, en raison d’un trafic de conférence plus important par exemple.</span><span class="sxs-lookup"><span data-stu-id="c95dc-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c95dc-169">Dans Lync Server 2013, les bases de données de présence sont désormais hébergées sur des serveurs frontaux, contrairement à Lync Server 2010 où elles étaient hébergées sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c95dc-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="c95dc-170">Cela signifie que les performances de disque et la capacité de vos serveurs frontaux ne doivent pas être compromises par les recommandations répertoriées plus haut dans cette section et dans les <A href="lync-server-2013-server-hardware-platforms.md">plateformes matérielles de serveur pour Lync Server 2013</A>, quel que soit le nombre d’utilisateurs hébergés par vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c95dc-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="c95dc-171">Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, étant donné le modèle utilisateur, tel qu’il est défini dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-172">Bande passante moyenne par utilisateur</span><span class="sxs-lookup"><span data-stu-id="c95dc-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="c95dc-173">Besoins en bande passante par serveur frontal avec 6 660 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c95dc-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-174">1,3 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="c95dc-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="c95dc-175">13 Mbits/s</span><span class="sxs-lookup"><span data-stu-id="c95dc-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-176">Pour améliorer les performances multimédia de la fonctionnalité de conférence A/V et du serveur de médiation colocalisée sur vos serveurs frontaux, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c95dc-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="c95dc-177">RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c95dc-178">Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>côté réception dans Windows Server 2008 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c95dc-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c95dc-179">Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c95dc-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="c95dc-180">Nombre maximal de conférences</span><span class="sxs-lookup"><span data-stu-id="c95dc-180">Conferencing Maximums</span></span>

<span data-ttu-id="c95dc-181">Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent assister à une conférence en même temps, donc un pool de 80 000 utilisateurs peut avoir 4 000 utilisateurs en conférence simultanément.</span><span class="sxs-lookup"><span data-stu-id="c95dc-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="c95dc-182">Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo par exemple) et du nombre de participants.</span><span class="sxs-lookup"><span data-stu-id="c95dc-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="c95dc-183">Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles.</span><span class="sxs-lookup"><span data-stu-id="c95dc-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="c95dc-184">Par exemple, si le nombre de conférences en mode mixte dans votre organisation est anormalement élevé par rapport au modèle utilisateur, vous devrez peut-être déployer un nombre de serveurs frontaux et de serveurs de conférence A/V plus important que celui recommandé dans ce document.</span><span class="sxs-lookup"><span data-stu-id="c95dc-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="c95dc-185">Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="c95dc-186">La taille de conférence maximale prise en charge par un pool frontal Lync Server 2013 classique qui héberge également les utilisateurs est de 250 participants.</span><span class="sxs-lookup"><span data-stu-id="c95dc-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="c95dc-187">Pendant une conférence de 250 utilisateurs, le pool prend toujours en charge d’autres conférences, de sorte qu’un total de 5% des utilisateurs du pool se trouvent dans des conférences simultanées.</span><span class="sxs-lookup"><span data-stu-id="c95dc-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="c95dc-188">Par exemple, dans un pool de douze serveurs frontaux et 80 000 utilisateurs, tandis que la Conférence utilisateur 250 se produit, Lync Server prend en charge 3 750 autres utilisateurs participant à des conférences plus petites.</span><span class="sxs-lookup"><span data-stu-id="c95dc-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="c95dc-189">Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou le serveur Standard Edition, Lync Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c95dc-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="c95dc-190">Pour activer les conférences avec des utilisateurs entre 250 et 1000, vous pouvez configurer un pool frontal distinct pour héberger ces conférences.</span><span class="sxs-lookup"><span data-stu-id="c95dc-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="c95dc-191">Ce pool frontal n’héberge aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="c95dc-192">Pour plus d’informations, consultez la rubrique [prise en charge de grandes réunions à l’aide de Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="c95dc-193">Si votre organisation a de nombreuses conférences en mode mixte que celles supposées dans le modèle utilisateur, vous devrez peut-être déployer davantage de serveurs frontaux que les recommandations de ce document (jusqu’à une limite de 12 FEs).</span><span class="sxs-lookup"><span data-stu-id="c95dc-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="c95dc-194">Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="c95dc-195">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c95dc-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-196">Les pools étirés ne sont pas pris en charge pour ce rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c95dc-197">Vous devez déployer un serveur Edge pour chaque 12 000 utilisateurs distants qui accèdent simultanément à un site.</span><span class="sxs-lookup"><span data-stu-id="c95dc-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c95dc-198">Nous vous conseillons au moins deux serveurs Edge pour une disponibilité élevée.</span><span class="sxs-lookup"><span data-stu-id="c95dc-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="c95dc-199">Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c95dc-200">Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.</span><span class="sxs-lookup"><span data-stu-id="c95dc-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-201">Pour améliorer les performances du service Edge de conférence A/V sur vos serveurs Edge, vous devez activer le partage du trafic entrant (RSS, Receive-Side Scaling) sur les cartes réseau de vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="c95dc-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="c95dc-202">RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c95dc-203">Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>côté réception dans Windows Server 2008 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c95dc-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c95dc-204">Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c95dc-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="c95dc-205">48000b</span><span class="sxs-lookup"><span data-stu-id="c95dc-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-206">Les pools étirés ne sont pas pris en charge pour ce rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c95dc-207">Si vous déployez le rôle de serveur Directeur, nous vous recommandons de déployer un directeur pour chaque 12 000 utilisateurs distants qui accèdent simultanément à un site.</span><span class="sxs-lookup"><span data-stu-id="c95dc-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c95dc-208">Nous vous conseillons au moins deux directeurs pour une disponibilité élevée.</span><span class="sxs-lookup"><span data-stu-id="c95dc-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="c95dc-209">Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c95dc-210">Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.</span><span class="sxs-lookup"><span data-stu-id="c95dc-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="c95dc-211">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c95dc-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-212">Les pools étirés ne sont pas pris en charge pour ce rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c95dc-213">Si vous colocaliser serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante pour les utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="c95dc-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="c95dc-214">Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, dont le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP dont vous disposez, le nombre d’homologues de passerelle que chaque pool de serveurs de médiation les contrôles, le trafic des heures de pointe via ces passerelles et le pourcentage d’appels avec des médias qui contournent le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c95dc-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="c95dc-215">Les tableaux suivants fournissent une indication du nombre d’appels simultanés qu’un serveur de médiation peut gérer, en supposant que le matériel pour les serveurs de médiation répond aux exigences des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) et que la technologie Hyper-Threading soit activée.</span><span class="sxs-lookup"><span data-stu-id="c95dc-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="c95dc-216">Pour plus d’informations sur l’extensibilité du serveur de médiation, voir [estimation de l’utilisation et du trafic vocaux pour Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) et [les instructions de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="c95dc-217">Tous les tableaux ci-dessous présupposent une utilisation telle que résumée dans les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="c95dc-218">Capacité de serveur de médiation autonome : 70% d’utilisateurs internes, 30% d’utilisateurs externes avec une capacité d’appel sans contournement (transcodage multimédia effectué par le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="c95dc-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-219">Matériel serveur</span><span class="sxs-lookup"><span data-stu-id="c95dc-219">Server hardware</span></span></th>
<th><span data-ttu-id="c95dc-220">Nombre maximal d’appels</span><span class="sxs-lookup"><span data-stu-id="c95dc-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="c95dc-221">Nombre maximal de lignes T1</span><span class="sxs-lookup"><span data-stu-id="c95dc-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="c95dc-222">Nombre maximal de lignes E1</span><span class="sxs-lookup"><span data-stu-id="c95dc-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-223">Double processeur, principal, cadencé à 2,26 GHz <strong>avec Hyper-Threading désactivé</strong>, avec une mémoire de 32 Go et une carte réseau double port.</span><span class="sxs-lookup"><span data-stu-id="c95dc-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c95dc-224">1100</span><span class="sxs-lookup"><span data-stu-id="c95dc-224">1100</span></span></p></td>
<td><p><span data-ttu-id="c95dc-225">46</span><span class="sxs-lookup"><span data-stu-id="c95dc-225">46</span></span></p></td>
<td><p><span data-ttu-id="c95dc-226">35</span><span class="sxs-lookup"><span data-stu-id="c95dc-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-227">Dual Processor, hex Core, processeur Hyper-Threading 2,26 GHz, 1 32 Go de mémoire et une carte réseau double port.</span><span class="sxs-lookup"><span data-stu-id="c95dc-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c95dc-228">1500</span><span class="sxs-lookup"><span data-stu-id="c95dc-228">1500</span></span></p></td>
<td><p><span data-ttu-id="c95dc-229">63</span><span class="sxs-lookup"><span data-stu-id="c95dc-229">63</span></span></p></td>
<td><p><span data-ttu-id="c95dc-230">47</span><span class="sxs-lookup"><span data-stu-id="c95dc-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-231">Bien que des serveurs dotés de 32 Go de mémoire aient été utilisés pour tester les performances, les serveurs ayant 16 Go de mémoire sont pris en charge pour un serveur de médiation autonome et sont suffisants pour fournir les performances indiquées dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="c95dc-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="c95dc-232">Capacité du serveur de médiation (serveur de médiation colocalisé avec le serveur frontal) 70% d’utilisateurs internes, 30% d’utilisateurs externes, capacité d’appel sans contournement (traitement multimédia effectué par le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="c95dc-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-233">Matériel serveur</span><span class="sxs-lookup"><span data-stu-id="c95dc-233">Server hardware</span></span></th>
<th><span data-ttu-id="c95dc-234">Nombre maximal d’appels</span><span class="sxs-lookup"><span data-stu-id="c95dc-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-235">Dual Processor, hex Core, processeur Hyper-Threading 2,26 GHz, avec une mémoire de 32 Go et 2 cartes réseau 1 Go.</span><span class="sxs-lookup"><span data-stu-id="c95dc-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="c95dc-236">150</span><span class="sxs-lookup"><span data-stu-id="c95dc-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-237">Ce nombre est plus petit que les numéros pour le serveur de médiation autonome car le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les 6600 utilisateurs hébergés dessus, en plus du transcodage nécessaire pour les appels vocaux.</span><span class="sxs-lookup"><span data-stu-id="c95dc-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c95dc-238">Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="c95dc-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="c95dc-239">RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c95dc-240">Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>côté réception dans Windows Server 2008 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c95dc-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c95dc-241">Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="c95dc-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="c95dc-242">serveur principal</span><span class="sxs-lookup"><span data-stu-id="c95dc-242">Back End Server</span></span>

<span data-ttu-id="c95dc-243">Dans Lync Server 2013, les bases de données de présence se trouvent sur les serveurs frontaux et non sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c95dc-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="c95dc-244">Cela a permis une configuration plus simple pour chaque serveur principal de Lync Server 2013, ce qui équivaut à la configuration matérielle requise pour le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c95dc-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="c95dc-245">À la différence de Lync Server 2010, le serveur principal devait être un serveur de plus grande qualité avec 25 disques.</span><span class="sxs-lookup"><span data-stu-id="c95dc-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="c95dc-246">Toutefois, la charge de travail des serveurs principaux est toujours telle que vous ne devriez pas ne pas faire face aux recommandations matérielles répertoriées plus haut dans cette section et dans les [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c95dc-247">Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer la mise en miroir du serveur.</span><span class="sxs-lookup"><span data-stu-id="c95dc-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="c95dc-248">Pour plus d’informations, reportez-vous à la rubrique [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c95dc-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="c95dc-249">Surveillance et archivage</span><span class="sxs-lookup"><span data-stu-id="c95dc-249">Monitoring and Archiving</span></span>

<span data-ttu-id="c95dc-250">Dans Lync Server 2013, si vous déployez la surveillance ou l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, et non sur des rôles serveur distincts.</span><span class="sxs-lookup"><span data-stu-id="c95dc-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="c95dc-251">La surveillance et l’archivage utilisent toujours leur propre magasin de bases de données, distinct du magasin principal.</span><span class="sxs-lookup"><span data-stu-id="c95dc-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="c95dc-252">Sinon, si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange au lieu d’un magasin SQL dédié.</span><span class="sxs-lookup"><span data-stu-id="c95dc-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="c95dc-253">Le tableau suivant indique approximativement la proportion de stockage de base de données requise par utilisateur et par jour pour les données de surveillance et d’archivage.</span><span class="sxs-lookup"><span data-stu-id="c95dc-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="c95dc-254"><strong>CDR (surveillance)</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c95dc-255"><strong>QoE (surveillance)</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c95dc-256"><strong>Archivage</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-257">Espace disque requis par utilisateur et par jour</span><span class="sxs-lookup"><span data-stu-id="c95dc-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="c95dc-258">49 KO</span><span class="sxs-lookup"><span data-stu-id="c95dc-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="c95dc-259">28 KO</span><span class="sxs-lookup"><span data-stu-id="c95dc-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="c95dc-260">57 KO</span><span class="sxs-lookup"><span data-stu-id="c95dc-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c95dc-261">Microsoft a utilisé le matériel du tableau suivant pour le serveur de base de données pour la surveillance et l’archivage pendant le test des performances.</span><span class="sxs-lookup"><span data-stu-id="c95dc-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="c95dc-262">Les tests ont collecté les données de deux pools frontaux, chacun contenant 80 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c95dc-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="c95dc-263">Matériel utilisé dans les tests de performances de surveillance et d’archivage</span><span class="sxs-lookup"><span data-stu-id="c95dc-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c95dc-264">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="c95dc-264">Hardware component</span></span></th>
<th><span data-ttu-id="c95dc-265">Recommandé</span><span class="sxs-lookup"><span data-stu-id="c95dc-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-266">UC</span><span class="sxs-lookup"><span data-stu-id="c95dc-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="c95dc-267">Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="c95dc-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-268">Mémoire</span><span class="sxs-lookup"><span data-stu-id="c95dc-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="c95dc-269">48 gigaoctets (Go)</span><span class="sxs-lookup"><span data-stu-id="c95dc-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-270">Disque</span><span class="sxs-lookup"><span data-stu-id="c95dc-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="c95dc-271">disques durs 25 10 000-RPM avec 300 Go sur chaque disque, avec la configuration suivante</span><span class="sxs-lookup"><span data-stu-id="c95dc-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="c95dc-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="c95dc-273"><strong>Configuration RAID</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c95dc-274"><strong>Nombre de disques</strong></span><span class="sxs-lookup"><span data-stu-id="c95dc-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-275">Fichiers de données de base de données d’archivage, d’enregistrement des détails des appels, QoE et archivage, sur un seul lecteur</span><span class="sxs-lookup"><span data-stu-id="c95dc-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="c95dc-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="c95dc-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="c95dc-277">16 </span><span class="sxs-lookup"><span data-stu-id="c95dc-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-278">Fichier journal de la base de données d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="c95dc-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="c95dc-279">0,1</span><span class="sxs-lookup"><span data-stu-id="c95dc-279">1</span></span></p></td>
<td><p><span data-ttu-id="c95dc-280">n°2</span><span class="sxs-lookup"><span data-stu-id="c95dc-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-281">Fichier journal de la base de données QoE</span><span class="sxs-lookup"><span data-stu-id="c95dc-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="c95dc-282">0,1</span><span class="sxs-lookup"><span data-stu-id="c95dc-282">1</span></span></p></td>
<td><p><span data-ttu-id="c95dc-283">n°2</span><span class="sxs-lookup"><span data-stu-id="c95dc-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95dc-284">Fichier journal de la base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="c95dc-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="c95dc-285">0,1</span><span class="sxs-lookup"><span data-stu-id="c95dc-285">1</span></span></p></td>
<td><p><span data-ttu-id="c95dc-286">n°2</span><span class="sxs-lookup"><span data-stu-id="c95dc-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95dc-287">Réseau</span><span class="sxs-lookup"><span data-stu-id="c95dc-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c95dc-288">1 carte réseau double port, 1 Gbps ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</span><span class="sxs-lookup"><span data-stu-id="c95dc-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c95dc-289">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c95dc-289">In This Section</span></span>

  - [<span data-ttu-id="c95dc-290">Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95dc-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="c95dc-291">Instructions de déploiement pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95dc-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

