---
title: Migration vers Skype pour Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les rubriques de cette section vous guident tout au long du processus de migration vers Skype pour Business Server 2019.
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231608"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="9dfc0-103">Migration vers Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9dfc0-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="9dfc0-104">Les rubriques de cette section vous guident tout au long du processus de migration vers Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="9dfc0-105">Cet article traite migration Lync Server 2013 ou Skype pour Business Server 2015 à Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dfc0-106">Dans l’ensemble du contenu, nous utilisons le terme *hérité* pour faire référence à hérité Lync Server 2013 ou Skype pour Business Server 2015 que vous migrez vers Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9dfc0-107">Ce guide décrit les étapes généralement requises pour effectuer chaque phase de migration.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="9dfc0-108">Il ne traite pas chaque topologie de déploiement hérité possibles ou chaque scénario de migration possibles.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="9dfc0-109">Par conséquent, vous devrez pas effectuer toutes les étapes décrites, ou vous devrez peut-être effectuer des étapes supplémentaires, en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="9dfc0-110">Ce guide fournit également des exemples d’étapes de vérification.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="9dfc0-111">Ces étapes de vérification sont fournis pour vous aider à comprendre ce qu’il faut rechercher pour s’assurer que chaque phase se termine avec succès au cours de la migration.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="9dfc0-112">Personnaliser ces étapes de vérification pour votre processus de migration spécifique.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="9dfc0-113">Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="9dfc0-114">Il n’explique pas comment modifier votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="9dfc0-115">Ce guide n’aborde pas l’implémentation de nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="9dfc0-116">Lors de la procédure détaillée est expliquée ailleurs, ce guide vous dirige vers la section de l’article ou un article.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="9dfc0-117">Cet article définit les termes spécifiés dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="9dfc0-118">**migration :** Déplacement de votre déploiement de production à partir de Lync Server 2013 ou Skype pour Business Server 2015 à Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="9dfc0-119">**coexistence :** Environnement temporaire qui existe durant la migration lorsque certaines fonctionnalités ont été migrées vers Skype pour Business Server 2019 et d’autres fonctionnalités reste encore sur une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="9dfc0-120">**interopérabilité :** La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="9dfc0-121">**hérité :** Le système vous migrez des, qui est soit Lync Server 2013 soit Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9dfc0-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="9dfc0-122">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="9dfc0-122">In this section</span></span>

- [<span data-ttu-id="9dfc0-123">Avant de commencer la migration</span><span class="sxs-lookup"><span data-stu-id="9dfc0-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="9dfc0-124">Étape 1 : Planifier la migration</span><span class="sxs-lookup"><span data-stu-id="9dfc0-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="9dfc0-125">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="9dfc0-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="9dfc0-126">Étape 3 : Déployer un pool pilote</span><span class="sxs-lookup"><span data-stu-id="9dfc0-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="9dfc0-127">Phase 4 : Déplacer les utilisateurs de test le pool pilote</span><span class="sxs-lookup"><span data-stu-id="9dfc0-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="9dfc0-128">Étape 5 : Ajouter un serveur Edge au pool pilote</span><span class="sxs-lookup"><span data-stu-id="9dfc0-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="9dfc0-129">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="9dfc0-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="9dfc0-130">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="9dfc0-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="9dfc0-131">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="9dfc0-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

