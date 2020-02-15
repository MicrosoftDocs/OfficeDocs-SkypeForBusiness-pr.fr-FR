---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08379ec217cc684ae9b6bc11c44b89a3d642f6df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Phases de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Dans Lync Server 2013, vous définissez des sites sur votre réseau qui contiennent des composants Lync Server 2013. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse.

Un *pool frontal* est un ensemble de serveurs frontaux configurés de manière identique et qui fonctionnent ensemble pour fournir des services à un groupe commun d’utilisateurs. Un pool fournit l’évolutivité et la fonction de basculement aux utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un seul serveur. Cela vous permet de disposer des fonctionnalités Lync Server 2013 pour un coût moindre, mais ne fournit pas de véritable solution de haute disponibilité.

Les phases suivantes décrivent le processus de migration d’un pool de Lync Server 2010 vers Lync Server 2013. Dans le cas de sites multiples contenant des pools multiples, chaque pool doit suivre cette approche basée sur des phases.

1.  [Phase 1 : planification de la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Phase 2 : préparer la migration](phase-2-prepare-for-migration.md)

3.  [Phase 3 : déployer le pool pilote Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Phase 5 : ajouter le serveur Edge Lync Server 2013 au pool pilote](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6 : passer d’un déploiement pilote en production](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Phase 7 : effectuer les tâches postérieures à la migration](phase-7-complete-post-migration-tasks.md)

8.  [Phase 8 : désactiver les pools hérités](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

