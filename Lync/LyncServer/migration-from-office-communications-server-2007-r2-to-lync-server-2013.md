---
title: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migration d’Office Communications Server 2007 R2 vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Les rubriques de cette section vous guident tout au long du processus de migration d’Office Communications Server 2007 R2 vers Lync Server 2013

<div>


> [!IMPORTANT]  
> Ce document décrit les étapes généralement requises pour effectuer chaque phase de la migration. Elle ne traite pas chaque topologie de déploiement hérité possible ou chaque scénario de migration possible. Par conséquent, il est possible que vous n’ayez pas à effectuer toutes les étapes décrites ou que vous deviez effectuer des étapes supplémentaires, selon votre déploiement. Ce document fournit également des exemples de procédure de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez savoir pour vous assurer que toutes les phases s’exécutent correctement lors de la migration. Adaptez ces étapes de vérification à votre processus de migration spécifique.



</div>

Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Ce guide ne traite pas de l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est documentée à un autre emplacement, ce guide vous dirige vers la section document ou document appropriée.

Ce document définit les termes indiqués dans la liste suivante.

  - *vers*  
    Migration de votre déploiement de production d’une version antérieure d’Office Communications Server 2007 R2 vers Lync Server 2013.

<!-- end list -->

  - *installation*  
    Installation d’une nouvelle version du logiciel sur un ordinateur client ou serveur.

<!-- end list -->

  - *coexistence*  
    L’environnement temporaire existant lors de la migration lors de la migration de certaines fonctionnalités vers Lync Server 2013 et d’autres fonctionnalités continuent de subsister sur une version antérieure d’Office Communications Server 2007 R2.

<!-- end list -->

  - *interopérabilité*  
    La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration_1.md)

  - [Phases de migration](migration-phases_1.md)

  - [Étape 1: planifier la migration à partir d’Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Étape 2 : Préparer la migration](phase-2-prepare-for-migration_1.md)

  - [Étape 3: déployer le pool de pilotes de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Étape 4: fusionner les topologies](phase-4-merge-topologies.md)

  - [Étape 5: configurer le pool de pilotes](phase-5-configure-the-pilot-pool.md)

  - [Étape 6: déplacer les utilisateurs vers le pool de pilotes](phase-6-move-users-to-the-pilot-pool.md)

  - [Étape 7: ajouter le serveur Edge Lync Server 2013 au pool de pilotes](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8: basculer entre le déploiement pilote et la production](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9: effectuer les tâches postérieures à la migration](phase-9-complete-post-migration-tasks.md)

  - [Étape 10: désaffecter le site hérité](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

