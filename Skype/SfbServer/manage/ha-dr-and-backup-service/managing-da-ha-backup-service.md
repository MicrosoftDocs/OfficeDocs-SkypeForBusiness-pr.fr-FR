---
title: Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Découvrez les procédures relatives aux opérations de récupération d’urgence, ainsi que la maintenance du service de sauvegarde, qui synchronise les données dans des pools frontaux couplés.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817154"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="6e1d6-103">Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6e1d6-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="6e1d6-104">Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour la maintenance du service de sauvegarde, qui synchronise les données dans des pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="6e1d6-p101">Les procédures de récupération d’urgence, qu’il s’agisse du basculement ou de la restauration automatique, sont manuelles. En cas d’urgence, l’administrateur doit appeler manuellement les procédures de basculement. Il en est de même pour la restauration automatique, après la réparation du pool.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="6e1d6-108">Les procédures de récupération d’urgence de cette section supposent les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e1d6-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="6e1d6-109">Vous avez un déploiement avec des pools frontux couplés, situés dans différents sites, comme décrit dans Planifier la haute disponibilité et la récupération [d’urgence.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6e1d6-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="6e1d6-110">Le service de sauvegarde a été exécuté sur ces pools couplés pour maintenir leur synchronisation.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="6e1d6-111">Si le magasin central de gestion est hébergé sur l’un ou l’autre des pools, il est installé et s’exécute sur les deux pools couplés, l’un de ces pools hébergeant le maître actif et l’autre pool hébergeant le pool de veille.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e1d6-p103">Dans les procédures suivantes, le paramètre *PoolFQDN* se réfère au nom de domaine complet (FQDN) du pool affecté par la situation d’urgence et non pas le pool depuis lequel les utilisateurs affectés sont redirigés. Dans le cas d’un ensemble d’utilisateurs identique, le paramètre se réfère au même pool, dans les cmdlets de basculement et de récupération automatique (c’est-à-dire, le pool ayant hébergé les utilisateurs avant le basculement).</span><span class="sxs-lookup"><span data-stu-id="6e1d6-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="6e1d6-p104">Par exemple, supposons que tous les utilisateurs hébergés sur un pool P1 ont été basculés sur le pool de sauvegarde, P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement traités par les services de P2 pour qu’ils soient traités par les services de P1, l’administrateur doit procéder comme ceci :</span><span class="sxs-lookup"><span data-stu-id="6e1d6-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6e1d6-p105">Il doit restaurer automatiquement tous les utilisateurs hébergés à l’origine sur P1 de P2 à P1 en utilisant la cmdlet de restauration automatique. Dans ce cas, le *PoolFQDN* est le nom de domaine complet (FQDN) de P1.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6e1d6-118">Il doit ensuite basculer tous les utilisateurs hébergés à l’origine sur P2 vers P1 en utilisant la cmdlet de basculement.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="6e1d6-119">Dans ce cas, le PoolFQDN est le nom de domaine complet (FQDN) de P2.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6e1d6-120">Si l’administrateur souhaite ultérieurement restaurer automatiquement les utilisateurs de P2 vers P2, le PoolFQDN est le nom de domaine complet FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="6e1d6-p107">Remarquez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, la cmdlet de l’étape 2 ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="6e1d6-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="6e1d6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e1d6-123">See Also</span></span>

[<span data-ttu-id="6e1d6-124">Planifier la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="6e1d6-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
