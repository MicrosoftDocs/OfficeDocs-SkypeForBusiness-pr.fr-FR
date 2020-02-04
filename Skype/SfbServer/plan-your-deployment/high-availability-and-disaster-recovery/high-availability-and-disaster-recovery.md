---
title: Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL.
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695969"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server
 
Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL. 
  
La haute disponibilité désigne la disponibilité des services Skype entreprise Server même en cas de panne d’un ou de plusieurs serveurs. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Comme dans les versions précédentes de Lync Server, la principale fonctionnalité de haute disponibilité pour la plupart des rôles de serveur dans Skype entreprise Server est la redondance du serveur via le regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype entreprise Server fournit également des options de reprise après sinistre pour les pools front-end. Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre. Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.
  
Skype entreprise Server prend également en charge quatre modes de haute disponibilité pour votre serveur principal : la mise en miroir SQL, les groupes de disponibilité AlwaysOn, les instances de cluster de reprise AlwaysOn (ICF) et la mise en cluster de basculement SQL.
  
> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.

> [!NOTE]
> Les groupes de disponibilité AlwaysOn ne sont pas pris en charge par les serveurs de chat permanents. 
  
Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur. 
  
## <a name="see-also"></a>Voir aussi

[Haute disponibilité et gestion du pool frontal](high-availability.md)
  
[Reprise après sinistre de la liste frontale dans Skype entreprise Server](disaster-recovery.md)
  
[Utilisation de l’interface utilisateur en cas d’échec de la mise en réserve dans Skype entreprise Server](user-experience.md)
  
[Haute disponibilité du serveur principal dans Skype entreprise Server](back-end-server.md)
  
[Forte disponibilité du partage de fichiers dans Skype entreprise Server](file-sharing.md)
