---
title: Phases de migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants de Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752626"
---
# <a name="migration-phases"></a><span data-ttu-id="fd031-104">Phases de migration</span><span class="sxs-lookup"><span data-stu-id="fd031-104">Migration phases</span></span>

<span data-ttu-id="fd031-105">Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd031-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="fd031-106">Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse.</span><span class="sxs-lookup"><span data-stu-id="fd031-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="fd031-107">Un pool frontal est un ensemble de serveurs frontaux configurés de manière identique et qui fonctionnent ensemble pour fournir des services à un groupe commun d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fd031-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="fd031-108">Un pool fournit l’évolutivité et la fonction de basculement aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fd031-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="fd031-109">Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques.</span><span class="sxs-lookup"><span data-stu-id="fd031-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="fd031-110">Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="fd031-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="fd031-111">Cela vous permet de disposer des fonctionnalités de Skype entreprise Server 2019 pour un coût moindre, mais ne fournit pas une véritable solution de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="fd031-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="fd031-112">Les phases suivantes décrivent le processus de migration d’un pool vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd031-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="fd031-113">Dans le cas de sites multiples contenant des pools multiples, chaque pool doit suivre cette approche basée sur des phases.</span><span class="sxs-lookup"><span data-stu-id="fd031-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="fd031-114">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="fd031-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="fd031-115">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="fd031-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="fd031-116">Phase 3 : déploiement du pool pilote Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="fd031-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="fd031-117">Phase 4 : déplacer les utilisateurs test vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="fd031-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="fd031-118">Phase 5 : ajouter le serveur Edge de Skype entreprise Server 2019 au pool pilote</span><span class="sxs-lookup"><span data-stu-id="fd031-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="fd031-119">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="fd031-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="fd031-120">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="fd031-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="fd031-121">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="fd031-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

