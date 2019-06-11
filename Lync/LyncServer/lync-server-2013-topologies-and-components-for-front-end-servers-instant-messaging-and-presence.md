---
title: 'Lync Server 2013 : Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="fec0a-102">Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec0a-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec0a-103">_**Dernière modification de la rubrique:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="fec0a-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="fec0a-104">Les seuls composants requis pour la messagerie instantanée et la présence sont :</span><span class="sxs-lookup"><span data-stu-id="fec0a-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="fec0a-105">Serveurs frontaux de votre organisation ou serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fec0a-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="fec0a-106">Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="fec0a-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="fec0a-107">Un programme d’équilibrage de la charge, si vous avez un pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fec0a-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="fec0a-108">Pour plus d’informations, reportez-vous [à configuration requise pour l’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fec0a-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="fec0a-109">Planification du déploiement de pools front-end</span><span class="sxs-lookup"><span data-stu-id="fec0a-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="fec0a-110">Dans Lync Server 2013, l’architecture du pool frontal a changé, et ces modifications affectent la manière dont vous devez planifier et mettre à jour vos pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="fec0a-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="fec0a-111">Nous vous recommandons d’inclure au moins trois serveurs front-end dans votre version Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fec0a-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="fec0a-112">Dans Lync Server, l’architecture des pools front-end utilise un modèle de systèmes distribués, dont les données sont conservées sur trois serveurs front-end de la liste.</span><span class="sxs-lookup"><span data-stu-id="fec0a-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="fec0a-113">Pour plus d’informations sur cette nouvelle architecture, voir [modifications de topologie dans Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="fec0a-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="fec0a-114">Si vous ne voulez pas déployer trois serveurs frontaux Enterprise Edition et que vous souhaitez effectuer une reprise d’urgence, nous vous conseillons d’utiliser Lync Server Standard Edition et de créer deux pools avec une relation de sauvegarde couplée.</span><span class="sxs-lookup"><span data-stu-id="fec0a-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="fec0a-115">Cela fournit une solution de reprise après sinistre avec deux serveurs uniquement.</span><span class="sxs-lookup"><span data-stu-id="fec0a-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="fec0a-116">Pour plus d’informations sur les topologies et les fonctionnalités de haute disponibilité et de récupération d’urgence, reportez-vous à la section [planification d’une haute disponibilité et d’une reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fec0a-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="fec0a-117">Planification de la gestion des regroupements front-end</span><span class="sxs-lookup"><span data-stu-id="fec0a-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="fec0a-118">Pour les listes frontales, suivez les instructions de cette section.</span><span class="sxs-lookup"><span data-stu-id="fec0a-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="fec0a-119">Vérification du bon fonctionnement des pools</span><span class="sxs-lookup"><span data-stu-id="fec0a-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="fec0a-120">Avec le nouveau modèle distribué pour les pools front-end, certains numéros des serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne.</span><span class="sxs-lookup"><span data-stu-id="fec0a-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="fec0a-121">Il existe deux modes de perte pour une réserve</span><span class="sxs-lookup"><span data-stu-id="fec0a-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="fec0a-122">Perte de quorum au niveau du groupe de routage, provoquée par lʼinsuffisance des serveurs réplica pour un groupe de routage particulier.</span><span class="sxs-lookup"><span data-stu-id="fec0a-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="fec0a-123">Un groupe de routage est une agrégation d’un ensemble d’utilisateurs hébergés dans le pool.</span><span class="sxs-lookup"><span data-stu-id="fec0a-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="fec0a-124">Chaque groupe de routage comporte trois réplicas du pool: un seul et deux secondaires.</span><span class="sxs-lookup"><span data-stu-id="fec0a-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="fec0a-125">Perte de quorum au niveau du pool, provoquée par une insuffisance du nombre de serveurs d’amorçage en cours d’exécution dans le pool.</span><span class="sxs-lookup"><span data-stu-id="fec0a-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="fec0a-126">Perte de quorum au niveau du groupe de routage</span><span class="sxs-lookup"><span data-stu-id="fec0a-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="fec0a-p107">Lors du premier démarrage d’un nouveau nouveau pool frontal, il est primordial que 85 % des serveurs soient opérationnels, comme indiqué dans le tableau ci-après. Si un pourcentage inférieur de serveurs est en cours d’exécution, les services risquent de rester bloqués dans leur état de démarrage et le pool risque de ne pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="fec0a-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec0a-129">Nombre total de serveurs dans le pool</span><span class="sxs-lookup"><span data-stu-id="fec0a-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="fec0a-130">Nombre de serveurs devant être en cours d’exécution pour que le pool démarre la première fois</span><span class="sxs-lookup"><span data-stu-id="fec0a-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-131">2</span><span class="sxs-lookup"><span data-stu-id="fec0a-131">2</span></span></p></td>
<td><p><span data-ttu-id="fec0a-132">1</span><span class="sxs-lookup"><span data-stu-id="fec0a-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-133">3</span><span class="sxs-lookup"><span data-stu-id="fec0a-133">3</span></span></p></td>
<td><p><span data-ttu-id="fec0a-134">3</span><span class="sxs-lookup"><span data-stu-id="fec0a-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-135">4</span><span class="sxs-lookup"><span data-stu-id="fec0a-135">4</span></span></p></td>
<td><p><span data-ttu-id="fec0a-136">3</span><span class="sxs-lookup"><span data-stu-id="fec0a-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-137">5</span><span class="sxs-lookup"><span data-stu-id="fec0a-137">5</span></span></p></td>
<td><p><span data-ttu-id="fec0a-138">4</span><span class="sxs-lookup"><span data-stu-id="fec0a-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-139">6</span><span class="sxs-lookup"><span data-stu-id="fec0a-139">6</span></span></p></td>
<td><p><span data-ttu-id="fec0a-140">5</span><span class="sxs-lookup"><span data-stu-id="fec0a-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-141">7</span><span class="sxs-lookup"><span data-stu-id="fec0a-141">7</span></span></p></td>
<td><p><span data-ttu-id="fec0a-142">5</span><span class="sxs-lookup"><span data-stu-id="fec0a-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-143">version8</span><span class="sxs-lookup"><span data-stu-id="fec0a-143">8</span></span></p></td>
<td><p><span data-ttu-id="fec0a-144">6</span><span class="sxs-lookup"><span data-stu-id="fec0a-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-145">09</span><span class="sxs-lookup"><span data-stu-id="fec0a-145">9</span></span></p></td>
<td><p><span data-ttu-id="fec0a-146">7</span><span class="sxs-lookup"><span data-stu-id="fec0a-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-147">0,10</span><span class="sxs-lookup"><span data-stu-id="fec0a-147">10</span></span></p></td>
<td><p><span data-ttu-id="fec0a-148">version8</span><span class="sxs-lookup"><span data-stu-id="fec0a-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-149">27,9</span><span class="sxs-lookup"><span data-stu-id="fec0a-149">11</span></span></p></td>
<td><p><span data-ttu-id="fec0a-150">09</span><span class="sxs-lookup"><span data-stu-id="fec0a-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-151">midi</span><span class="sxs-lookup"><span data-stu-id="fec0a-151">12</span></span></p></td>
<td><p><span data-ttu-id="fec0a-152">0,10</span><span class="sxs-lookup"><span data-stu-id="fec0a-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fec0a-153">Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent).</span><span class="sxs-lookup"><span data-stu-id="fec0a-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="fec0a-154">S’il n’est pas possible de démarrer ce nombre de serveurs (mais que suffisamment de serveurs peuvent être démarrés pour éviter une perte de quorum au niveau du pool), vous pouvez utiliser l’applet de commande **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** pour permettre au pool de récupérer de cette perte de quorum au niveau du groupe de routage et d’avancer.</span><span class="sxs-lookup"><span data-stu-id="fec0a-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="fec0a-155">Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="fec0a-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec0a-156">Dans la mesure où Lync Server utilise la base de données SQL principale comme témoin, si vous fermez la base de données principale et que vous basculez vers la copie miroir et que vous arrêtez les serveurs frontaux suffisants pour qu’ils soient insuffisants en fonction de la table précédente, le pool entier est déplacée vers le bas.</span><span class="sxs-lookup"><span data-stu-id="fec0a-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="fec0a-157">Pour plus d’informations, voir <A href="http://go.microsoft.com/fwlink/?linkid=393672">témoin de mise en miroir de base de données</A>.</span><span class="sxs-lookup"><span data-stu-id="fec0a-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="fec0a-158">Perte de quorum au niveau du pool</span><span class="sxs-lookup"><span data-stu-id="fec0a-158">Pool-level quorum loss</span></span>

<span data-ttu-id="fec0a-159">Pour qu’un pool frontal puisse fonctionner, il ne peut pas être dans la perte de quorum au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="fec0a-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="fec0a-160">Si le nombre de serveurs en cours de passe est inférieur au niveau fonctionnel, comme indiqué dans le tableau suivant, les serveurs restants du pool arrêtent tous les services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fec0a-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="fec0a-161">Notez que les nombres figurant dans le tableau ci-dessous partent du principe que les serveurs dorsaux du pool s’exécutent.</span><span class="sxs-lookup"><span data-stu-id="fec0a-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec0a-162">Nombre total de serveurs frontaux de la liste</span><span class="sxs-lookup"><span data-stu-id="fec0a-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="fec0a-163">Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</span><span class="sxs-lookup"><span data-stu-id="fec0a-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-164">2</span><span class="sxs-lookup"><span data-stu-id="fec0a-164">2</span></span></p></td>
<td><p><span data-ttu-id="fec0a-165">1</span><span class="sxs-lookup"><span data-stu-id="fec0a-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-166">3-4</span><span class="sxs-lookup"><span data-stu-id="fec0a-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="fec0a-167">2 (n’importe lesquels)</span><span class="sxs-lookup"><span data-stu-id="fec0a-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-168">5-6</span><span class="sxs-lookup"><span data-stu-id="fec0a-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="fec0a-169">3 (n’importe lesquels)</span><span class="sxs-lookup"><span data-stu-id="fec0a-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-170">7</span><span class="sxs-lookup"><span data-stu-id="fec0a-170">7</span></span></p></td>
<td><p><span data-ttu-id="fec0a-171">4 (n’importe lesquels)</span><span class="sxs-lookup"><span data-stu-id="fec0a-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec0a-172">8-9</span><span class="sxs-lookup"><span data-stu-id="fec0a-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="fec0a-173">4 (n’importe lesquels parmi les 7 premiers serveurs)</span><span class="sxs-lookup"><span data-stu-id="fec0a-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec0a-174">10-12</span><span class="sxs-lookup"><span data-stu-id="fec0a-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="fec0a-175">5 (n’importe lesquels parmi les 9 premiers serveurs)</span><span class="sxs-lookup"><span data-stu-id="fec0a-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fec0a-176">Dans le tableau ci-dessus, le «premier serveur» est le serveur qui s’est affiché en premier, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="fec0a-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="fec0a-177">Pour déterminer ces serveurs, vous pouvez utiliser l’applet de commande **Get-CsComputer** avec l’option **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="fec0a-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="fec0a-178">Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux situés en haut de la liste sont les premiers serveurs.</span><span class="sxs-lookup"><span data-stu-id="fec0a-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="fec0a-179">Pools front-end avec deux serveurs front-end</span><span class="sxs-lookup"><span data-stu-id="fec0a-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="fec0a-180">Nous déconseillons le déploiement d’un pool frontal qui ne contient que deux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="fec0a-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="fec0a-181">Si vous avez besoin de déployer une telle réserve, suivez les instructions ci-après:</span><span class="sxs-lookup"><span data-stu-id="fec0a-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="fec0a-182">Si l’un des deux serveurs frontaux est en panne, vous devez essayer de remettre le serveur en panne dès que vous le pouvez.</span><span class="sxs-lookup"><span data-stu-id="fec0a-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="fec0a-183">De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fec0a-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="fec0a-184">Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :</span><span class="sxs-lookup"><span data-stu-id="fec0a-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="fec0a-185">Il est recommandé de redémarrer à la fois les serveurs front-end en même temps.</span><span class="sxs-lookup"><span data-stu-id="fec0a-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="fec0a-186">Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.</span><span class="sxs-lookup"><span data-stu-id="fec0a-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="fec0a-187">Si vous ne pouvez pas les remettre dans cet ordre, utilisez l’applet de commande suivante avant de remettre le pool à nouveau:.</span><span class="sxs-lookup"><span data-stu-id="fec0a-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="fec0a-188">Étapes supplémentaires pour garantir le fonctionnement des pools</span><span class="sxs-lookup"><span data-stu-id="fec0a-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="fec0a-189">Vous devez prêter attention à deux autres facteurs pour vous assurer que vos pools frontaux restent opérationnels.</span><span class="sxs-lookup"><span data-stu-id="fec0a-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="fec0a-190">Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="fec0a-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="fec0a-191">Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de reprise après sinistre, après avoir établi la relation, vous devez vous assurer que ce pool comporte trois serveurs frontaux s’exécutant simultanément pour une synchronisation correcte. données avec le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="fec0a-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="fec0a-192">Pour plus d’informations sur les fonctionnalités de jumelage de pool et de récupération d’urgence, reportez-vous à la rubrique [planification d’une haute disponibilité et de récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fec0a-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="fec0a-193">Amélioration de la fiabilité des mises à niveau de pool</span><span class="sxs-lookup"><span data-stu-id="fec0a-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="fec0a-194">Lorsque vous avez besoin de mettre à niveau ou de mettre à jour les serveurs dans un pool frontal, suivez le flux de travail présenté dans [mettre à niveau ou mettre à jour les serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)et les instructions suivantes:</span><span class="sxs-lookup"><span data-stu-id="fec0a-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="fec0a-195">Lorsque vous passez d’un domaine de mise à niveau à un autre pour les mises à niveau (suivi du flux de travail lors de la [mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), vous devez utiliser l’applet de commande **Get-CsPoolUpgradeReadinessState** et vérifier l’état Ready.</span><span class="sxs-lookup"><span data-stu-id="fec0a-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="fec0a-196">L’ajout d’une attente de 20 minutes entre chaque domaine de mise à niveau après avoir atteint la «prête» permettra d’améliorer la fiabilité des mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="fec0a-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="fec0a-197">Si ce n’est **pas** le cas, redémarrez le minuteur de 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="fec0a-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="fec0a-198">Par ailleurs, vous pouvez exécuter l’applet de passe **Get-CsPoolFabricState** avant et après le démarrage de l’intervalle de 20 minutes et vérifier qu’il n’y a aucune modification apportée aux principaux et aux secondaires des groupes de routage.</span><span class="sxs-lookup"><span data-stu-id="fec0a-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="fec0a-199">Ne passez pas au domaine de mise à niveau suivant si l’un des serveurs du dernier domaine de mise à niveau corrigé est bloqué ou n’est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="fec0a-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="fec0a-200">Cela s’applique également si l’un des serveurs au sein d’une mise à niveau ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="fec0a-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="fec0a-201">Exécutez **Get-CsPoolFabricState** pour vous assurer que tous les groupes de routage disposent d’une adresse principale et d’au moins un secondaire; Cela permet de vérifier si tous les utilisateurs ont un service.</span><span class="sxs-lookup"><span data-stu-id="fec0a-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="fec0a-202">Si certains utilisateurs ne disposent pas d’un service, exécutez **Get-CsPoolFabricState** avec l’option – verbose pour rechercher les groupes de routage pour lesquels il manque des réplicas.</span><span class="sxs-lookup"><span data-stu-id="fec0a-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="fec0a-203">Ne redémarrez pas le pool entier en tant que première étape de dépannage.</span><span class="sxs-lookup"><span data-stu-id="fec0a-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="fec0a-204">Pour plus d’informations sur cette cmdlet, voir [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="fec0a-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="fec0a-205">Assurez-vous que toutes les instances des fenêtres de l’observateur d’événements ou du moniteur de performance sont fermées pour les installations/désinstallations de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="fec0a-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="fec0a-206">Modification de la configuration d’un pool frontal</span><span class="sxs-lookup"><span data-stu-id="fec0a-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="fec0a-207">Dès lors que vous ajoutez des serveurs frontaux à un pool ou que vous les supprimez de la liste, puis que vous publiez la nouvelle topologie, vous devez suivre les instructions suivantes:</span><span class="sxs-lookup"><span data-stu-id="fec0a-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="fec0a-208">Après la publication de la nouvelle topologie, vous devez redémarrer chaque serveur frontal du pool.</span><span class="sxs-lookup"><span data-stu-id="fec0a-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="fec0a-209">Redémarrez-les un par autre.</span><span class="sxs-lookup"><span data-stu-id="fec0a-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="fec0a-210">Si le pool entier est arrêté lors de la modification de la configuration, exécutez l’applet de commande suivante une fois la nouvelle topologie publiée:</span><span class="sxs-lookup"><span data-stu-id="fec0a-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="fec0a-211">Si un serveur frontal tombe en panne et est susceptible d’être remplacé pendant quelques jours ou davantage, supprimez le serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="fec0a-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="fec0a-212">Ajoutez le nouveau serveur frontal à la topologie lorsque ce dernier est disponible.</span><span class="sxs-lookup"><span data-stu-id="fec0a-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

