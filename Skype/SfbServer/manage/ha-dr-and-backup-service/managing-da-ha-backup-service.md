---
title: Gestion de la reprise après sinistre, haute disponibilité et service de sauvegarde
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Apprenez-en davantage sur les procédures d’opérations de récupération d’urgence, ainsi que pour la gestion du service de sauvegarde, qui synchronise les données dans des listes frontales couplées.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303897"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gestion de la reprise après sinistre de Skype entreprise Server, haute disponibilité et service de sauvegarde

Cette section contient des procédures pour les opérations de reprise après sinistre, ainsi que pour la gestion du service de sauvegarde, qui synchronise les données dans des listes frontales couplées.

Les procédures de reprise après sinistre, à la fois de basculement et de restauration automatique, sont manuelles. En cas de sinistre, l’administrateur doit appeler manuellement les procédures de basculement. Il en va de même pour la restauration après la réparation du pool.

Les procédures de reprise après sinistre dans cette section sont supposées comme suit:

  - Vous disposez d’un déploiement avec des plages frontales couplées dans les différents sites, comme décrit dans la section [planifier une disponibilité élevée et une reprise après sinistre](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). Le service de sauvegarde est en cours d’exécution sur ces pools couplés pour qu’ils soient synchronisés.

  - Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et en cours d’exécution sur les deux pools couplés, avec l’un de ces pools hébergeant la forme de base active et l’autre réserve hébergeant la réserve.

> [!IMPORTANT]
> Dans les procédures suivantes, le paramètre *PoolFQDN* fait référence au nom de domaine complet (FQDN) du pool affecté par un sinistre, et non à partir du pool sur lequel les utilisateurs concernés sont redirigés. Pour le même ensemble d’utilisateurs concernés, il fait référence au même pool dans les applets de service de basculement et de restauration automatique (autrement dit, le pool qui a d’abord hébergé les utilisateurs avant le basculement).<BR><br>Par exemple, supposons que l’ensemble des utilisateurs hébergés sur un pool P1 aient pu basculer vers le pool de sauvegardes P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement desservis par P2 pour être desservi par P1, l’administrateur doit procéder comme suit: 
> <OL>
> <LI>
> <P>Basculez vers la page d’accueil de tous les utilisateurs à l’origine de l’appel P1 sur P1 à l’aide de l’applet de la cmdlet failback. Dans le cas présent, le *PoolFQDN* est P1's FQDN.</P>
> <LI>
> <P>Faire basculer tous les utilisateurs de la page d’origine de la page de base sur l’applet de contrôle Dans le cas présent, le PoolFQDN est P2's FQDN.</P>
> <LI>
> <P>Si l’administrateur souhaite plus tard régulariser les utilisateurs de P2, le PoolFQDN est P2's FQDN.</P></LI></OL><br>Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 de conservation de l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, l’applet de la cmdlet Step 2 ne fonctionne pas.


## <a name="see-also"></a>Voir aussi

[Planifier la haute disponibilité et la récupération d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
