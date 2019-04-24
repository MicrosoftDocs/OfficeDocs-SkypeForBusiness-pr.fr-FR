---
title: Planification de la haute disponibilité et récupération d’urgence dans Skype Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype pour Business Server offre une haute disponibilité avec le pool, la récupération d’urgence de jumelage des pools et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et le clustering de basculement SQL de serveur.
ms.openlocfilehash: 9e48fa65572dea5c0e6a297397d2a502cefcdc36
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214060"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planification de la haute disponibilité et récupération d’urgence dans Skype Business Server
 
Skype pour Business Server offre une haute disponibilité avec le pool, la récupération d’urgence de jumelage des pools et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et le clustering de basculement SQL de serveur. 
  
Haute disponibilité fait référence à s’assurer que Skype pour les services Business Server sont disponibles, même si un ou plusieurs serveurs tombe en panne. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Comme dans les versions précédentes de Lync Server, la fonctionnalité principale de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server est la redondance des serveurs via un regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype pour Business Server fournit également des options de récupération pour les pools frontaux reprise après sinistre. Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre. Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.
  
Skype pour Business Server prend également en charge quatre modes de haute disponibilité pour vos serveurs principaux : mise en miroir, les groupes de disponibilité AlwaysOn, les Instances de Cluster de basculement AlwaysOn (FCI) et le clustering avec basculement SQL SQL.
  
> [!NOTE]
> La mise en miroir SQL est disponible dans Skype pour Business Server 2015 mais n’est plus pris en charge dans Skype pour Business Server 2019. Les méthodes de clustering avec basculement SQL, les Instances de Cluster de basculement AlwaysOn (FCI) et les groupes de disponibilité AlwaysOn sont préférés avec Skype pour Business Server 2019.

> [!NOTE]
> Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente. 
  
Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur. 
  
## <a name="see-also"></a>Voir aussi

[Haute disponibilité et gestion du pool frontal](high-availability.md)
  
[La récupération d’urgence dans Skype fin pool de serveurs frontaux pour Business Server](disaster-recovery.md)
  
[Expérience utilisateur défaillance d’un pool dans Skype pour Business Server](user-experience.md)
  
[Arrière serveur haute disponibilité dans Skype pour Business Server](back-end-server.md)
  
[Partage de fichiers haute disponibilité dans Skype pour Business Server](file-sharing.md)
