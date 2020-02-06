---
title: Déployer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790122"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Déployer la haute disponibilité et la récupération d’urgence
 
Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL. 
  
La haute disponibilité désigne la disponibilité des services Skype entreprise Server même en cas de panne d’un ou de plusieurs serveurs. La reprise après sinistre fait référence au maintien de services en cas de sinistre naturel ou humain et de préservation de la quantité de données du désastre possible.
  
Cette section indique comment déployer ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.
  
## <a name="related-sections"></a>Sections connexes

[Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Voir aussi

[Déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype entreprise Server](alwayson-availability-group.md)

[Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server](front-end-pools-for-disaster-recovery.md)
  
[Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015](sql-mirroring-for-high-availability.md)
  
