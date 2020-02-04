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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="9578a-102">Haute disponibilité du serveur principal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9578a-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9578a-103">_**Dernière modification de la rubrique :** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="9578a-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="9578a-104">Pour garantir la disponibilité de votre serveur principal, vous pouvez utiliser la mise en miroir SQL synchrone ou le regroupement SQL.</span><span class="sxs-lookup"><span data-stu-id="9578a-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="9578a-105">Vous pouvez utiliser l’une de ces solutions en option, mais nous vous recommandons de préserver la continuité d’activité de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9578a-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="9578a-106">La mise en miroir SQL asynchrone n’est pas prise en charge pour la haute disponibilité du serveur principal dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9578a-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="9578a-107">Dans le reste de ce document, la mise en miroir SQL désigne la mise en miroir SQL synchrone, sauf mention contraire explicite.</span><span class="sxs-lookup"><span data-stu-id="9578a-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="9578a-108">Vous pouvez facilement configurer la mise en miroir SQL avec le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9578a-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="9578a-109">Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="9578a-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="9578a-110">Si vous utilisez la mise en miroir SQL ou le regroupement SQL dans un pool qui est associé à un autre pool frontal pour la récupération après sinistre, vous devez utiliser la même solution de haute disponibilité back-end dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="9578a-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="9578a-111">Vous ne devez pas associer un pool à l’aide de la mise en miroir SQL avec un pool utilisant le regroupement SQL.</span><span class="sxs-lookup"><span data-stu-id="9578a-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="9578a-112">Lorsque vous déployez la mise en miroir SQL, toutes les bases de données du serveur Lync dans le pool sont mises en miroir, y compris la Banque centrale de gestion, si elles se trouvent dans ce pool, ainsi que la base de données d’application du groupe de réponse et la base de données d’application du parc d’appels, si ces applications s’exécutent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9578a-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="9578a-113">Avec la mise en miroir SQL, vous n’avez pas besoin d’utiliser le stockage partagé pour les serveurs.</span><span class="sxs-lookup"><span data-stu-id="9578a-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="9578a-114">Chaque serveur garde sa copie des bases de données en local.</span><span class="sxs-lookup"><span data-stu-id="9578a-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="9578a-115">Vous pouvez choisir de déployer la mise en miroir SQL avec ou sans témoin.</span><span class="sxs-lookup"><span data-stu-id="9578a-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="9578a-116">Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="9578a-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="9578a-117">Dans le cas contraire, un administrateur doit appeler le basculement manuellement.</span><span class="sxs-lookup"><span data-stu-id="9578a-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="9578a-118">Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="9578a-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="9578a-p106">Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="9578a-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="9578a-122">Pour plus d’informations sur la prise en charge des clusters SQL, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="9578a-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="9578a-123">Pour plus d’informations sur le déploiement de clusters SQL, voir [configurer le regroupement SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="9578a-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="9578a-124">Temps de récupération pour le basculement automatique du serveur principal avec la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="9578a-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="9578a-125">Pour le basculement de bout en bout automatique avec la mise en miroir SQL, l’objectif d’ingénierie pour le temps de récupération (RTO) est de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="9578a-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="9578a-126">En raison de la mise en miroir SQL synchrone, nous ne prévoyons pas la perte de données en cas d’échec du serveur principal, sauf dans de rares cas où les données sont déplacées sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="9578a-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="9578a-127">La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="9578a-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="9578a-128">Utilisation de l’interface utilisateur lors de l’échec du serveur principal avec la mise en miroir SQL</span><span class="sxs-lookup"><span data-stu-id="9578a-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="9578a-129">L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="9578a-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="9578a-130">Si vous utilisez la mise en miroir SQL et que vous avez configuré un témoin, le basculement du serveur principal se produit automatiquement et rapidement.</span><span class="sxs-lookup"><span data-stu-id="9578a-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="9578a-131">Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.</span><span class="sxs-lookup"><span data-stu-id="9578a-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="9578a-132">Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement.</span><span class="sxs-lookup"><span data-stu-id="9578a-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="9578a-133">Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés.</span><span class="sxs-lookup"><span data-stu-id="9578a-133">During that time, active users may be affected.</span></span> <span data-ttu-id="9578a-134">Leurs sessions se poursuivent normalement pendant environ 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="9578a-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="9578a-135">Si le serveur principal n’est toujours pas restauré ou s’il n’a pas pu basculer vers la sauvegarde, les utilisateurs sont basculés vers le mode de résilience, ce qui signifie qu’ils ne sont pas en mesure d’effectuer des tâches nécessitant un changement permanent sur le serveur Lync (par exemple, ajouter un contact).</span><span class="sxs-lookup"><span data-stu-id="9578a-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="9578a-p111">Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.</span><span class="sxs-lookup"><span data-stu-id="9578a-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

