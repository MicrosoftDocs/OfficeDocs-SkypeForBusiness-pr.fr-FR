---
title: 'Lync Server 2013 : haute disponibilité du serveur principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7313d11557344586910f6afeeb5422744207023
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="1f48f-102">Haute disponibilité des serveurs principaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f48f-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f48f-103">_**Dernière modification de la rubrique :** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="1f48f-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="1f48f-104">Pour garantir la haute disponibilité de vos serveurs principaux, vous pouvez utiliser la mise en miroir SQL synchrone ou le clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="1f48f-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="1f48f-105">L’utilisation de l’une de ces solutions facultatives, mais est recommandée pour maintenir la continuité de l’activité de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1f48f-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="1f48f-106">La mise en miroir SQL asynchrone n’est pas prise en charge pour la haute disponibilité des serveurs principaux dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f48f-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="1f48f-107">Dans le reste du document, sauf mention explicite, la mise en miroir SQL sous-entend une mise en miroir SQL synchrone.</span><span class="sxs-lookup"><span data-stu-id="1f48f-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="1f48f-108">Vous pouvez facilement configurer la mise en miroir SQL avec le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1f48f-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="1f48f-109">Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="1f48f-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="1f48f-110">Si vous utilisez la mise en miroir SQL ou le clustering SQL dans un pool qui est associé à un autre pool frontal pour la récupération d’urgence, vous devez utiliser la même solution de haute disponibilité principale dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="1f48f-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="1f48f-111">Vous ne devez pas associer un pool à l’aide de la mise en miroir SQL avec un pool à l’aide du clustering SQL.</span><span class="sxs-lookup"><span data-stu-id="1f48f-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="1f48f-112">Lorsque vous déployez la mise en miroir SQL, toutes les bases de données Lync Server du pool sont mises en miroir, notamment le magasin central de gestion, s’il se trouve dans ce pool, ainsi que la base de données de l’application Response Group et la base de données de l’application de parcage d’appel, si ces applications sont en cours d’exécution dans le pool.</span><span class="sxs-lookup"><span data-stu-id="1f48f-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="1f48f-p104">La mise en miroir SQL vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local.</span><span class="sxs-lookup"><span data-stu-id="1f48f-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="1f48f-p105">Vous pouvez déployer la mise en miroir SQL avec ou sans témoin. Ceci dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="1f48f-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="1f48f-p106">Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="1f48f-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="1f48f-122">Pour plus d’informations sur la prise en charge du clustering SQL, reportez-vous [à Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="1f48f-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="1f48f-123">Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="1f48f-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="1f48f-124">Temps de récupération pour le basculement automatique de serveur principal avec mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="1f48f-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="1f48f-125">Pour le basculement automatique automatique avec mise en miroir SQL, le objectif d’ingénierie pour l’objectif de temps de récupération (RTO) est de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="1f48f-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="1f48f-126">Par l’usage de la mise en miroir SQL synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="1f48f-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="1f48f-127">La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="1f48f-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="1f48f-128">Expérience utilisateur lors d’une défaillance du serveur principal avec la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="1f48f-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="1f48f-129">L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1f48f-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="1f48f-130">Si vous utilisez la mise en miroir SQL et qu’un témoin est configuré, et que le principal échoue, le basculement du serveur principal s’effectue automatiquement et rapidement.</span><span class="sxs-lookup"><span data-stu-id="1f48f-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="1f48f-131">Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.</span><span class="sxs-lookup"><span data-stu-id="1f48f-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="1f48f-132">Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement.</span><span class="sxs-lookup"><span data-stu-id="1f48f-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="1f48f-133">Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés.</span><span class="sxs-lookup"><span data-stu-id="1f48f-133">During that time, active users may be affected.</span></span> <span data-ttu-id="1f48f-134">Leurs sessions se poursuivent normalement pendant environ 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="1f48f-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="1f48f-135">Si le serveur principal n’est toujours pas restauré, ou si un administrateur n’a pas basculé vers la sauvegarde, les utilisateurs sont basculés en mode résistance, ce qui signifie qu’ils ne peuvent pas effectuer des tâches nécessitant une modification permanente sur Lync Server (par exemple, l’ajout d’un contact).</span><span class="sxs-lookup"><span data-stu-id="1f48f-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="1f48f-p111">Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résilience s’active pour les utilisateurs actifs après une certaine durée.</span><span class="sxs-lookup"><span data-stu-id="1f48f-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

