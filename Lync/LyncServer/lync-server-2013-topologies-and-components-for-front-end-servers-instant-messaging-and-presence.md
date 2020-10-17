---
title: 'Lync Server 2013 : topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503751"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="24bec-102">Topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24bec-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24bec-103">_**Dernière modification de la rubrique :** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="24bec-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="24bec-104">Les seuls composants requis pour la messagerie instantanée et la présence sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="24bec-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="24bec-105">Les serveurs frontaux ou les serveurs Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="24bec-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="24bec-106">Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="24bec-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="24bec-107">Un équilibreur de charge, si vous disposez d’un pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="24bec-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="24bec-108">Pour plus d’informations, reportez-vous à [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24bec-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="24bec-109">Planification du déploiement des pools frontaux</span><span class="sxs-lookup"><span data-stu-id="24bec-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="24bec-110">Dans Lync Server 2013, l’architecture de pool frontal a changé et les modifications apportées affectent la planification et la gestion de vos pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="24bec-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="24bec-111">Nous recommandons que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="24bec-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="24bec-112">Dans Lync Server, l’architecture des pools frontaux utilise un modèle de systèmes distribués, les données de chaque utilisateur étant conservées sur trois serveurs frontaux dans le pool.</span><span class="sxs-lookup"><span data-stu-id="24bec-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="24bec-113">Pour plus d’informations sur cette nouvelle architecture, consultez la rubrique [modifications de la topologie dans Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="24bec-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="24bec-114">Si vous ne souhaitez pas déployer trois serveurs frontaux Enterprise Edition et que vous souhaitez une récupération d’urgence, nous vous recommandons d’utiliser Lync Server Standard Edition et de créer deux pools avec une relation de sauvegarde couplée.</span><span class="sxs-lookup"><span data-stu-id="24bec-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="24bec-115">Cette opération fournit une solution de récupération d’urgence avec seulement deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="24bec-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="24bec-116">Pour plus d’informations sur les topologies et les fonctionnalités de haute disponibilité et de récupération d’urgence, reportez-vous à la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="24bec-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="24bec-117">Planification de la gestion des pools frontaux</span><span class="sxs-lookup"><span data-stu-id="24bec-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="24bec-118">Pour les pools frontaux, suivez les instructions de cette section.</span><span class="sxs-lookup"><span data-stu-id="24bec-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="24bec-119">Vérifier que les pools sont fonctionnels</span><span class="sxs-lookup"><span data-stu-id="24bec-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="24bec-120">Avec le nouveau modèle distribué pour les pools frontaux, certains numéros des serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne.</span><span class="sxs-lookup"><span data-stu-id="24bec-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="24bec-121">Il existe deux modes de perte pour un pool</span><span class="sxs-lookup"><span data-stu-id="24bec-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="24bec-122">Perte de quorum au niveau du groupe de routage, causée par des serveurs de réplication insuffisants pour un groupe de routage particulier.</span><span class="sxs-lookup"><span data-stu-id="24bec-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="24bec-123">Un groupe de routage est une agrégation d’un ensemble d’utilisateurs hébergés dans le pool.</span><span class="sxs-lookup"><span data-stu-id="24bec-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="24bec-124">Chaque groupe de routage dispose de trois réplicas dans le pool : un principal et deux secondaires.</span><span class="sxs-lookup"><span data-stu-id="24bec-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="24bec-125">Perte de quorum au niveau du pool, provoqué lorsque le pool ne comporte pas suffisamment de serveurs d’amorçage.</span><span class="sxs-lookup"><span data-stu-id="24bec-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="24bec-126">Perte de quorum au niveau du groupe de routage</span><span class="sxs-lookup"><span data-stu-id="24bec-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="24bec-127">La première fois que vous démarrez un nouveau pool frontal, il est essentiel que 85% des serveurs soient opérationnels, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="24bec-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="24bec-128">Si le nombre de serveurs en cours d’exécution est moindre, les services peuvent être bloqués dans l’état de démarrage et le pool peut ne pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="24bec-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24bec-129">Nombre total de serveurs dans le pool</span><span class="sxs-lookup"><span data-stu-id="24bec-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="24bec-130">Nombre de serveurs qui doivent être en cours d’exécution pour que le pool démarre pour la première fois</span><span class="sxs-lookup"><span data-stu-id="24bec-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24bec-131">n°2</span><span class="sxs-lookup"><span data-stu-id="24bec-131">2</span></span></p></td>
<td><p><span data-ttu-id="24bec-132">0,1</span><span class="sxs-lookup"><span data-stu-id="24bec-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-133">3</span><span class="sxs-lookup"><span data-stu-id="24bec-133">3</span></span></p></td>
<td><p><span data-ttu-id="24bec-134">3</span><span class="sxs-lookup"><span data-stu-id="24bec-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-135">4 </span><span class="sxs-lookup"><span data-stu-id="24bec-135">4</span></span></p></td>
<td><p><span data-ttu-id="24bec-136">3</span><span class="sxs-lookup"><span data-stu-id="24bec-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-137">5 </span><span class="sxs-lookup"><span data-stu-id="24bec-137">5</span></span></p></td>
<td><p><span data-ttu-id="24bec-138">4 </span><span class="sxs-lookup"><span data-stu-id="24bec-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-139">6 </span><span class="sxs-lookup"><span data-stu-id="24bec-139">6</span></span></p></td>
<td><p><span data-ttu-id="24bec-140">5 </span><span class="sxs-lookup"><span data-stu-id="24bec-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-141">7 </span><span class="sxs-lookup"><span data-stu-id="24bec-141">7</span></span></p></td>
<td><p><span data-ttu-id="24bec-142">5 </span><span class="sxs-lookup"><span data-stu-id="24bec-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-143">8 </span><span class="sxs-lookup"><span data-stu-id="24bec-143">8</span></span></p></td>
<td><p><span data-ttu-id="24bec-144">6 </span><span class="sxs-lookup"><span data-stu-id="24bec-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-145">9 </span><span class="sxs-lookup"><span data-stu-id="24bec-145">9</span></span></p></td>
<td><p><span data-ttu-id="24bec-146">7 </span><span class="sxs-lookup"><span data-stu-id="24bec-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-147">10 </span><span class="sxs-lookup"><span data-stu-id="24bec-147">10</span></span></p></td>
<td><p><span data-ttu-id="24bec-148">8 </span><span class="sxs-lookup"><span data-stu-id="24bec-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-149">a4</span><span class="sxs-lookup"><span data-stu-id="24bec-149">11</span></span></p></td>
<td><p><span data-ttu-id="24bec-150">9 </span><span class="sxs-lookup"><span data-stu-id="24bec-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-151">12 </span><span class="sxs-lookup"><span data-stu-id="24bec-151">12</span></span></p></td>
<td><p><span data-ttu-id="24bec-152">10 </span><span class="sxs-lookup"><span data-stu-id="24bec-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24bec-153">Chaque fois que le pool est démarré, 85% des serveurs doivent être démarrés (comme indiqué dans le tableau précédent).</span><span class="sxs-lookup"><span data-stu-id="24bec-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="24bec-154">Si ce nombre de serveurs ne peut pas être démarré (mais que les serveurs peuvent être démarrés de manière à ne pas être au même niveau que la perte de quorum au niveau du pool), vous pouvez utiliser l’applet de commande **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** pour permettre au pool de récupérer à partir de cette perte de quorum au niveau du groupe de routage et de progresser.</span><span class="sxs-lookup"><span data-stu-id="24bec-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="24bec-155">Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="24bec-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24bec-156">Étant donné que Lync Server utilise la base de données SQL principale comme témoin, si vous arrêtez la base de données principale et basculez vers la copie miroir, et que vous arrêtez suffisamment de serveurs frontaux pour qu’ils soient insuffisants en fonction du tableau précédent, le pool entier sera inactif.</span><span class="sxs-lookup"><span data-stu-id="24bec-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="24bec-157">Pour plus d’informations, voir <A href="https://go.microsoft.com/fwlink/?linkid=393672">témoin de mise en miroir de bases de données</A>.</span><span class="sxs-lookup"><span data-stu-id="24bec-157">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="24bec-158">Perte de quorum au niveau du pool</span><span class="sxs-lookup"><span data-stu-id="24bec-158">Pool-level quorum loss</span></span>

<span data-ttu-id="24bec-159">Pour qu’un pool frontal fonctionne du tout, il ne peut pas faire l’objets d’une perte de quorum au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="24bec-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="24bec-160">Si le nombre de serveurs en cours d’exécution tombe en dessous du niveau fonctionnel, comme indiqué dans le tableau suivant, les autres serveurs du pool arrêtent tous les services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24bec-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="24bec-161">Notez que les chiffres du tableau suivant partent du principe que les serveurs principaux du pool sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="24bec-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24bec-162">Nombre total de serveurs frontaux dans le pool</span><span class="sxs-lookup"><span data-stu-id="24bec-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="24bec-163">Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel</span><span class="sxs-lookup"><span data-stu-id="24bec-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24bec-164">n°2</span><span class="sxs-lookup"><span data-stu-id="24bec-164">2</span></span></p></td>
<td><p><span data-ttu-id="24bec-165">0,1</span><span class="sxs-lookup"><span data-stu-id="24bec-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-166">3-4</span><span class="sxs-lookup"><span data-stu-id="24bec-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="24bec-167">Any 2</span><span class="sxs-lookup"><span data-stu-id="24bec-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-168">5-6</span><span class="sxs-lookup"><span data-stu-id="24bec-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="24bec-169">Any 3</span><span class="sxs-lookup"><span data-stu-id="24bec-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-170">7 </span><span class="sxs-lookup"><span data-stu-id="24bec-170">7</span></span></p></td>
<td><p><span data-ttu-id="24bec-171">N’importe quel 4</span><span class="sxs-lookup"><span data-stu-id="24bec-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bec-172">8-9</span><span class="sxs-lookup"><span data-stu-id="24bec-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="24bec-173">Un 4 des 7 premiers serveurs</span><span class="sxs-lookup"><span data-stu-id="24bec-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bec-174">10-12</span><span class="sxs-lookup"><span data-stu-id="24bec-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="24bec-175">Un 5 des premiers serveurs</span><span class="sxs-lookup"><span data-stu-id="24bec-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24bec-176">Dans le tableau précédent, les « premiers serveurs » sont les serveurs qui ont été mis en avant pour la première fois, de façon chronologique, au moment du premier démarrage du pool.</span><span class="sxs-lookup"><span data-stu-id="24bec-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="24bec-177">Pour déterminer ces serveurs, vous pouvez utiliser la cmdlet **Get-CsComputer** avec l’option **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="24bec-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="24bec-178">Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux en haut de la liste sont les premiers serveurs.</span><span class="sxs-lookup"><span data-stu-id="24bec-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="24bec-179">Pools frontaux avec deux serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="24bec-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="24bec-180">Nous vous déconseillons de déployer un pool frontal qui ne contient que deux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="24bec-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="24bec-181">Si vous devez déployer un tel pool, suivez les instructions ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="24bec-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="24bec-182">Si l’un des deux serveurs frontaux tombe en panne, vous devez essayer de le remettre dès que possible.</span><span class="sxs-lookup"><span data-stu-id="24bec-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="24bec-183">De même, si vous devez mettre à niveau l’un des deux serveurs, remettez-le en ligne dès que la mise à niveau est terminée.</span><span class="sxs-lookup"><span data-stu-id="24bec-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="24bec-184">Si, pour une raison quelconque, vous devez mettre les deux serveurs en même temps, procédez comme suit lorsque le temps d’arrêt du pool est terminé :</span><span class="sxs-lookup"><span data-stu-id="24bec-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="24bec-185">La meilleure pratique consiste à redémarrer les deux serveurs frontaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="24bec-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="24bec-186">Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leur ordre d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="24bec-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="24bec-187">Si vous ne pouvez pas les rétablir dans cet ordre, utilisez l’applet de commande suivante avant de rétablir le pool :.</span><span class="sxs-lookup"><span data-stu-id="24bec-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="24bec-188">Étapes supplémentaires permettant de s’assurer que les pools sont fonctionnels</span><span class="sxs-lookup"><span data-stu-id="24bec-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="24bec-189">Vous devez surveiller deux autres facteurs afin de vous assurer que vos pools frontaux demeurent fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="24bec-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="24bec-190">Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="24bec-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="24bec-191">Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de récupération d’urgence, après avoir établi cette relation, vous devez vous assurer que ce pool dispose de trois serveurs frontaux exécutés simultanément à un moment donné pour synchroniser correctement les données avec le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24bec-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="24bec-192">Pour plus d’informations sur les paires de pools et les fonctionnalités de récupération d’urgence, voir [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="24bec-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="24bec-193">Amélioration de la fiabilité des mises à niveau de pool</span><span class="sxs-lookup"><span data-stu-id="24bec-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="24bec-194">Lorsque vous devez mettre à niveau ou appliquer des correctifs aux serveurs dans un pool frontal, suivez le flux de travail indiqué dans [Upgrade ou Update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), ainsi que les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="24bec-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="24bec-195">Lorsque vous passez d’un domaine de mise à niveau à un autre pour les mises à niveau (après le flux de travail à la [mise à niveau ou la mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), vous allez utiliser la cmdlet **Get-CsPoolUpgradeReadinessState** et vérifier que l’État est prêt.</span><span class="sxs-lookup"><span data-stu-id="24bec-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="24bec-196">L’ajout d’une attente de 20 minutes entre chaque domaine de mise à niveau après avoir atteint « prêt » rendra les mises à niveau plus fiables.</span><span class="sxs-lookup"><span data-stu-id="24bec-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="24bec-197">S’il **n’est pas prêt** pendant cette période de 20 minutes, redémarrez le minuteur de 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="24bec-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="24bec-198">Vous pouvez également exécuter la cmdlet **Get-applet cspoolfabricstate ne** avant et après le début de l’intervalle de 20 minutes et vous assurer qu’aucune modification n’est apportée aux principaux et aux secondaires des groupes de routage.</span><span class="sxs-lookup"><span data-stu-id="24bec-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="24bec-199">Ne passez pas au domaine de mise à niveau suivant si l’un des serveurs du dernier domaine de mise à niveau corrigé est bloqué ou ne redémarre pas.</span><span class="sxs-lookup"><span data-stu-id="24bec-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="24bec-200">Cela s’applique également si l’un des serveurs au sein d’une mise à niveau ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="24bec-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="24bec-201">Exécutez **Get-applet cspoolfabricstate ne** pour vous assurer que tous les groupes de routage ont un principal et au moins un secondaire ; Cela permet de vérifier si tous les utilisateurs disposent d’un service.</span><span class="sxs-lookup"><span data-stu-id="24bec-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="24bec-202">Si certains utilisateurs ont un service et d’autres non, exécutez **Get-applet cspoolfabricstate ne** avec l’option – verbose pour vérifier les groupes de routage qui ont des réplicas manquants.</span><span class="sxs-lookup"><span data-stu-id="24bec-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="24bec-203">Ne redémarrez pas l’intégralité du pool en tant que première étape de dépannage.</span><span class="sxs-lookup"><span data-stu-id="24bec-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="24bec-204">Pour plus d’informations sur cette applet de commande, consultez la rubrique [Get-applet cspoolfabricstate ne](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="24bec-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="24bec-205">Assurez-vous que toutes les instances des fenêtres de l’observateur d’événements ou de l’analyseur de performances sont fermées pour les installations/désinstallations de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="24bec-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="24bec-206">Modification de la configuration d’un pool frontal</span><span class="sxs-lookup"><span data-stu-id="24bec-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="24bec-207">Chaque fois que vous ajoutez des serveurs frontaux à un pool, ou que vous les supprimez du pool, puis que vous publiez la nouvelle topologie, suivez ces instructions :</span><span class="sxs-lookup"><span data-stu-id="24bec-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="24bec-208">Une fois la nouvelle topologie publiée, vous devez redémarrer chaque serveur frontal dans le pool.</span><span class="sxs-lookup"><span data-stu-id="24bec-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="24bec-209">Redémarrez-les une à la fois.</span><span class="sxs-lookup"><span data-stu-id="24bec-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="24bec-210">Si le pool entier est inactif lors de la modification de la configuration, exécutez l’applet de commande suivante après la publication de la nouvelle topologie :</span><span class="sxs-lookup"><span data-stu-id="24bec-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="24bec-211">Si un serveur frontal tombe en panne et qu’il n’est probablement pas remplacé pendant quelques jours ou plus, supprimez le serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="24bec-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="24bec-212">Ajoutez le nouveau serveur frontal à la topologie lorsqu’il est de nouveau disponible.</span><span class="sxs-lookup"><span data-stu-id="24bec-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

