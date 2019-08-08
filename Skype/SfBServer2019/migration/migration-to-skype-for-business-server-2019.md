---
title: Migration vers Skype entreprise Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les rubriques de cette section vous guident dans le processus de migration vers Skype entreprise Server 2019.
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237771"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="23cd9-103">Migration vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="23cd9-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="23cd9-104">Les rubriques de cette section vous guident dans le processus de migration vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23cd9-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="23cd9-105">Cet article décrit la migration de Lync Server 2013 ou de Skype entreprise Server 2015 vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23cd9-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23cd9-106">Dans l’ensemble du contenu, nous utilisons le terme *hérité* pour faire référence à l’ancien serveur Lync Server 2013 ou à Skype entreprise Server 2015 que vous migrez vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23cd9-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="23cd9-107">Ce guide décrit les étapes généralement requises pour effectuer chaque phase de migration.</span><span class="sxs-lookup"><span data-stu-id="23cd9-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="23cd9-108">Elle ne traite pas chaque topologie de déploiement hérité possible ou chaque scénario de migration possible.</span><span class="sxs-lookup"><span data-stu-id="23cd9-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="23cd9-109">Par conséquent, il est possible que vous n’ayez pas à effectuer toutes les étapes décrites ou que vous deviez effectuer des étapes supplémentaires, selon votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="23cd9-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="23cd9-110">Ce guide fournit également des exemples de procédure de vérification.</span><span class="sxs-lookup"><span data-stu-id="23cd9-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="23cd9-111">Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez savoir pour vous assurer que toutes les phases s’exécutent correctement lors de la migration.</span><span class="sxs-lookup"><span data-stu-id="23cd9-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="23cd9-112">Adaptez ces étapes de vérification à votre processus de migration spécifique.</span><span class="sxs-lookup"><span data-stu-id="23cd9-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="23cd9-113">Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="23cd9-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="23cd9-114">Il n’explique pas comment modifier votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="23cd9-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="23cd9-115">Ce guide ne traite pas de l’implémentation des nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="23cd9-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="23cd9-116">Lorsqu’une procédure détaillée est documentée à un autre emplacement, ce guide vous dirige vers l’article ou la section article.</span><span class="sxs-lookup"><span data-stu-id="23cd9-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="23cd9-117">Cet article définit les termes comme spécifié dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="23cd9-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="23cd9-118">**migration:** Migration de votre déploiement de production de Lync Server 2013 ou de Skype entreprise Server 2015 vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23cd9-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="23cd9-119">**coexistence:** Environnement temporaire existant lors de la migration lors de la migration de certaines fonctionnalités vers Skype entreprise Server 2019 et si d’autres fonctionnalités continuent de subsister dans une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="23cd9-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="23cd9-120">**interopérabilité:** La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.</span><span class="sxs-lookup"><span data-stu-id="23cd9-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="23cd9-121">**héritage:** Le système à partir duquel vous effectuez la migration, qui est Lync Server 2013 ou Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="23cd9-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="23cd9-122">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="23cd9-122">In this section</span></span>

- [<span data-ttu-id="23cd9-123">Avant de commencer la migration</span><span class="sxs-lookup"><span data-stu-id="23cd9-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="23cd9-124">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="23cd9-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="23cd9-125">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="23cd9-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="23cd9-126">Étape 3 : Déployer un pool pilote</span><span class="sxs-lookup"><span data-stu-id="23cd9-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="23cd9-127">Étape 4: déplacer les utilisateurs de test vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="23cd9-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="23cd9-128">Étape 5 : Ajouter un serveur Edge au pool pilote</span><span class="sxs-lookup"><span data-stu-id="23cd9-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="23cd9-129">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="23cd9-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="23cd9-130">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="23cd9-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="23cd9-131">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="23cd9-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

