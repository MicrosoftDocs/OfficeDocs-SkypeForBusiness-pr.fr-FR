---
title: Phases de migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants de Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752626"
---
# <a name="migration-phases"></a>Phases de migration

Dans Skype entreprise Server 2019, vous définissez des sites sur votre réseau qui contiennent des composants de Skype entreprise Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau à haute vitesse et à faible latence, tels qu’un réseau local (LAN) ou deux réseaux connectés par un réseau fibre optique à grande vitesse. 
  
Un pool frontal est un ensemble de serveurs frontaux configurés de manière identique et qui fonctionnent ensemble pour fournir des services à un groupe commun d’utilisateurs. Un pool fournit l’évolutivité et la fonction de basculement aux utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Un serveur Standard Edition, conçu pour les petites organisations, définit également un pool et s’exécute sur un seul serveur. Cela vous permet de disposer des fonctionnalités de Skype entreprise Server 2019 pour un coût moindre, mais ne fournit pas une véritable solution de haute disponibilité. 
  
Les phases suivantes décrivent le processus de migration d’un pool vers Skype entreprise Server 2019. Dans le cas de sites multiples contenant des pools multiples, chaque pool doit suivre cette approche basée sur des phases.
  
1. [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
2. [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
3. [Phase 3 : déploiement du pool pilote Skype entreprise Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Phase 5 : ajouter le serveur Edge de Skype entreprise Server 2019 au pool pilote](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
8. [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

