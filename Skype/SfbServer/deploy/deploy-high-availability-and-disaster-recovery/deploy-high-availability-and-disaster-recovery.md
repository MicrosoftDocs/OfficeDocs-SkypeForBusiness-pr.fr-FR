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
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="24dda-103">Déployer la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="24dda-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="24dda-104">Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL.</span><span class="sxs-lookup"><span data-stu-id="24dda-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="24dda-105">La haute disponibilité désigne la disponibilité des services Skype entreprise Server même en cas de panne d’un ou de plusieurs serveurs. La reprise après sinistre fait référence au maintien de services en cas de sinistre naturel ou humain et de préservation de la quantité de données du désastre possible.</span><span class="sxs-lookup"><span data-stu-id="24dda-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="24dda-106">Cette section indique comment déployer ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="24dda-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="24dda-107">La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24dda-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="24dda-108">Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24dda-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="24dda-109">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="24dda-109">Related sections</span></span>

[<span data-ttu-id="24dda-110">Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="24dda-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="24dda-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24dda-111">See also</span></span>

[<span data-ttu-id="24dda-112">Déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="24dda-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="24dda-113">Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="24dda-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="24dda-114">Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="24dda-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
