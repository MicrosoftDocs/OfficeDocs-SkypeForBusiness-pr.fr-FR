---
title: Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype pour Business Server assure une disponibilité élevée avec serveur de regroupement, de reprise après sinistre avec un pool d’appariement et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et la gestion de clusters avec basculement SQL.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a>Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server 2015
 
Skype pour Business Server assure une disponibilité élevée avec serveur de regroupement, de reprise après sinistre avec un pool d’appariement et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et la gestion de clusters avec basculement SQL. 
  
Haute disponibilité fait référence à s’assurer que Skype pour services Business Server sont disponibles même si un ou plusieurs serveurs tombe en panne. La récupération d’urgence se réfère au fait de maintenir les services en activité même dans le cas d’une catastrophe naturelle ou causée par l’homme, et de préserver autant de données que possible.
  
Comme dans les versions précédentes de Lync Server, la fonctionnalité principale de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server est la redondance des serveurs via un regroupement de. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype pour Business Server fournit également pour les pools de Front-End, les options de récupération après sinistre. Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre. Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.
  
Skype pour Business Server prend également en charge quatre modes de haute disponibilité pour vos serveurs de fin précédente : la mise en miroir de base de données, groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn (FCI) et clustering avec basculement SQL.
  
> [!NOTE]
> Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec des serveurs de conversation permanent. 
  
Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Avant fin Pool à haute disponibilité et la gestion](high-availability.md)
  
[Avant la reprise de pool fin dans Skype pour Business Server 2015](disaster-recovery.md)
  
[Expérience de l’utilisateur lors de l’échec de pool dans Skype pour Business Server 2015](user-experience.md)
  
[Sauvegarder un serveur haute disponibilité dans Skype pour Business Server 2015](back-end-server.md)
  
[Partage de fichiers haute disponibilité dans Skype pour Business Server 2015](file-sharing.md)

