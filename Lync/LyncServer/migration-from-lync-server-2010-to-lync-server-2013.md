---
title: Migration de Lync Server 2010 vers Lync Server 2013
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
ms.openlocfilehash: 7ea588abf4018ab06a415d4aa5ef7decf5f93996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migration de Lync Server 2010 vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Les rubriques de cette section vous guident tout au long du processus de migration de Lync Server 2010 vers Lync Server 2013.

<div>


> [!IMPORTANT]  
> Le présent document décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce document propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre processus de migration propre.



</div>

Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.

Ce document définit les termes spécifiés dans la liste suivante.

  - *MIGR*  
    Migration de votre déploiement de production d’une version antérieure de Lync Server 2010 vers Lync Server 2013.

<!-- end list -->

  - *mise à niveau*  
    Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.

<!-- end list -->

  - *coexistence*  
    Environnement temporaire qui existe lors de la migration, quand une fonctionnalité a été migrée vers Lync Server 2013 et que d’autres fonctionnalités demeurent sur une version antérieure de Lync Server 2010.

<!-- end list -->

  - *interopérabilité*  
    Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration.md)

  - [Phase 1 : planification de la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Phase 2 : préparer la migration](phase-2-prepare-for-migration.md)

  - [Phase 3 : déployer le pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Phase 5 : ajouter le serveur Edge Lync Server 2013 au pool pilote](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6 : passer d’un déploiement pilote en production](phase-6-move-from-pilot-deployment-into-production.md)

  - [Phase 7 : effectuer les tâches postérieures à la migration](phase-7-complete-post-migration-tasks.md)

  - [Phase 8 : désactiver les pools hérités](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

