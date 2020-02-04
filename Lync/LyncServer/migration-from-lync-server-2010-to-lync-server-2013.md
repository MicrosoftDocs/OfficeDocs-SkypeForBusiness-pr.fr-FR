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

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migration de Lync Server 2010 vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Les rubriques de cette section vous guident dans le processus de migration de Lync Server 2010 vers Lync Server 2013.

<div>


> [!IMPORTANT]  
> Ce document décrit les étapes généralement requises pour effectuer chaque phase de la migration. Elle ne traite pas chaque topologie de déploiement hérité possible ou chaque scénario de migration possible. Par conséquent, il est possible que vous n’ayez pas à effectuer toutes les étapes décrites ou que vous deviez effectuer des étapes supplémentaires, selon votre déploiement. Ce document fournit également des exemples de procédure de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez savoir pour vous assurer que toutes les phases s’exécutent correctement lors de la migration. Adaptez ces étapes de vérification à votre processus de migration spécifique.



</div>

Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Ce guide ne traite pas de l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est documentée à un autre emplacement, ce guide vous dirige vers la section document ou document appropriée.

Ce document définit les termes indiqués dans la liste suivante.

  - *vers*  
    Migration de votre déploiement de production d’une version antérieure de Lync Server 2010 vers Lync Server 2013.

<!-- end list -->

  - *installation*  
    Installation d’une nouvelle version du logiciel sur un ordinateur client ou serveur.

<!-- end list -->

  - *coexistence*  
    Environnement temporaire existant lors de la migration lors de la migration de certaines fonctionnalités vers Lync Server 2013 et d’autres fonctionnalités continuent d’exister sur une version antérieure de Lync Server 2010.

<!-- end list -->

  - *interopérabilité*  
    La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Avant de commencer la migration](before-you-begin-the-migration.md)

  - [Étape 1 : planifier la migration à partir de Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)

  - [Étape 3 : déployer le pool de pilotes de Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Étape 4 : déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Étape 5 : ajouter le serveur Edge Lync Server 2013 au pool de pilotes](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)

  - [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)

  - [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

