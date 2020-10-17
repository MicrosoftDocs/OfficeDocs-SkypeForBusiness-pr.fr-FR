---
title: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013
description: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0afdc754ae691bc674c200addb9fb97c1eb4199
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569590"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="82164-103">Migration d’Office Communications Server 2007 R2 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82164-103">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82164-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="82164-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="82164-105">Les rubriques de cette section vous guident tout au long du processus de migration d’Office Communications Server 2007 R2 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82164-105">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82164-p101">Le présent document décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce document propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre processus de migration propre.</span><span class="sxs-lookup"><span data-stu-id="82164-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="82164-p102">Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.</span><span class="sxs-lookup"><span data-stu-id="82164-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="82164-116">Ce document définit les termes spécifiés dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="82164-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="82164-117">*MIGR*</span><span class="sxs-lookup"><span data-stu-id="82164-117">*migration*</span></span>  
    <span data-ttu-id="82164-118">Migration de votre déploiement de production d’une version précédente d’Office Communications Server 2007 R2 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82164-118">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="82164-119">*mise à niveau*</span><span class="sxs-lookup"><span data-stu-id="82164-119">*upgrade*</span></span>  
    <span data-ttu-id="82164-120">Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="82164-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="82164-121">*coexistence*</span><span class="sxs-lookup"><span data-stu-id="82164-121">*coexistence*</span></span>  
    <span data-ttu-id="82164-122">Environnement temporaire qui existe lors de la migration, quand une fonctionnalité a été migrée vers Lync Server 2013 et que d’autres fonctionnalités demeurent sur une version antérieure d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="82164-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="82164-123">*interopérabilité*</span><span class="sxs-lookup"><span data-stu-id="82164-123">*interoperability*</span></span>  
    <span data-ttu-id="82164-124">Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.</span><span class="sxs-lookup"><span data-stu-id="82164-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82164-125">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="82164-125">In This Section</span></span>

  - [<span data-ttu-id="82164-126">Avant de commencer la migration</span><span class="sxs-lookup"><span data-stu-id="82164-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="82164-127">Phases de migration</span><span class="sxs-lookup"><span data-stu-id="82164-127">Migration phases</span></span>](migration-phases.md)

  - [<span data-ttu-id="82164-128">Phase 1 : planifier votre migration à partir d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="82164-128">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="82164-129">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="82164-129">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="82164-130">Phase 3 : déployer le pool pilote Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82164-130">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="82164-131">Phase 4 : fusionner les topologies</span><span class="sxs-lookup"><span data-stu-id="82164-131">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="82164-132">Phase 5 : configuration du pool pilote</span><span class="sxs-lookup"><span data-stu-id="82164-132">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="82164-133">Phase 6 : déplacer des utilisateurs vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="82164-133">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="82164-134">Phase 7 : ajouter le serveur Edge Lync Server 2013 au pool pilote</span><span class="sxs-lookup"><span data-stu-id="82164-134">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="82164-135">Phase 8 : passer d’un déploiement pilote en production</span><span class="sxs-lookup"><span data-stu-id="82164-135">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="82164-136">Phase 9 : effectuer les tâches postérieures à la migration</span><span class="sxs-lookup"><span data-stu-id="82164-136">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="82164-137">Phase 10 : mettre hors service le site hérité</span><span class="sxs-lookup"><span data-stu-id="82164-137">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

