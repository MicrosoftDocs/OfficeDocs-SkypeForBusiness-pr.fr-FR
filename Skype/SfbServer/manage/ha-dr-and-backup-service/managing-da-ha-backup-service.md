---
title: Gestion de Service de sauvegarde, haute disponibilité et la récupération d’urgence
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez les procédures pour les opérations de récupération d’urgence, ainsi que pour gérer le Service de sauvegarde qui synchronise les données dans des pools frontaux couplés.
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199825"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gestion de Skype pour le Service de sauvegarde, haute disponibilité et la récupération d’urgence Business Server

Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour gérer le Service de sauvegarde qui synchronise les données dans des pools frontaux couplés.

Procédures de récupération d’urgence, le basculement et la restauration automatique, sont manuelles. S’il existe une catastrophe, l’administrateur doit appeler manuellement les procédures de basculement. Les mêmes s’applique à la restauration automatique une fois que le pool est réparé.

Les procédures de récupération d’urgence dans cette section supposent les éléments suivants :

  - Vous disposez d’un déploiement avec des pools frontaux couplés, situés dans différents sites, comme décrit dans le [Plan de haute disponibilité et récupération d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). Le Service de sauvegarde a été exécuté sur ces pools associés pour qu’elles soient synchronisées.

  - Si le magasin Central de gestion est hébergé sur un pool, il est installé et en cours d’exécution sur les deux pools associés, avec un de ces pools hébergeant le contrôleur actif et l’autre pool hébergeant la mise en veille.

> [!IMPORTANT]
> Dans les procédures suivantes, le paramètre *PoolFQDN* désigne le nom de domaine complet du pool qui est affecté par la reprise après sinistre, pas le pool qui ont affecté les utilisateurs sont redirigés à partir de. Pour le même ensemble d’utilisateurs affectés, il fait référence au même pool dans le basculement et la restauration des applets de commande (autrement dit, le pool hébergé tout d’abord les utilisateurs avant le basculement).<BR><br>Par exemple, supposons un cas dans lequel tous les utilisateurs hébergement sur un pool P1 ont été basculés vers le pool de sauvegarde, P2. Si l’administrateur souhaite déplacer tous les utilisateurs actuellement pris en charge par P2 à P1, l’administrateur doit effectuer les étapes suivantes : 
> <OL>
> <LI>
> <P>Échec sauvegarder tous les utilisateurs hébergés à l’origine de P1 de P2 à P1 à l’aide de l’applet de commande la restauration automatique. Dans ce cas, le *PoolFQDN* est P1 nom de domaine complet.</P>
> <LI>
> <P>Faire basculer toutes les utilisateurs hébergés à l’origine de P2 à P1 à l’aide de l’applet de commande de basculement. Dans ce cas, le PoolFQDN est P2 nom de domaine complet.</P>
> <LI>
> <P>Si l’administrateur souhaite ultérieurement à basculer les utilisateurs de P2 vers P2, le PoolFQDN est P2 nom de domaine complet.</P></LI></OL><br>Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool. Si vous essayez de l’étape 2 avant l’étape 1, l’applet de commande de l’étape 2 échoue.


## <a name="see-also"></a>Voir aussi

[Planifier la haute disponibilité et la récupération d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
