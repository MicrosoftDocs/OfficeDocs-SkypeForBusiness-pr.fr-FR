---
title: Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815922"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="cacce-103">Prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cacce-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="cacce-104">Skype entreprise Server offre une grande disponibilité grâce à la mise en pool de serveurs, une reprise après sinistre avec le jumelage de pools, ainsi que plusieurs modes de haute disponibilité du serveur principal, y compris les groupes d’attribution de la base de données, la mise en miroir de la base de données et le basculement SQL.</span><span class="sxs-lookup"><span data-stu-id="cacce-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="cacce-105">La haute disponibilité désigne la disponibilité des services Skype entreprise Server même en cas de panne d’un ou de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="cacce-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="cacce-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="cacce-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="cacce-107">Comme dans les versions précédentes de Lync Server, la principale fonctionnalité de haute disponibilité pour la plupart des rôles de serveur dans Skype entreprise Server est la redondance du serveur via le regroupement.</span><span class="sxs-lookup"><span data-stu-id="cacce-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="cacce-108">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="cacce-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="cacce-109">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="cacce-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="cacce-110">Skype entreprise Server fournit également des options de reprise après sinistre pour les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="cacce-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="cacce-111">Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre.</span><span class="sxs-lookup"><span data-stu-id="cacce-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="cacce-112">Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.</span><span class="sxs-lookup"><span data-stu-id="cacce-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="cacce-113">Skype entreprise Server prend également en charge quatre modes de haute disponibilité pour votre serveur principal : la mise en miroir SQL, les groupes de disponibilité AlwaysOn, les instances de cluster de reprise AlwaysOn (ICF) et la mise en cluster de basculement SQL.</span><span class="sxs-lookup"><span data-stu-id="cacce-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cacce-114">La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cacce-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cacce-115">Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cacce-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="cacce-116">Les groupes de disponibilité AlwaysOn ne sont pas pris en charge par les serveurs de chat permanents.</span><span class="sxs-lookup"><span data-stu-id="cacce-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="cacce-117">Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="cacce-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cacce-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cacce-118">See also</span></span>

[<span data-ttu-id="cacce-119">Haute disponibilité et gestion du pool frontal</span><span class="sxs-lookup"><span data-stu-id="cacce-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="cacce-120">Reprise après sinistre de la liste frontale dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cacce-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="cacce-121">Utilisation de l’interface utilisateur en cas d’échec de la mise en réserve dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cacce-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="cacce-122">Haute disponibilité du serveur principal dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cacce-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="cacce-123">Forte disponibilité du partage de fichiers dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cacce-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
