---
title: Migration vers Skype Entreprise Server 2019
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
description: Les rubriques de cette section vous guident tout au long du processus de migration vers Skype Entreprise Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752616"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migration vers Skype Entreprise Server 2019

Les rubriques de cette section vous guident tout au long du processus de migration vers Skype Entreprise Server 2019. Cet article traite de la migration de Lync Server 2013 ou Skype Entreprise Server 2015 vers Skype Entreprise Server 2019.

> [!IMPORTANT]
> Tout au long du contenu, nous utilisons le terme hérité pour faire référence à l’hérité Lync Server 2013 ou Skype Entreprise Server 2015 que vous migrez vers Skype Entreprise Server 2019. 
  
> [!IMPORTANT]
> Ce guide décrit les étapes généralement requises pour accomplir chaque phase de migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles ni tous les scénarios de migration possibles. Par conséquent, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce guide fournit également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Adaptez-les à votre processus de migration propre. 
  
Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est documentée ailleurs, ce guide vous dirige vers l’article ou la section de l’article. 
  
Cet article définit les termes spécifiés dans la liste suivante.
  
**migration :** Déplacement de votre déploiement de production de Lync Server 2013 ou Skype Entreprise Server 2015 vers Skype Entreprise Server 2019.
    
**coexistence :** L’environnement temporaire qui existe pendant la migration lorsque certaines fonctionnalités ont été migrées vers Skype Entreprise Server 2019 et que d’autres fonctionnalités restent sur une version antérieure.
    
**interopérabilité :** La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

**legacy :** Système duquel vous migrez, soit Lync Server 2013, soit Skype Entreprise Server 2015.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Avant de commencer la migration](before-you-begin-the-migration.md)
    
- [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
- [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
- [Étape 3 : Déployer un pool pilote](phase-3-deploy-pilot-pool.md)
    
- [Phase 4 : Déplacer les utilisateurs de test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Étape 5 : Ajouter un serveur Edge au pool pilote](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
- [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

