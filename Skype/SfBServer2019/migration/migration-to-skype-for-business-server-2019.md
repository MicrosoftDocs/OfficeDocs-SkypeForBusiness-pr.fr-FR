---
title: Migration vers Skype entreprise Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les rubriques de cette section vous guident dans le processus de migration vers Skype entreprise Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813402"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migration vers Skype entreprise Server 2019

Les rubriques de cette section vous guident dans le processus de migration vers Skype entreprise Server 2019. Cet article décrit la migration de Lync Server 2013 ou de Skype entreprise Server 2015 vers Skype entreprise Server 2019.

> [!IMPORTANT]
> Dans l’ensemble du contenu, nous utilisons le terme *hérité* pour faire référence à l’ancien serveur Lync Server 2013 ou à Skype entreprise Server 2015 que vous migrez vers Skype entreprise Server 2019.
  
> [!IMPORTANT]
> Ce guide décrit les étapes généralement requises pour effectuer chaque phase de migration. Elle ne traite pas chaque topologie de déploiement hérité possible ou chaque scénario de migration possible. Par conséquent, il est possible que vous n’ayez pas à effectuer toutes les étapes décrites ou que vous deviez effectuer des étapes supplémentaires, selon votre déploiement. Ce guide fournit également des exemples de procédure de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez savoir pour vous assurer que toutes les phases s’exécutent correctement lors de la migration. Adaptez ces étapes de vérification à votre processus de migration spécifique. 
  
Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Ce guide ne traite pas de l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est documentée à un autre emplacement, ce guide vous dirige vers l’article ou la section article. 
  
Cet article définit les termes comme spécifié dans la liste suivante.
  
**migration :** Migration de votre déploiement de production de Lync Server 2013 ou de Skype entreprise Server 2015 vers Skype entreprise Server 2019.
    
**coexistence :** Environnement temporaire existant lors de la migration lors de la migration de certaines fonctionnalités vers Skype entreprise Server 2019 et si d’autres fonctionnalités continuent de subsister dans une version antérieure.
    
**interopérabilité :** La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

**héritage :** Le système à partir duquel vous effectuez la migration, qui est Lync Server 2013 ou Skype entreprise Server 2015.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Avant de commencer la migration](before-you-begin-the-migration.md)
    
- [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
- [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
- [Étape 3 : Déployer un pool pilote](phase-3-deploy-pilot-pool.md)
    
- [Étape 4 : déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Étape 5 : Ajouter un serveur Edge au pool pilote](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
- [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

