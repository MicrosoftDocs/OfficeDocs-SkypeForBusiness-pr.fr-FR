---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par le biais d’un réseau haut débit à faible latence, par exemple un réseau local unique (LAN) ou deux réseaux connectés par un réseau fibres optiques haut débit.
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813422"
---
# <a name="migration-phases"></a><span data-ttu-id="3fe6f-104">Phases de migration</span><span class="sxs-lookup"><span data-stu-id="3fe6f-104">Migration phases</span></span>

<span data-ttu-id="3fe6f-105">Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="3fe6f-106">Un site est un ensemble d’ordinateurs qui sont bien connectés par le biais d’un réseau haut débit à faible latence, par exemple un réseau local unique (LAN) ou deux réseaux connectés par un réseau fibres optiques haut débit.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="3fe6f-107">Un pool frontal est un ensemble de serveurs frontaux configurés de manière identique et collabore pour fournir des services à un groupe d’utilisateurs communs.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="3fe6f-108">Un pool fournit une capacité d’évolutivité et de basculement pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="3fe6f-109">Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="3fe6f-110">Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un serveur unique.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="3fe6f-111">Cela vous permet de disposer de la fonctionnalité Skype entreprise Server 2019 pour un coût inférieur, mais ne fournit pas de véritable solution de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="3fe6f-112">Les phases suivantes décrivent le processus de migration d’un pool vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="3fe6f-113">Pour les sites multiples contenant plusieurs pools, chaque pool individuel doit suivre cette approche par phases.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="3fe6f-114">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="3fe6f-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="3fe6f-115">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="3fe6f-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="3fe6f-116">Étape 3 : déploiement du pool de pilotes Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="3fe6f-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="3fe6f-117">Étape 4 : déplacer les utilisateurs de test vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="3fe6f-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="3fe6f-118">Étape 5 : ajouter le serveur Edge de Skype entreprise Server 2019 au pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="3fe6f-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="3fe6f-119">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="3fe6f-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="3fe6f-120">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="3fe6f-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="3fe6f-121">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="3fe6f-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

