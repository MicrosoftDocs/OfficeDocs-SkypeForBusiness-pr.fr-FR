---
title: Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype pour Business Server assure une disponibilité élevée avec serveur de regroupement, de reprise après sinistre avec un pool d’appariement et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et la gestion de clusters avec basculement SQL.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="368ef-103">Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="368ef-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="368ef-104">Skype pour Business Server assure une disponibilité élevée avec serveur de regroupement, de reprise après sinistre avec un pool d’appariement et plusieurs modes de haute disponibilité du serveur principal, y compris les groupes de disponibilité AlwaysOn, la mise en miroir de base de données et la gestion de clusters avec basculement SQL.</span><span class="sxs-lookup"><span data-stu-id="368ef-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="368ef-105">Haute disponibilité fait référence à s’assurer que Skype pour services Business Server sont disponibles même si un ou plusieurs serveurs tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="368ef-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="368ef-106">La récupération d’urgence se réfère au fait de maintenir les services en activité même dans le cas d’une catastrophe naturelle ou causée par l’homme, et de préserver autant de données que possible.</span><span class="sxs-lookup"><span data-stu-id="368ef-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="368ef-107">Comme dans les versions précédentes de Lync Server, la fonctionnalité principale de haute disponibilité pour la plupart des rôles de serveur dans Skype pour Business Server est la redondance des serveurs via un regroupement de.</span><span class="sxs-lookup"><span data-stu-id="368ef-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="368ef-108">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="368ef-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="368ef-109">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="368ef-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="368ef-110">Skype pour Business Server fournit également pour les pools de Front-End, les options de récupération après sinistre.</span><span class="sxs-lookup"><span data-stu-id="368ef-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="368ef-111">Vous pouvez configurer deux pools dans des zones géographiques différentes qui jouent le rôle de sauvegardes l’un pour l’autre.</span><span class="sxs-lookup"><span data-stu-id="368ef-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="368ef-112">Ainsi, en cas de panne d’un pool ou d’un site, le pool de sauvegarde continue à fournir un service aux utilisateurs des deux sites.</span><span class="sxs-lookup"><span data-stu-id="368ef-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="368ef-113">Skype pour Business Server prend également en charge quatre modes de haute disponibilité pour vos serveurs de fin précédente : la mise en miroir de base de données, groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn (FCI) et clustering avec basculement SQL.</span><span class="sxs-lookup"><span data-stu-id="368ef-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="368ef-114">Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec des serveurs de conversation permanent.</span><span class="sxs-lookup"><span data-stu-id="368ef-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="368ef-115">Cette section décrit en détail ces fonctionnalités et aborde également les mesures que vous pouvez prendre dans le cadre de la haute disponibilité et de la récupération d’urgence pour certains autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="368ef-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="368ef-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="368ef-116">See also</span></span>

#### 

[<span data-ttu-id="368ef-117">Avant fin Pool à haute disponibilité et la gestion</span><span class="sxs-lookup"><span data-stu-id="368ef-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="368ef-118">Avant la reprise de pool fin dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="368ef-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="368ef-119">Expérience de l’utilisateur lors de l’échec de pool dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="368ef-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="368ef-120">Sauvegarder un serveur haute disponibilité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="368ef-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="368ef-121">Partage de fichiers haute disponibilité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="368ef-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

