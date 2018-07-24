---
title: Déployer la haute disponibilité et la récupération d’urgence
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype pour Business Server offre une haute disponibilité avec le pool, la récupération d’urgence de jumelage des pools et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et le clustering de basculement SQL de serveur.
ms.openlocfilehash: c3741527b83634d8a3571daa2623af55806e7f19
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993598"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="50d15-103">Déployer la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="50d15-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="50d15-104">Skype pour Business Server offre une haute disponibilité avec le pool, la récupération d’urgence de jumelage des pools et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et le clustering de basculement SQL de serveur.</span><span class="sxs-lookup"><span data-stu-id="50d15-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="50d15-105">Haute disponibilité fait référence à s’assurer que Skype pour les services Business Server sont disponibles, même si un ou plusieurs serveurs tombe en panne. Récupération d’urgence fait référence à des services de conservation accédant en cas d’incident physique ou a provoqué l’homme et conserver autant de données à partir d’avant la reprise après sinistre que possible.</span><span class="sxs-lookup"><span data-stu-id="50d15-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="50d15-106">Cette section indique comment déployer ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="50d15-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="50d15-107">La mise en miroir SQL est disponible dans Skype pour Business Server 2015 mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="50d15-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="50d15-108">Les méthodes de clustering avec basculement SQL, les Instances de Cluster de basculement AlwaysOn (FCI) et les groupes de disponibilité AlwaysOn sont préférés avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="50d15-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="50d15-109">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="50d15-109">Related sections</span></span>

[<span data-ttu-id="50d15-110">Planification de la haute disponibilité et récupération d’urgence dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="50d15-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="50d15-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50d15-111">See also</span></span>

[<span data-ttu-id="50d15-112">Déployer un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="50d15-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="50d15-113">Déployer les pools frontaux couplés pour la récupération d’urgence dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="50d15-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="50d15-114">Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="50d15-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
