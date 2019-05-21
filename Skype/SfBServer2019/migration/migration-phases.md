---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par le biais d’un réseau haut débit à faible latence, par exemple un réseau local unique (LAN) ou deux réseaux connectés par un réseau fibres optiques haut débit.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298161"
---
# <a name="migration-phases"></a>Phases de migration

Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par le biais d’un réseau haut débit à faible latence, par exemple un réseau local unique (LAN) ou deux réseaux connectés par un réseau fibres optiques haut débit. 
  
Un pool frontal est un ensemble de serveurs frontaux configurés de manière identique et collabore pour fournir des services à un groupe d’utilisateurs communs. Un pool fournit une capacité d’évolutivité et de basculement pour les utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un serveur unique. Cela vous permet de disposer de la fonctionnalité Skype entreprise Server 2019 pour un coût inférieur, mais ne fournit pas de véritable solution de haute disponibilité. 
  
Les phases suivantes décrivent le processus de migration d’un pool vers Skype entreprise Server 2019. Pour les sites multiples contenant plusieurs pools, chaque pool individuel doit suivre cette approche par phases.
  
1. [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
2. [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
3. [Étape 3: déploiement du pool de pilotes Skype entreprise Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Étape 4: déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Étape 5: ajouter le serveur Edge de Skype entreprise Server 2019 au pool de pilotes](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
8. [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

