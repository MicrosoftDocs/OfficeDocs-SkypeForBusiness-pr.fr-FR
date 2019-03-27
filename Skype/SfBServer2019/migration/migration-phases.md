---
title: Phases de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype pour Business Server 2019, vous définissez les sites de votre réseau qui contiennent Skype pour les composants Business Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau rapide et à faible latence, par exemple un réseau local (LAN) unique ou deux réseaux connectés par un réseau optique Fibre à haute vitesse.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886528"
---
# <a name="migration-phases"></a>Phases de migration

Dans Skype pour Business Server 2019, vous définissez les sites de votre réseau qui contiennent Skype pour les composants Business Server 2019. Un site est un ensemble d’ordinateurs qui sont bien connectés par un réseau rapide et à faible latence, par exemple un réseau local (LAN) unique ou deux réseaux connectés par un réseau optique Fibre à haute vitesse. 
  
Un pool frontal est un ensemble de serveurs frontaux qui sont configurés à l’identique et ensemble pour fournir des services à un groupe commun d’utilisateurs. Un pool fournit l’évolutivité et la capacité de basculement à vos utilisateurs. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Un serveur Standard Edition server, conçu pour les petites organisations, également définit un pool et s’exécute sur un serveur unique. Cela vous permet d’avoir Skype pour la fonctionnalité Business Server 2019 pour un coût inférieur, mais ne fournit pas une véritable solution de haute disponibilité. 
  
Les phases suivantes décrivent le processus de migration pool vers Skype pour Business Server 2019. Plusieurs sites contenant plusieurs pools, chaque pool doit suivre cette approche progressive.
  
1. [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
2. [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
3. [Phase 3 : Déploiement Skype pour le pool pilote Business Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Phase 4 : Déplacer les utilisateurs de test le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Phase 5 : Ajoutez Skype pour Business Server 2019 Edge Server vers le pool pilote](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
8. [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

