---
title: Gestion de la reprise après sinistre, haute disponibilité et service de sauvegarde
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Apprenez-en davantage sur les procédures d’opérations de récupération d’urgence, ainsi que pour la gestion du service de sauvegarde, qui synchronise les données dans des listes frontales couplées.
ms.openlocfilehash: bb8178b98d355159a92d7187884e5502912f4436
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818335"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="7cf33-103">Gestion de la reprise après sinistre de Skype entreprise Server, haute disponibilité et service de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="7cf33-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="7cf33-104">Cette section contient des procédures pour les opérations de reprise après sinistre, ainsi que pour la gestion du service de sauvegarde, qui synchronise les données dans des listes frontales couplées.</span><span class="sxs-lookup"><span data-stu-id="7cf33-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="7cf33-105">Les procédures de reprise après sinistre, à la fois de basculement et de restauration automatique, sont manuelles.</span><span class="sxs-lookup"><span data-stu-id="7cf33-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="7cf33-106">En cas de sinistre, l’administrateur doit appeler manuellement les procédures de basculement.</span><span class="sxs-lookup"><span data-stu-id="7cf33-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="7cf33-107">Il en va de même pour la restauration après la réparation du pool.</span><span class="sxs-lookup"><span data-stu-id="7cf33-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="7cf33-108">Les procédures de reprise après sinistre dans cette section sont supposées comme suit :</span><span class="sxs-lookup"><span data-stu-id="7cf33-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="7cf33-109">Vous disposez d’un déploiement avec des plages frontales couplées dans les différents sites, comme décrit dans la section [planifier une disponibilité élevée et une reprise après sinistre](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7cf33-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="7cf33-110">Le service de sauvegarde est en cours d’exécution sur ces pools couplés pour qu’ils soient synchronisés.</span><span class="sxs-lookup"><span data-stu-id="7cf33-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="7cf33-111">Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et en cours d’exécution sur les deux pools couplés, avec l’un de ces pools hébergeant la forme de base active et l’autre réserve hébergeant la réserve.</span><span class="sxs-lookup"><span data-stu-id="7cf33-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cf33-112">Dans les procédures suivantes, le paramètre *PoolFQDN* fait référence au nom de domaine complet (FQDN) du pool affecté par un sinistre, et non à partir du pool sur lequel les utilisateurs concernés sont redirigés.</span><span class="sxs-lookup"><span data-stu-id="7cf33-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="7cf33-113">Pour le même ensemble d’utilisateurs concernés, il fait référence au même pool dans les applets de service de basculement et de restauration automatique (autrement dit, le pool qui a d’abord hébergé les utilisateurs avant le basculement).</span><span class="sxs-lookup"><span data-stu-id="7cf33-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="7cf33-114">Par exemple, supposons que l’ensemble des utilisateurs hébergés sur un pool P1 aient pu basculer vers le pool de sauvegardes P2.</span><span class="sxs-lookup"><span data-stu-id="7cf33-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="7cf33-115">Si l’administrateur veut déplacer tous les utilisateurs actuellement desservis par P2 pour être desservi par P1, l’administrateur doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="7cf33-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="7cf33-116">Basculez vers la page d’accueil de tous les utilisateurs à l’origine de l’appel P1 sur P1 à l’aide de l’applet de la cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="7cf33-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="7cf33-117">Dans le cas présent, le *PoolFQDN* est P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="7cf33-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="7cf33-118">Faire basculer tous les utilisateurs de la page d’origine de la page de base sur l’applet de contrôle</span><span class="sxs-lookup"><span data-stu-id="7cf33-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="7cf33-119">Dans le cas présent, le PoolFQDN est P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="7cf33-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="7cf33-120">Si l’administrateur souhaite plus tard régulariser les utilisateurs de P2, le PoolFQDN est P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="7cf33-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="7cf33-121">Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 de conservation de l’intégrité du pool.</span><span class="sxs-lookup"><span data-stu-id="7cf33-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="7cf33-122">Si vous essayez l’étape 2 avant l’étape 1, l’applet de la cmdlet Step 2 ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="7cf33-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="7cf33-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7cf33-123">See Also</span></span>

[<span data-ttu-id="7cf33-124">Planifier la haute disponibilité et la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="7cf33-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
