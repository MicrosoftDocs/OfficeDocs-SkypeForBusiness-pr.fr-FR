---
title: 'Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde'
ms.reviewer: null
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Découvrez les procédures relatives aux opérations de récupération d’urgence, ainsi que la maintenance du service de sauvegarde, qui synchronise les données dans des pools frontaux couplés.'
---


# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gestion Skype Entreprise Server récupération d’urgence, haute disponibilité et service de sauvegarde

Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour la maintenance du service de sauvegarde, qui synchronise les données dans des pools frontaux couplés.

Les procédures de récupération d’urgence, qu’il s’agisse du basculement ou de la restauration automatique, sont manuelles. En cas d’urgence, l’administrateur doit appeler manuellement les procédures de basculement. Il en est de même pour la restauration automatique, après la réparation du pool.

Les procédures de récupération d’urgence de cette section supposent les opérations suivantes :

  - Vous avez un déploiement avec des pools frontux couplés, situés sur différents sites, comme décrit dans Planifier la haute disponibilité et la récupération [d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). Le service de sauvegarde a été exécuté sur ces pools couplés pour maintenir leur synchronisation.

  - Si le magasin central de gestion est hébergé sur l’un ou l’autre des pools, il est installé et s’exécute sur les deux pools couplés, l’un de ces pools hébergeant le maître actif et l’autre pool hébergeant le pool de veille.

> [!IMPORTANT]
> Dans les procédures suivantes, le paramètre *PoolFQDN* se réfère au nom de domaine complet (FQDN) du pool affecté par la situation d’urgence et non pas le pool depuis lequel les utilisateurs affectés sont redirigés. Dans le cas d’un ensemble d’utilisateurs identique, le paramètre se réfère au même pool, dans les cmdlets de basculement et de récupération automatique (c’est-à-dire, le pool ayant hébergé les utilisateurs avant le basculement).<BR><br>Par exemple, supposons que tous les utilisateurs hébergés sur un pool P1 ont été basculés sur le pool de sauvegarde, P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement traités par les services de P2 pour qu’ils soient traités par les services de P1, l’administrateur doit procéder comme ceci : 
> <OL>
> <LI>
> <P>Il doit restaurer automatiquement tous les utilisateurs hébergés à l’origine sur P1 de P2 à P1 en utilisant la cmdlet de restauration automatique. Dans ce cas, le *PoolFQDN* est le nom de domaine complet (FQDN) de P1.</P>
> <LI>
> <P>Il doit ensuite basculer tous les utilisateurs hébergés à l’origine sur P2 vers P1 en utilisant la cmdlet de basculement. Dans ce cas, le PoolFQDN est le nom de domaine complet (FQDN) de P2.</P>
> <LI>
> <P>Si l’administrateur souhaite ultérieurement restaurer automatiquement les utilisateurs de P2 vers P2, le PoolFQDN est le nom de domaine complet FQDN de P2.</P></LI></OL><br>Remarquez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, la cmdlet de l’étape 2 ne fonctionnera pas.


## <a name="see-also"></a>Voir aussi

[Planifier la haute disponibilité et la récupération d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
