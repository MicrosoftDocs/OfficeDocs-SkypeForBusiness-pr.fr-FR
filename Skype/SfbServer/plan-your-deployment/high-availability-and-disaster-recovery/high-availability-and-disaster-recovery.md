---
title: Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données.
ms.openlocfilehash: f9834c52a563282afe6db6ce91cf7e5fa0456480
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756511"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server
 
Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données. 
  
La haute disponibilité permet de s’assurer que Skype Entreprise Server services sont disponibles même si un ou plusieurs serveurs sont en panne. La récupération d’urgence fait référence au maintien des services en cours en cas d’urgence naturelle ou humaine et à la conservation de la plus grande quantité de données possible avant la catastrophe.
  
Comme dans les versions précédentes de Lync Server, la fonctionnalité de haute disponibilité principale pour la plupart des rôles serveur dans Skype Entreprise Server est la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype Entreprise Server également des options de récupération d’urgence pour les pools frontux. Vous pouvez configurer deux pools dans différentes zones géographiques pour qu’ils servent de sauvegardes l’un pour l’autre. Ensuite, si l’intégralité d’un pool ou d’un site est en panne, le pool de sauvegarde peut continuer à fournir un service aux utilisateurs des deux sites.
  
Skype Entreprise Server prend également en charge quatre modes de haute disponibilité pour vos serveurs principaux : la mise en miroir SQL, les groupes de disponibilité AlwaysOn, les instances de cluster de point de SQL AlwaysOn et le clustering de SQL.
  
> [!NOTE]
> SQL La mise en miroir est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.

> [!NOTE]
> Les groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente. 
  
Cette section explique ces fonctionnalités et explique également les étapes que vous pouvez suivre pour la haute disponibilité et la récupération d’urgence pour certains de vos autres rôles serveur. 
  
## <a name="see-also"></a>Voir aussi

[Haute disponibilité et gestion du pool frontal](high-availability.md)
  
[Récupération d’urgence du pool frontal dans Skype Entreprise Server](disaster-recovery.md)
  
[Expérience utilisateur lors de la défaillance d’un pool Skype Entreprise Server](user-experience.md)
  
[Haute disponibilité du serveur principal dans Skype Entreprise Server](back-end-server.md)
  
[Haute disponibilité du partage de fichiers dans Skype Entreprise Server](file-sharing.md)
