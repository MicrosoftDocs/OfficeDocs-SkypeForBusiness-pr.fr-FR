---
title: Migration vers Skype entreprise Server 2019
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
description: Les rubriques de cette section vous guident tout au long du processus de migration vers Skype entreprise Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752616"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="35f36-103">Migration vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="35f36-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="35f36-104">Les rubriques de cette section vous guident tout au long du processus de migration vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="35f36-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="35f36-105">Cet article traite de la migration de Lync Server 2013 ou Skype entreprise Server 2015 vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="35f36-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35f36-106">Tout au long du contenu, nous utilisons le terme *hérité* pour faire référence à l’ancien Lync Server 2013 ou Skype entreprise Server 2015 que vous migrez vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="35f36-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35f36-107">Ce guide décrit les étapes généralement requises pour effectuer chaque phase de la migration.</span><span class="sxs-lookup"><span data-stu-id="35f36-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="35f36-108">Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles.</span><span class="sxs-lookup"><span data-stu-id="35f36-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="35f36-109">Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="35f36-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="35f36-110">Ce guide fournit également des exemples d’étapes de vérification.</span><span class="sxs-lookup"><span data-stu-id="35f36-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="35f36-111">Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration.</span><span class="sxs-lookup"><span data-stu-id="35f36-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="35f36-112">Adaptez-les à votre processus de migration propre.</span><span class="sxs-lookup"><span data-stu-id="35f36-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="35f36-113">Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="35f36-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="35f36-114">Il n’explique pas comment modifier votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="35f36-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="35f36-115">Il n’aborde pas l’implémentation des nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="35f36-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="35f36-116">Lorsqu’une procédure détaillée est documentée ailleurs, ce guide vous dirige vers la section article ou article.</span><span class="sxs-lookup"><span data-stu-id="35f36-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="35f36-117">Cet article définit les termes comme indiqué dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="35f36-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="35f36-118">**migration :** Migration de votre déploiement de production de Lync Server 2013 ou Skype entreprise Server 2015 vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="35f36-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="35f36-119">**coexistence :** Environnement temporaire qui existe lors de la migration, quand une fonctionnalité a été migrée vers Skype entreprise Server 2019 et que d’autres fonctionnalités demeurent sur une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="35f36-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="35f36-120">**interopérabilité :** Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.</span><span class="sxs-lookup"><span data-stu-id="35f36-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="35f36-121">**hérité :** Le système à partir duquel vous effectuez la migration, c’est-à-dire Lync Server 2013 ou Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="35f36-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="35f36-122">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="35f36-122">In this section</span></span>

- [<span data-ttu-id="35f36-123">Avant de commencer la migration</span><span class="sxs-lookup"><span data-stu-id="35f36-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="35f36-124">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="35f36-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="35f36-125">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="35f36-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="35f36-126">Étape 3 : Déployer un pool pilote</span><span class="sxs-lookup"><span data-stu-id="35f36-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="35f36-127">Phase 4 : déplacer les utilisateurs test vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="35f36-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="35f36-128">Étape 5 : Ajouter un serveur Edge au pool pilote</span><span class="sxs-lookup"><span data-stu-id="35f36-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="35f36-129">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="35f36-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="35f36-130">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="35f36-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="35f36-131">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="35f36-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

