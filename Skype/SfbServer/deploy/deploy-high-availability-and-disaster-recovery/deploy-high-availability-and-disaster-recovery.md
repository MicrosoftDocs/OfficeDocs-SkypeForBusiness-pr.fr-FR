---
title: Déployer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données.
ms.openlocfilehash: df77652840c127e011042172f618eba37d916f85
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394322"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Déployer la haute disponibilité et la récupération d’urgence
 
Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données. 
  
La haute disponibilité permet de s’assurer que Skype Entreprise Server services sont disponibles même si un ou plusieurs serveurs sont en panne. La récupération d’urgence fait référence au maintien des services en cours en cas d’urgence naturelle ou humaine, et à la conservation de la plus grande quantité de données possible avant la catastrophe.
  
Cette section explique comment déployer ces fonctionnalités et explique également les étapes que vous pouvez suivre pour la haute disponibilité et la récupération d’urgence pour certains de vos autres rôles serveur.

> [!NOTE]
> SQL miroir est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.
  
## <a name="related-sections"></a>Sections connexes

[Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Voir aussi

[Déployer un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype Entreprise Server](alwayson-availability-group.md)

[Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server](front-end-pools-for-disaster-recovery.md)
  
[Déployer SQL mise en miroir pour la haute disponibilité du serveur principal dans Skype Entreprise Server 2015](sql-mirroring-for-high-availability.md)
  
