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
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="e296d-103">Déployer la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="e296d-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="e296d-104">Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL.</span><span class="sxs-lookup"><span data-stu-id="e296d-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="e296d-105">La haute disponibilité fait référence à la mise à disposition des services Skype Entreprise Server même si un ou plusieurs serveurs sont en panne. La récupération d’urgence fait référence au maintien des services en cours en cas d’urgence naturelle ou humaine, et à la conservation de la plus grande quantité de données possible avant la catastrophe.</span><span class="sxs-lookup"><span data-stu-id="e296d-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="e296d-106">Cette section explique comment déployer ces fonctionnalités et explique également les étapes que vous pouvez suivre pour la haute disponibilité et la récupération d’urgence pour certains de vos autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="e296d-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="e296d-107">SQL miroir est disponible dans Skype Entreprise Server 2015, mais n’est plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e296d-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e296d-108">Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e296d-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="e296d-109">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="e296d-109">Related sections</span></span>

[<span data-ttu-id="e296d-110">Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e296d-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="e296d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e296d-111">See also</span></span>

[<span data-ttu-id="e296d-112">Déployer un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e296d-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="e296d-113">Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e296d-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="e296d-114">Déployer SQL miroir pour la haute disponibilité du serveur principal dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e296d-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
