---
title: Migration de Lync Server 2010 vers Lync Server 2013
TOCTitle: Migration de Lync Server 2010 vers Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205369(v=OCS.15)
ms:contentKeyID: 49299273
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de Lync Server 2010 vers Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-17_

Les rubriques de cette section vous guident à travers le processus de migration de Lync Server 2010 vers Lync Server 2013.

> [!IMPORTANT]  
> Le présent document décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce document propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre propre processus de migration.

Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.

Ce document définit les termes spécifiés dans la liste suivante.

  - *migration*   
    Déplacement de votre déploiement de production depuis une version précédente d’Lync Server 2010 vers Lync Server 2013.

<!-- end list -->

  - *mise à niveau*   
    Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.

<!-- end list -->

  - *coexistence*   
    Environnement temporaire qui existe durant la migration lorsque certaines fonctionnalités sont déplacées vers Lync Server 2013 alors que d’autres restent encore sur une version précédente d’Lync Server 2010.

<!-- end list -->

  - *interopérabilité*   
    Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

## Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration.md)

  - [Phase 1 : Planification de la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Phase 2 : Préparation de la migration](phase-2-prepare-for-migration.md)

  - [Phase 3 : Déploiement du pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Phase 4 : Déplacement des utilisateurs de test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Phase 5 : Ajout d’un serveur Edge Lync Server 2013 à un pool pilote](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)

  - [Phase 7 : Exécution des tâches post-migration \[W14 vers W15\]](phase-7-complete-post-migration-tasks.md)

  - [Phase 8 : Mise hors service des pools hérités](phase-8-decommission-legacy-pools.md)

