---
title: 'Lync Server 2013 : gestion de la prise d’appel de groupe lors de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a0abe6c64b0e6d5cba80c0adb6a01c5dbacb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0a5bc-102">Gestion de la prise d’appel de groupe lors de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a5bc-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a5bc-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0a5bc-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0a5bc-104">Lorsqu’un pool frontal devient indisponible en raison d’un incident non planifié, le service est basculé vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="0a5bc-105">Lors du basculement vers le pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et sont en mode résistance.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="0a5bc-106">En mode résistance, les utilisateurs ne peuvent pas reprendre les appels des autres utilisateurs ou avoir des appels pris par d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="0a5bc-107">Une fois le basculement terminé, les utilisateurs peuvent de nouveau utiliser la prise d’appel de groupe comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="0a5bc-108">Pendant la restauration automatique vers le pool principal, les utilisateurs sont redirigés vers le pool principal et resont en mode résilience.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="0a5bc-109">La fonctionnalité de prise d’appel de groupe n’est pas disponible tant que les utilisateurs ne sont pas en mode résistance.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="0a5bc-110">Cette section présente des considérations relatives à la prise d’appel de groupe lors de la récupération d’urgence et décrit également l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="0a5bc-111">Considérations relatives à la prise d’appel de groupe lors de la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="0a5bc-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="0a5bc-112">Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parcage d’appel en cours d’exécution dans le pool de sauvegarde pour les numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="0a5bc-113">Par conséquent, la prise en charge de la prise d’appel de groupe pendant la récupération d’urgence nécessite le déploiement et l’activation de l’application de parcage d’appel à la fois dans le pool principal et dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="0a5bc-114">Les plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel doivent être redirigées vers le pool de sauvegarde une fois le processus de basculement vers le pool de sauvegarde terminé.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="0a5bc-115">Les plages de numéros doivent être redirigées vers le pool principal une fois le processus de retour arrière vers le pool principal terminé.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="0a5bc-116">Pour rediriger les plages de prise d’appel de groupe, utilisez la cmdlet **Set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="0a5bc-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="0a5bc-117">Si vous déployez un nouveau pool avec un nom de domaine complet (FQDN) différent pour remplacer le pool principal, vous devez réaffecter toutes les plages de numéros de prise d’appel de groupe associées au pool principal au nom de domaine complet du nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="0a5bc-118">Pour réaffecter des plages de numéros au nouveau pool, vous pouvez utiliser la cmdlet **Set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="0a5bc-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="0a5bc-119">Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit** , voir [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="0a5bc-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="0a5bc-120">Expérience de prise d’appel de groupe en cas de défaillance du pool</span><span class="sxs-lookup"><span data-stu-id="0a5bc-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="0a5bc-121">Le tableau suivant résume l’expérience de prise d’appel de groupe par le biais des phases de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="0a5bc-122">Expérience utilisateur durant la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="0a5bc-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a5bc-123">État de l’appel</span><span class="sxs-lookup"><span data-stu-id="0a5bc-123">Call state</span></span></th>
<th><span data-ttu-id="0a5bc-124">Basculement vers le pool de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="0a5bc-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="0a5bc-125">Restauration automatique vers le pool principal</span><span class="sxs-lookup"><span data-stu-id="0a5bc-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a5bc-126">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="0a5bc-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="0a5bc-127"><strong>Lors du processus de basculement :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-128">La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résilience</span><span class="sxs-lookup"><span data-stu-id="0a5bc-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-129"><strong>Une fois le basculement terminé :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-130">Prise d’appel de groupe disponible lorsque les plages de numéros de prise d’appel de résilience et de groupe sont redirigées vers le pool de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="0a5bc-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0a5bc-131"><strong>Pendant le processus de restauration automatique :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-132">La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résilience</span><span class="sxs-lookup"><span data-stu-id="0a5bc-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-133"><strong>Une fois la restauration terminée :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-134">Prise d’appel de groupe disponible lorsque les plages de numéros de prise d’appel de résilience et de groupe sont redirigées vers le pool principal</span><span class="sxs-lookup"><span data-stu-id="0a5bc-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a5bc-135">Appels dans la file d’attente de prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="0a5bc-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="0a5bc-136"><strong>Lors du processus de basculement :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-137">Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-138"><strong>Une fois le basculement terminé :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-139">Aucun appel dans cet État</span><span class="sxs-lookup"><span data-stu-id="0a5bc-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0a5bc-140"><strong>Pendant le processus de restauration automatique :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-141">Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-142"><strong>Une fois la restauration terminée :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-143">Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="0a5bc-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a5bc-144">Appel établi</span><span class="sxs-lookup"><span data-stu-id="0a5bc-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="0a5bc-145"><strong>Lors du processus de basculement :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-146">Les appels restent connectés</span><span class="sxs-lookup"><span data-stu-id="0a5bc-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-147"><strong>Une fois le basculement terminé :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-148">Les appels restent connectés</span><span class="sxs-lookup"><span data-stu-id="0a5bc-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0a5bc-149"><strong>Pendant le processus de restauration automatique :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-150">Les appels restent connectés</span><span class="sxs-lookup"><span data-stu-id="0a5bc-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="0a5bc-151"><strong>Une fois la restauration terminée :</strong></span><span class="sxs-lookup"><span data-stu-id="0a5bc-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0a5bc-152">Les appels restent connectés</span><span class="sxs-lookup"><span data-stu-id="0a5bc-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

