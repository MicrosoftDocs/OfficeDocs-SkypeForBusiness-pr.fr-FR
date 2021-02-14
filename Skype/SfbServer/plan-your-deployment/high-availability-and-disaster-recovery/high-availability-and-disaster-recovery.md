---
title: Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802814"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="a7292-103">Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7292-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="a7292-104">Skype Entreprise Server offre une haute disponibilité avec la mise en pool de serveurs, la récupération d’urgence avec le jumelage de pool et plusieurs modes de haute disponibilité du serveur principal, notamment les groupes de disponibilité AlwaysOn, la mise en miroir de bases de données et le clustering de SQL.</span><span class="sxs-lookup"><span data-stu-id="a7292-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="a7292-105">La haute disponibilité fait référence à la mise à disposition des services Skype Entreprise Server même si un ou plusieurs serveurs sont en panne.</span><span class="sxs-lookup"><span data-stu-id="a7292-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="a7292-106">La récupération d’urgence fait référence au maintien des services en cours en cas d’urgence naturelle ou humaine, et à la conservation de la plus grande quantité de données possible avant la catastrophe.</span><span class="sxs-lookup"><span data-stu-id="a7292-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="a7292-107">Comme dans les versions précédentes de Lync Server, la fonctionnalité de haute disponibilité principale pour la plupart des rôles serveur dans Skype Entreprise Server est la redondance des serveurs via la mise en pool.</span><span class="sxs-lookup"><span data-stu-id="a7292-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="a7292-108">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="a7292-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a7292-109">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="a7292-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="a7292-110">Skype Entreprise Server fournit également des options de récupération d’urgence pour les pools frontux.</span><span class="sxs-lookup"><span data-stu-id="a7292-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="a7292-111">Vous pouvez configurer deux pools dans différentes zones géographiques pour qu’ils servent de sauvegardes l’un pour l’autre.</span><span class="sxs-lookup"><span data-stu-id="a7292-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="a7292-112">Ensuite, si l’intégralité d’un pool ou d’un site est en panne, le pool de sauvegarde peut continuer à fournir un service aux utilisateurs des deux sites.</span><span class="sxs-lookup"><span data-stu-id="a7292-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="a7292-113">Skype Entreprise Server prend également en charge quatre modes de haute disponibilité pour vos serveurs principaux : la mise en miroir SQL, les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et le clustering de SQL.</span><span class="sxs-lookup"><span data-stu-id="a7292-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7292-114">SQL miroir est disponible dans Skype Entreprise Server 2015, mais n’est plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a7292-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a7292-115">Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a7292-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="a7292-116">Les groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="a7292-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="a7292-117">Cette section explique ces fonctionnalités et explique également les étapes que vous pouvez suivre pour la haute disponibilité et la récupération d’urgence pour certains de vos autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="a7292-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a7292-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7292-118">See also</span></span>

[<span data-ttu-id="a7292-119">Haute disponibilité et gestion du pool frontal</span><span class="sxs-lookup"><span data-stu-id="a7292-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="a7292-120">Récupération d’urgence du pool frontal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7292-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="a7292-121">Expérience utilisateur en cas de défaillance d’un pool dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7292-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="a7292-122">Haute disponibilité du serveur principal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7292-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="a7292-123">Haute disponibilité du partage de fichiers dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7292-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
