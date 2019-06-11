---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Phases de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

Dans Lync Server 2013, vous définissez des sites sur votre réseau qui contiennent les composants Lync Server 2013. Un site est un ensemble d’ordinateurs qui sont bien connectés par le biais d’un réseau haut débit à faible latence, par exemple un réseau local unique (LAN) ou deux réseaux connectés par un réseau fibres optiques haut débit.

Un *pool frontal* est un ensemble de serveurs frontaux configurés de manière identique et collabore pour fournir des services à un groupe d’utilisateurs communs. Un pool fournit une capacité d’évolutivité et de basculement pour les utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un serveur unique. Cela vous permet d’utiliser la fonctionnalité Lync Server 2013 pour un coût inférieur, mais ne fournit pas de véritable solution de disponibilité élevée.

Les phases suivantes décrivent le processus de migration d’un pool de Lync Server 2010 vers Lync Server 2013. Pour les sites multiples contenant plusieurs pools, chaque pool individuel doit suivre cette approche par phases.

1.  [Étape 1: planifier la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)

3.  [Étape 3: déployer le pool de pilotes de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Étape 4: déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Étape 5: ajouter le serveur Edge Lync Server 2013 au pool de pilotes](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)

8.  [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

