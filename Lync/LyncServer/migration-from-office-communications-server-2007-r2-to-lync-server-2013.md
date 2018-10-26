---
title: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013
TOCTitle: Migration d’Office Communications Server 2007 R2 vers Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205375(v=OCS.15)
ms:contentKeyID: 49299354
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration d’Office Communications Server 2007 R2 vers Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Les rubriques de cette section vous guideront durant le processus de migration de Office Communications Server 2007 R2 vers Lync Server 2013

> [!IMPORTANT]  
> Le présent document décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce document propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre propre processus de migration.

Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.

Ce document définit les termes spécifiés dans la liste suivante.

  - *migration*   
    Déplacement de votre déploiement de production depuis une version précédente d’Office Communications Server 2007 R2 vers Lync Server 2013.

<!-- end list -->

  - *mise à niveau*   
    Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.

<!-- end list -->

  - *coexistence*   
    Environnement temporaire qui existe durant la migration lorsque certaines fonctionnalités sont déplacées vers Lync Server 2013 alors que d’autres restent encore sur une version précédente d’Office Communications Server 2007 R2.

<!-- end list -->

  - *interopérabilité*   
    Capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

## Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration_1.md)

  - [Phases de migration](migration-phases_1.md)

  - [Phase 1 : Planification de la migration à partir d’Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Phase 2 : Préparation de la migration](phase-2-prepare-for-migration_1.md)

  - [Phase 3 : Déploiement du pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Phase 4 : Fusion des topologies](phase-4-merge-topologies.md)

  - [Phase 5 : Configuration du pool pilote](phase-5-configure-the-pilot-pool.md)

  - [Phase 6 : Déplacement des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md)

  - [Phase 7 : Ajout d’un serveur Edge Lync Server 2013 à un pool pilote](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8 : Transition d’un déploiement pilote vers un environnement de production](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9 : Exécution des tâches post-migration](phase-9-complete-post-migration-tasks.md)

  - [Phase 10 : Mise hors service d’un site hérité](phase-10-decommission-legacy-site.md)

