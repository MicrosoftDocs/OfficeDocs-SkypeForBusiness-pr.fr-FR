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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875256"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="c73dc-103">Planification de la haute disponibilité et récupération d’urgence dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="c73dc-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="c73dc-104">Skype pour Business Server offre une haute disponibilité avec le pool, la récupération d’urgence de jumelage des pools et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et le clustering de basculement SQL de serveur.</span><span class="sxs-lookup"><span data-stu-id="c73dc-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="c73dc-105">Haute disponibilité fait référence à s’assurer que Skype pour les services Business Server sont disponibles, même si un ou plusieurs serveurs tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="c73dc-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="c73dc-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="c73dc-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="c73dc-107">Comme dans les versions précédentes de Lync Server, la fonctionnalité principale de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server est la redondance des serveurs via un regroupement.</span><span class="sxs-lookup"><span data-stu-id="c73dc-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="c73dc-108">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="c73dc-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="c73dc-109">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="c73dc-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="c73dc-110">Skype pour Business Server fournit également des options de récupération pour les pools frontaux reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="c73dc-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="c73dc-111">Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre.</span><span class="sxs-lookup"><span data-stu-id="c73dc-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="c73dc-112">Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.</span><span class="sxs-lookup"><span data-stu-id="c73dc-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="c73dc-113">Skype pour Business Server prend également en charge quatre modes de haute disponibilité pour vos serveurs principaux : mise en miroir, les groupes de disponibilité AlwaysOn, les Instances de Cluster de basculement AlwaysOn (FCI) et le clustering avec basculement SQL SQL.</span><span class="sxs-lookup"><span data-stu-id="c73dc-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c73dc-114">La mise en miroir SQL est disponible dans Skype pour Business Server 2015 mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c73dc-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c73dc-115">Les méthodes de clustering avec basculement SQL, les Instances de Cluster de basculement AlwaysOn (FCI) et les groupes de disponibilité AlwaysOn sont préférés avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c73dc-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="c73dc-116">Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="c73dc-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="c73dc-117">Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="c73dc-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c73dc-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c73dc-118">See also</span></span>

[<span data-ttu-id="c73dc-119">Haute disponibilité et gestion du pool frontal</span><span class="sxs-lookup"><span data-stu-id="c73dc-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="c73dc-120">La récupération d’urgence dans Skype fin pool de serveurs frontaux pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c73dc-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="c73dc-121">Expérience utilisateur défaillance d’un pool dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c73dc-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="c73dc-122">Arrière serveur haute disponibilité dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c73dc-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="c73dc-123">Partage de fichiers haute disponibilité dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c73dc-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
