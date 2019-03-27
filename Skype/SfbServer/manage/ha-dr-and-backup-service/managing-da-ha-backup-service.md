---
title: Gestion de Service de sauvegarde, haute disponibilité et la récupération d’urgence
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez les procédures pour les opérations de récupération d’urgence, ainsi que pour gérer le Service de sauvegarde qui synchronise les données dans des pools frontaux couplés.
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892412"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="81d17-103">Gestion de Skype pour le Service de sauvegarde, haute disponibilité et la récupération d’urgence Business Server</span><span class="sxs-lookup"><span data-stu-id="81d17-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="81d17-104">Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour gérer le Service de sauvegarde qui synchronise les données dans des pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="81d17-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="81d17-105">Procédures de récupération d’urgence, le basculement et la restauration automatique, sont manuelles.</span><span class="sxs-lookup"><span data-stu-id="81d17-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="81d17-106">S’il existe une catastrophe, l’administrateur doit appeler manuellement les procédures de basculement.</span><span class="sxs-lookup"><span data-stu-id="81d17-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="81d17-107">Les mêmes s’applique à la restauration automatique une fois que le pool est réparé.</span><span class="sxs-lookup"><span data-stu-id="81d17-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="81d17-108">Les procédures de récupération d’urgence dans cette section supposent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="81d17-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="81d17-109">Vous disposez d’un déploiement avec des pools frontaux couplés, situés dans différents sites, comme décrit dans le [Plan de haute disponibilité et récupération d’urgence](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="81d17-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="81d17-110">Le Service de sauvegarde a été exécuté sur ces pools associés pour qu’elles soient synchronisées.</span><span class="sxs-lookup"><span data-stu-id="81d17-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="81d17-111">Si le magasin Central de gestion est hébergé sur un pool, il est installé et en cours d’exécution sur les deux pools associés, avec un de ces pools hébergeant le contrôleur actif et l’autre pool hébergeant la mise en veille.</span><span class="sxs-lookup"><span data-stu-id="81d17-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81d17-112">Dans les procédures suivantes, le paramètre *PoolFQDN* désigne le nom de domaine complet du pool qui est affecté par la reprise après sinistre, pas le pool qui ont affecté les utilisateurs sont redirigés à partir de.</span><span class="sxs-lookup"><span data-stu-id="81d17-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="81d17-113">Pour le même ensemble d’utilisateurs affectés, il fait référence au même pool dans le basculement et la restauration des applets de commande (autrement dit, le pool hébergé tout d’abord les utilisateurs avant le basculement).</span><span class="sxs-lookup"><span data-stu-id="81d17-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="81d17-114">Par exemple, supposons un cas dans lequel tous les utilisateurs hébergement sur un pool P1 ont été basculés vers le pool de sauvegarde, P2.</span><span class="sxs-lookup"><span data-stu-id="81d17-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="81d17-115">Si l’administrateur souhaite déplacer tous les utilisateurs actuellement pris en charge par P2 à P1, l’administrateur doit effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="81d17-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="81d17-116">Échec sauvegarder tous les utilisateurs hébergés à l’origine de P1 de P2 à P1 à l’aide de l’applet de commande la restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="81d17-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="81d17-117">Dans ce cas, le *PoolFQDN* est P1 nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="81d17-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="81d17-118">Faire basculer toutes les utilisateurs hébergés à l’origine de P2 à P1 à l’aide de l’applet de commande de basculement.</span><span class="sxs-lookup"><span data-stu-id="81d17-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="81d17-119">Dans ce cas, le PoolFQDN est P2 nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="81d17-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="81d17-120">Si l’administrateur souhaite ultérieurement à basculer les utilisateurs de P2 vers P2, le PoolFQDN est P2 nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="81d17-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="81d17-121">Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool.</span><span class="sxs-lookup"><span data-stu-id="81d17-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="81d17-122">Si vous essayez de l’étape 2 avant l’étape 1, l’applet de commande de l’étape 2 échoue.</span><span class="sxs-lookup"><span data-stu-id="81d17-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="81d17-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81d17-123">See Also</span></span>

[<span data-ttu-id="81d17-124">Planifier la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="81d17-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
