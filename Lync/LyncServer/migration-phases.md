---
title: Phases de migration
description: Phases de migration.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547050"
---
# <a name="migration-phases"></a><span data-ttu-id="a9b74-103">Phases de migration</span><span class="sxs-lookup"><span data-stu-id="a9b74-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9b74-104">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a9b74-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a9b74-105">Dans Lync Server 2013, vous définissez des sites sur votre réseau qui contiennent des composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9b74-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="a9b74-106">Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse.</span><span class="sxs-lookup"><span data-stu-id="a9b74-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="a9b74-107">Un *pool frontal* est un ensemble de serveurs frontaux configurés de manière identique et qui fonctionnent ensemble pour fournir des services à un groupe commun d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9b74-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="a9b74-108">Un pool fournit l’évolutivité et la fonction de basculement aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9b74-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="a9b74-109">Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques.</span><span class="sxs-lookup"><span data-stu-id="a9b74-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="a9b74-110">Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="a9b74-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="a9b74-111">Cela vous permet de disposer des fonctionnalités Lync Server 2013 pour un coût moindre, mais ne fournit pas de véritable solution de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a9b74-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="a9b74-112">Les phases suivantes décrivent le processus de migration d’un pool de Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9b74-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="a9b74-113">Dans le cas de sites multiples contenant des pools multiples, chaque pool doit suivre cette approche basée sur des phases.</span><span class="sxs-lookup"><span data-stu-id="a9b74-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="a9b74-114">Phase 1 : planification de la migration à partir de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9b74-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="a9b74-115">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="a9b74-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="a9b74-116">Phase 3 : déployer le pool pilote Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9b74-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="a9b74-117">Phase 4 : déplacer les utilisateurs test vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="a9b74-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="a9b74-118">Phase 5 : ajouter le serveur Edge Lync Server 2013 au pool pilote</span><span class="sxs-lookup"><span data-stu-id="a9b74-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="a9b74-119">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="a9b74-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="a9b74-120">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="a9b74-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="a9b74-121">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="a9b74-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

