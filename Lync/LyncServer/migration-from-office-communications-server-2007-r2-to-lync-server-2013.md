---
title: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013
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
ms.openlocfilehash: a71ac7e0e1291dedfa45e4e358b5b3495d8a623b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527251"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migration d’Office Communications Server 2007 R2 vers Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Les rubriques de cette section vous guident tout au long du processus de migration d’Office Communications Server 2007 R2 vers Lync Server 2013

<div>


> [!IMPORTANT]  
> Le présent document décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce document propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre processus de migration propre.



</div>

Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.

Ce document définit les termes spécifiés dans la liste suivante.

  - *MIGR*  
    Migration de votre déploiement de production d’une version précédente d’Office Communications Server 2007 R2 vers Lync Server 2013.

<!-- end list -->

  - *mise à niveau*  
    Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.

<!-- end list -->

  - *coexistence*  
    Environnement temporaire qui existe lors de la migration, quand une fonctionnalité a été migrée vers Lync Server 2013 et que d’autres fonctionnalités demeurent sur une version antérieure d’Office Communications Server 2007 R2.

<!-- end list -->

  - *interopérabilité*  
    Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration_1.md)

  - [Phases de migration](migration-phases_1.md)

  - [Phase 1 : planifier votre migration à partir d’Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Étape 2 : Préparer la migration](phase-2-prepare-for-migration_1.md)

  - [Phase 3 : déployer le pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Phase 4 : fusionner les topologies](phase-4-merge-topologies.md)

  - [Phase 5 : configuration du pool pilote](phase-5-configure-the-pilot-pool.md)

  - [Phase 6 : déplacer des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md)

  - [Phase 7 : ajouter le serveur Edge Lync Server 2013 au pool pilote](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8 : passer d’un déploiement pilote en production](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9 : effectuer les tâches postérieures à la migration](phase-9-complete-post-migration-tasks.md)

  - [Phase 10 : mettre hors service le site hérité](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

