---
title: Gestion de la reprise après sinistre du serveur Lync, haute disponibilité et service de sauvegarde
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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="62dc0-102">Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62dc0-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="62dc0-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="62dc0-104">Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour la gestion du service de sauvegarde qui synchronise les données dans les pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="62dc0-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="62dc0-105">Les procédures de reprise après sinistre, à la fois de basculement et de restauration automatique, sont manuelles.</span><span class="sxs-lookup"><span data-stu-id="62dc0-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="62dc0-106">En cas de sinistre, l’administrateur doit appeler manuellement les procédures de basculement.</span><span class="sxs-lookup"><span data-stu-id="62dc0-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="62dc0-107">Il en va de même pour la restauration après la réparation du pool.</span><span class="sxs-lookup"><span data-stu-id="62dc0-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="62dc0-108">Les procédures de reprise après sinistre dans le reste de cette section sont supposées comme suit :</span><span class="sxs-lookup"><span data-stu-id="62dc0-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="62dc0-109">Vous disposez d’un déploiement avec des plages frontales couplées disponibles dans les différents sites, comme décrit dans la rubrique [planification de la haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="62dc0-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="62dc0-110">Le service de sauvegarde est en cours d’exécution sur ces pools couplés pour qu’ils soient synchronisés.</span><span class="sxs-lookup"><span data-stu-id="62dc0-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="62dc0-111">Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et en cours d’exécution sur les deux pools couplés, avec l’un de ces pools hébergeant la forme de base active et l’autre réserve hébergeant la réserve.</span><span class="sxs-lookup"><span data-stu-id="62dc0-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="62dc0-112">Dans les procédures suivantes, le paramètre <EM>PoolFQDN</EM> fait référence au nom de domaine complet (FQDN) du pool affecté par un sinistre, et non à partir du pool sur lequel les utilisateurs concernés sont redirigés.</span><span class="sxs-lookup"><span data-stu-id="62dc0-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="62dc0-113">Pour le même ensemble d’utilisateurs concernés, il fait référence au même pool dans les applets de service de basculement et de restauration automatique (autrement dit, le pool qui a d’abord hébergé les utilisateurs avant le basculement).</span><span class="sxs-lookup"><span data-stu-id="62dc0-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="62dc0-114">Par exemple, supposons que l’ensemble des utilisateurs hébergés sur un pool P1 aient pu basculer vers le pool de sauvegardes P2.</span><span class="sxs-lookup"><span data-stu-id="62dc0-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="62dc0-115">Si l’administrateur veut déplacer tous les utilisateurs actuellement desservis par P2 pour être desservi par P1, l’administrateur doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="62dc0-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="62dc0-116">Basculez vers la page d’accueil de tous les utilisateurs à l’origine de l’appel P1 sur P1 à l’aide de l’applet de la cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="62dc0-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="62dc0-117">Dans le cas présent, le <EM>PoolFQDN</EM> est P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="62dc0-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="62dc0-118">Faire basculer tous les utilisateurs de la page d’origine de la page de base sur l’applet de contrôle</span><span class="sxs-lookup"><span data-stu-id="62dc0-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="62dc0-119">Dans le cas présent, le <EM>PoolFQDN</EM> est P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="62dc0-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="62dc0-120">Si l’administrateur souhaite plus tard régulariser les utilisateurs de P2, le <EM>PoolFQDN</EM> est P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="62dc0-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="62dc0-121">Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 de conservation de l’intégrité du pool.</span><span class="sxs-lookup"><span data-stu-id="62dc0-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="62dc0-122">Si vous essayez l’étape 2 avant l’étape 1, l’applet de la cmdlet Step 2 ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="62dc0-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62dc0-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="62dc0-123">In This Section</span></span>

  - [<span data-ttu-id="62dc0-124">Configuration et surveillance du service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="62dc0-125">Basculement vers un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="62dc0-126">Basculement vers un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="62dc0-127">Basculement vers une base de données en miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="62dc0-128">Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="62dc0-129">Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="62dc0-130">Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="62dc0-131">Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="62dc0-132">Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62dc0-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62dc0-133">See Also</span></span>


[<span data-ttu-id="62dc0-134">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62dc0-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

