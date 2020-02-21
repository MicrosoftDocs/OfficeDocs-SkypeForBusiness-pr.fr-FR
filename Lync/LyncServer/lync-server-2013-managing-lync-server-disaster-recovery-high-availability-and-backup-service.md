---
title: Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="60278-102">Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60278-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="60278-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="60278-104">Cette section contient des procédures destinées aux opérations de récupération d’urgence, ainsi que pour la maintenance du service de sauvegarde qui synchronise les données des pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="60278-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="60278-p101">Les procédures de récupération d’urgence, qu’il s’agisse du basculement ou de la restauration automatique, sont manuelles. En cas d’urgence, l’administrateur doit appeler manuellement les procédures de basculement. Il en est de même pour la restauration automatique, après la réparation du pool.</span><span class="sxs-lookup"><span data-stu-id="60278-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="60278-108">Les procédures de récupération d’urgence présentées dans le reste de la section supposent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="60278-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="60278-109">Vous disposez d’un déploiement avec des pools frontaux couplés, situés dans différents sites, comme décrit dans la rubrique [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="60278-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="60278-110">Le service de sauvegarde a été exécuté sur ces pools couplés pour maintenir leur synchronisation.</span><span class="sxs-lookup"><span data-stu-id="60278-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="60278-111">Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et s’exécute sur les deux pools couplés, avec l’un de ces pools hébergeant le serveur principal actif et l’autre pool hébergeant le secours.</span><span class="sxs-lookup"><span data-stu-id="60278-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="60278-p103">Dans les procédures suivantes, le paramètre <EM>PoolFQDN</EM> se réfère au nom de domaine complet (FQDN) du pool affecté par la situation d’urgence et non pas le pool depuis lequel les utilisateurs affectés sont redirigés. Dans le cas d’un ensemble d’utilisateurs identique, le paramètre se réfère au même pool, dans les cmdlets de basculement et de récupération automatique (c’est-à-dire, le pool ayant hébergé les utilisateurs avant le basculement).</span><span class="sxs-lookup"><span data-stu-id="60278-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="60278-p104">Par exemple, supposons que tous les utilisateurs hébergés sur un pool P1 ont été basculés sur le pool de sauvegarde, P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement traités par les services de P2 pour qu’ils soient traités par les services de P1, l’administrateur doit procéder comme ceci :</span><span class="sxs-lookup"><span data-stu-id="60278-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="60278-p105">Il doit restaurer automatiquement tous les utilisateurs hébergés à l’origine sur P1 de P2 à P1 en utilisant la cmdlet de restauration automatique. Dans ce cas, le <EM>PoolFQDN</EM> est le nom de domaine complet (FQDN) de P1.</span><span class="sxs-lookup"><span data-stu-id="60278-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="60278-p106">Il doit ensuite basculer tous les utilisateurs hébergés à l’origine sur P2 vers P1 en utilisant la cmdlet de basculement. Dans ce cas, le <EM>PoolFQDN</EM> est le nom de domaine complet (FQDN) de P2.</span><span class="sxs-lookup"><span data-stu-id="60278-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="60278-120">Si l’administrateur souhaite ultérieurement restaurer automatiquement les utilisateurs de P2 vers P2, le <EM>PoolFQDN</EM> est le nom de domaine complet FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="60278-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="60278-121">Remarquez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool.</span><span class="sxs-lookup"><span data-stu-id="60278-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="60278-122">Si vous essayez l’étape 2 avant l’étape 1, la cmdlet de l’étape 2 ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="60278-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60278-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="60278-123">In This Section</span></span>

  - [<span data-ttu-id="60278-124">Configuration et surveillance du service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="60278-125">Basculement d’un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="60278-126">Restauration d’un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="60278-127">Basculement vers une base de données mise en miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="60278-128">Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="60278-129">Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="60278-130">Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="60278-131">Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="60278-132">Restauration du contenu d’une conférence à l’aide du service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60278-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60278-133">See Also</span></span>


[<span data-ttu-id="60278-134">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60278-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

