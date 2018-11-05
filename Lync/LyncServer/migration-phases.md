---
title: Phases de migration
TOCTitle: Phases de migration
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205336(v=OCS.15)
ms:contentKeyID: 49298873
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Phases de migration

 

_**Dernière rubrique modifiée :** 2012-09-17_

Dans Lync Server 2013, vous définissez des sites sur votre réseau qui contiennent des composants Lync Server 2013. Un site est un ensemble d’ordinateurs correctement connectés via un réseau à haut débit et à faible latence, tel qu’un réseau local unique ou deux réseaux connectés par un réseau en fibre optique à haut débit.

Un *pool frontal* est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent de pair pour proposer des services à un groupe commun d’utilisateurs. Un pool fournit des fonctionnalités d’évolutivité et de basculement aux utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Conçu pour les petites organisations, un serveur Standard Edition définit également un pool et est exécuté sur un seul serveur. Cela vous permet de disposer des fonctionnalités de Lync Server 2013 à moindre coût, mais ne vous offre pas de véritable solution à haute disponibilité.

Les phases suivantes décrivent la migration d’un pool de Lync Server 2010 vers Lync Server 2013. Lorsqu’il y a plusieurs sites contenant plusieurs pools, chaque pool individuel doit suivre cette approche par phase.

1.  [Phase 1 : Planification de la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Phase 2 : Préparation de la migration](phase-2-prepare-for-migration.md)

3.  [Phase 3 : Déploiement du pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Phase 4 : Déplacement des utilisateurs de test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Phase 5 : Ajout d’un serveur Edge Lync Server 2013 à un pool pilote](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Phase 7 : Exécution des tâches post-migration \[W14 vers W15\]](phase-7-complete-post-migration-tasks.md)

8.  [Phase 8 : Mise hors service des pools hérités](phase-8-decommission-legacy-pools.md)

