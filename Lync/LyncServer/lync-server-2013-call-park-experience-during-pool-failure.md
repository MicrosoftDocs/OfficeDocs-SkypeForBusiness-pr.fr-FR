---
title: 'Lync Server 2013 : Expérience de parcage d’appel en cas de défaillance d’un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="46cea-102">Expérience de parcage d’appel dans Lync Server 2013 en cas de défaillance d’un pool</span><span class="sxs-lookup"><span data-stu-id="46cea-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46cea-103">_**Dernière modification de la rubrique:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="46cea-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="46cea-104">Lorsqu’un pool frontal devient indisponible en raison d’un incident imprévu, les appels qui ont été emportés mais qui ne sont pas encore récupérés sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="46cea-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="46cea-105">Pendant le basculement vers un pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et sont en mode de résilience.</span><span class="sxs-lookup"><span data-stu-id="46cea-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="46cea-106">Lorsque le mode de résilience est activé, les utilisateurs ne peuvent pas parcr les appels, mais ils peuvent placer des appels en attente et les transférer.</span><span class="sxs-lookup"><span data-stu-id="46cea-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="46cea-107">Lorsque le basculement est terminé, les appels peuvent être de nouveau au parking et extraits comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="46cea-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="46cea-108">Pendant la restauration automatique, les utilisateurs ne peuvent pas parcr les appels tant qu’ils ne sont pas en mode de résilience.</span><span class="sxs-lookup"><span data-stu-id="46cea-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="46cea-109">Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parc d’appels qui est déployée dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="46cea-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="46cea-110">C’est pourquoi les utilisateurs qui sont redirigés vers le pool de sauvegarde utilisent les paramètres de parc d’appels configurés pour l’application de parc d’appels dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="46cea-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="46cea-111">Le tableau suivant récapitule le parc d’appels lors de la phase de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="46cea-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="46cea-112">Utilisation de l’utilisateur pendant une reprise après sinistre</span><span class="sxs-lookup"><span data-stu-id="46cea-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46cea-113">État de l’appel</span><span class="sxs-lookup"><span data-stu-id="46cea-113">Call state</span></span></th>
<th><span data-ttu-id="46cea-114">Lorsque la panne se produit</span><span class="sxs-lookup"><span data-stu-id="46cea-114">When outage occurs</span></span></th>
<th><span data-ttu-id="46cea-115">Lors du basculement</span><span class="sxs-lookup"><span data-stu-id="46cea-115">During failover</span></span></th>
<th><span data-ttu-id="46cea-116">Durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="46cea-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46cea-117">Appel n’a pas encore été immobilisé</span><span class="sxs-lookup"><span data-stu-id="46cea-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="46cea-118">L’appel reste connecté, mais ne peut pas être parqué.</span><span class="sxs-lookup"><span data-stu-id="46cea-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="46cea-119">Pendant le basculement, l’appel ne peut pas être parqué lorsque les utilisateurs sont en mode de résilience, mais qui peuvent être mis en attente et transférés.</span><span class="sxs-lookup"><span data-stu-id="46cea-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="46cea-120">Lorsque le basculement est terminé, l’appel peut être parqué et récupéré.</span><span class="sxs-lookup"><span data-stu-id="46cea-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="46cea-121">Pendant la restauration, l’appel ne peut pas être parqué tant que les utilisateurs sont en mode de résilience, mais ils peuvent être mis en attente et transférés.</span><span class="sxs-lookup"><span data-stu-id="46cea-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="46cea-122">Lorsque la restauration automatique se termine, l’appel peut être parqué et récupéré.</span><span class="sxs-lookup"><span data-stu-id="46cea-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46cea-123">Appel en stationnement, mais pas encore récupéré</span><span class="sxs-lookup"><span data-stu-id="46cea-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="46cea-124">L’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="46cea-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="46cea-125">Aucun appel dans cet État.</span><span class="sxs-lookup"><span data-stu-id="46cea-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="46cea-126">L’appel reste en stationnement.</span><span class="sxs-lookup"><span data-stu-id="46cea-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46cea-127">Appel parqué déjà récupéré</span><span class="sxs-lookup"><span data-stu-id="46cea-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="46cea-128">L’appel reste connecté.</span><span class="sxs-lookup"><span data-stu-id="46cea-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="46cea-129">L’appel reste connecté.</span><span class="sxs-lookup"><span data-stu-id="46cea-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="46cea-130">L’appel reste connecté.</span><span class="sxs-lookup"><span data-stu-id="46cea-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

