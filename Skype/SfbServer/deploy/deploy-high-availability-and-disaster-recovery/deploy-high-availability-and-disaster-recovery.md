---
title: Déployer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830614"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Déployer la haute disponibilité et la récupération d’urgence
 
Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL. 
  
La haute disponibilité fait référence à la mise à disposition des services Skype Entreprise Server même si un ou plusieurs serveurs sont en panne. La récupération d’urgence fait référence au maintien des services en cours en cas d’urgence naturelle ou humaine, et à la conservation de la plus grande quantité de données possible avant la catastrophe.
  
Cette section explique comment déployer ces fonctionnalités et explique également les étapes que vous pouvez suivre pour la haute disponibilité et la récupération d’urgence pour certains de vos autres rôles serveur.

> [!NOTE]
> SQL miroir est disponible dans Skype Entreprise Server 2015, mais n’est plus pris en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.
  
## <a name="related-sections"></a>Sections connexes

[Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Voir aussi

[Déployer un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype Entreprise Server](alwayson-availability-group.md)

[Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server](front-end-pools-for-disaster-recovery.md)
  
[Déployer SQL miroir pour la haute disponibilité du serveur principal dans Skype Entreprise Server 2015](sql-mirroring-for-high-availability.md)
  
