---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype pour Business Server 2019, vous définissez les sites de votre réseau qui contiennent Skype pour les composants Business Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau rapide et à faible latence, par exemple un réseau local (LAN) unique ou deux réseaux connectés par un réseau optique Fibre à haute vitesse.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886528"
---
# <a name="migration-phases"></a><span data-ttu-id="4646c-104">Phases de migration</span><span class="sxs-lookup"><span data-stu-id="4646c-104">Migration phases</span></span>

<span data-ttu-id="4646c-105">Dans Skype pour Business Server 2019, vous définissez les sites de votre réseau qui contiennent Skype pour les composants Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4646c-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="4646c-106">Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau rapide et à faible latence, par exemple un réseau local (LAN) unique ou deux réseaux connectés par un réseau optique Fibre à haute vitesse.</span><span class="sxs-lookup"><span data-stu-id="4646c-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="4646c-107">Un pool frontal est un ensemble de serveurs frontaux qui sont configurés à l’identique et ensemble pour fournir des services à un groupe commun d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4646c-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="4646c-108">Un pool fournit l’évolutivité et la capacité de basculement à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4646c-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="4646c-109">Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques.</span><span class="sxs-lookup"><span data-stu-id="4646c-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="4646c-110">Un serveur Standard Edition server, conçu pour les petites organisations, également définit un pool et s’exécute sur un serveur unique.</span><span class="sxs-lookup"><span data-stu-id="4646c-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="4646c-111">Cela vous permet d’avoir Skype pour la fonctionnalité Business Server 2019 pour un coût inférieur, mais ne fournit pas une véritable solution de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="4646c-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="4646c-112">Les phases suivantes décrivent le processus de migration pool vers Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4646c-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="4646c-113">Plusieurs sites contenant plusieurs pools, chaque pool doit suivre cette approche progressive.</span><span class="sxs-lookup"><span data-stu-id="4646c-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="4646c-114">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="4646c-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="4646c-115">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="4646c-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="4646c-116">Phase 3 : Déploiement Skype pour le pool pilote Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4646c-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="4646c-117">Phase 4 : Déplacer les utilisateurs de test le pool pilote</span><span class="sxs-lookup"><span data-stu-id="4646c-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="4646c-118">Phase 5 : Ajoutez Skype pour Business Server 2019 Edge Server vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="4646c-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="4646c-119">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="4646c-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="4646c-120">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="4646c-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="4646c-121">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="4646c-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

