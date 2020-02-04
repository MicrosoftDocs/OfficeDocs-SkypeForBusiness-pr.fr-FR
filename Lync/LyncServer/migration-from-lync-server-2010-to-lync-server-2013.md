---
title: Migration de Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c32d2679d4f31863e389735efb6660ea670b959
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="a9181-102">Migration de Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9181-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9181-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a9181-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a9181-104">Les rubriques de cette section vous guident dans le processus de migration de Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9181-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9181-105">Ce document décrit les étapes généralement requises pour effectuer chaque phase de la migration.</span><span class="sxs-lookup"><span data-stu-id="a9181-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="a9181-106">Elle ne traite pas chaque topologie de déploiement hérité possible ou chaque scénario de migration possible.</span><span class="sxs-lookup"><span data-stu-id="a9181-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="a9181-107">Par conséquent, il est possible que vous n’ayez pas à effectuer toutes les étapes décrites ou que vous deviez effectuer des étapes supplémentaires, selon votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a9181-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="a9181-108">Ce document fournit également des exemples de procédure de vérification.</span><span class="sxs-lookup"><span data-stu-id="a9181-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="a9181-109">Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez savoir pour vous assurer que toutes les phases s’exécutent correctement lors de la migration.</span><span class="sxs-lookup"><span data-stu-id="a9181-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="a9181-110">Adaptez ces étapes de vérification à votre processus de migration spécifique.</span><span class="sxs-lookup"><span data-stu-id="a9181-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="a9181-111">Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="a9181-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="a9181-112">Il n’explique pas comment modifier votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="a9181-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="a9181-113">Ce guide ne traite pas de l’implémentation des nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="a9181-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="a9181-114">Lorsqu’une procédure détaillée est documentée à un autre emplacement, ce guide vous dirige vers la section document ou document appropriée.</span><span class="sxs-lookup"><span data-stu-id="a9181-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="a9181-115">Ce document définit les termes indiqués dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="a9181-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="a9181-116">*vers*</span><span class="sxs-lookup"><span data-stu-id="a9181-116">*migration*</span></span>  
    <span data-ttu-id="a9181-117">Migration de votre déploiement de production d’une version antérieure de Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9181-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="a9181-118">*installation*</span><span class="sxs-lookup"><span data-stu-id="a9181-118">*upgrade*</span></span>  
    <span data-ttu-id="a9181-119">Installation d’une nouvelle version du logiciel sur un ordinateur client ou serveur.</span><span class="sxs-lookup"><span data-stu-id="a9181-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="a9181-120">*coexistence*</span><span class="sxs-lookup"><span data-stu-id="a9181-120">*coexistence*</span></span>  
    <span data-ttu-id="a9181-121">Environnement temporaire existant lors de la migration lors de la migration de certaines fonctionnalités vers Lync Server 2013 et d’autres fonctionnalités continuent d’exister sur une version antérieure de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a9181-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="a9181-122">*interopérabilité*</span><span class="sxs-lookup"><span data-stu-id="a9181-122">*interoperability*</span></span>  
    <span data-ttu-id="a9181-123">La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.</span><span class="sxs-lookup"><span data-stu-id="a9181-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9181-124">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a9181-124">In This Section</span></span>

  - [<span data-ttu-id="a9181-125">Avant de commencer la migration</span><span class="sxs-lookup"><span data-stu-id="a9181-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="a9181-126">Étape 1 : planifier la migration à partir de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9181-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="a9181-127">Étape 2 : Préparer la migration</span><span class="sxs-lookup"><span data-stu-id="a9181-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="a9181-128">Étape 3 : déployer le pool de pilotes de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9181-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="a9181-129">Étape 4 : déplacer les utilisateurs de test vers le pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="a9181-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="a9181-130">Étape 5 : ajouter le serveur Edge Lync Server 2013 au pool de pilotes</span><span class="sxs-lookup"><span data-stu-id="a9181-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="a9181-131">Phase 6 : Transition d’un déploiement pilote vers un environnement de production</span><span class="sxs-lookup"><span data-stu-id="a9181-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="a9181-132">Étape 7 : Exécuter les tâches post-migration</span><span class="sxs-lookup"><span data-stu-id="a9181-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="a9181-133">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="a9181-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

