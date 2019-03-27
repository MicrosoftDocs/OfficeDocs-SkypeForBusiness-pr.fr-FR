---
title: Migration vers Skype pour Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les rubriques de cette section vous guident tout au long du processus de migration vers Skype pour Business Server 2019.
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881596"
---
# <a name="migration-to-skype-for-business-server-2019"></a>Migration vers Skype pour Business Server 2019

Les rubriques de cette section vous guident tout au long du processus de migration vers Skype pour Business Server 2019. Cet article traite migration Lync Server 2013 ou Skype pour Business Server 2015 à Skype pour Business Server 2019.

> [!IMPORTANT]
> Dans l’ensemble du contenu, nous utilisons le terme *hérité* pour faire référence à hérité Lync Server 2013 ou Skype pour Business Server 2015 que vous migrez vers Skype pour Business Server 2019.
  
> [!IMPORTANT]
> Ce guide décrit les étapes généralement requises pour effectuer chaque phase de migration. Il ne traite pas chaque topologie de déploiement hérité possibles ou chaque scénario de migration possibles. Par conséquent, vous devrez pas effectuer toutes les étapes décrites, ou vous devrez peut-être effectuer des étapes supplémentaires, en fonction de votre déploiement. Ce guide fournit également des exemples d’étapes de vérification. Ces étapes de vérification sont fournis pour vous aider à comprendre ce qu’il faut rechercher pour s’assurer que chaque phase se termine avec succès au cours de la migration. Personnaliser ces étapes de vérification pour votre processus de migration spécifique. 
  
Ce guide fournit des informations spécifiques à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Ce guide n’aborde pas l’implémentation de nouvelles fonctionnalités. Lors de la procédure détaillée est expliquée ailleurs, ce guide vous dirige vers la section de l’article ou un article. 
  
Cet article définit les termes spécifiés dans la liste suivante.
  
**migration :** Déplacement de votre déploiement de production à partir de Lync Server 2013 ou Skype pour Business Server 2015 à Skype pour Business Server 2019.
    
**coexistence :** Environnement temporaire qui existe durant la migration lorsque certaines fonctionnalités ont été migrées vers Skype pour Business Server 2019 et d’autres fonctionnalités reste encore sur une version antérieure.
    
**interopérabilité :** La capacité de votre déploiement à fonctionner correctement pendant la période de coexistence.

**hérité :** Le système vous migrez des, qui est soit Lync Server 2013 soit Skype pour Business Server 2015.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Avant de commencer la migration](before-you-begin-the-migration.md)
    
- [Étape 1 : Planifier la migration](phase-1-plan-your-migration.md)
    
- [Étape 2 : Préparer la migration](phase-2-prepare-for-migration.md)
    
- [Étape 3 : Déployer un pool pilote](phase-3-deploy-pilot-pool.md)
    
- [Phase 4 : Déplacer les utilisateurs de test le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [Étape 5 : Ajouter un serveur Edge au pool pilote](phase-5-add-edge-server-to-pilot-pool.md)
    
- [Phase 6 : Transition d’un déploiement pilote vers un environnement de production](phase-6-move-from-pilot-deployment-into-production.md)
    
- [Étape 7 : Exécuter les tâches post-migration](phase-7-complete-post-migration-tasks.md)
    
- [Étape 8 : Mettre des pools hérités hors service](phase-8-decommission-legacy-pools.md)
    

