---
title: 'Lync Server 2013 : expérience de parcage d’appel en cas de défaillance du pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1834c9872dc9b8c1045c6e5e638f86f760b4ad4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="c9f6c-102">Expérience de parcage d’appel dans Lync Server 2013 en cas de défaillance du pool</span><span class="sxs-lookup"><span data-stu-id="c9f6c-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9f6c-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c9f6c-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c9f6c-104">Lorsqu’un pool frontal devient indisponible en raison d’un incident non planifié, les appels qui ont été parqués mais ne sont pas encore extraits sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="c9f6c-105">Durant le basculement vers un pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et placés en mode Résilience.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="c9f6c-106">Dans ce mode, les utilisateurs ne peuvent pas parquer les appels, mais ils peuvent les placer en attente et les transférer.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="c9f6c-107">Lorsque le basculement est terminé, les appels peuvent de nouveau être parqués et récupérés, comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="c9f6c-108">Durant la restauration automatique, les utilisateurs ne peuvent pas parquer les appels jusqu’à ce qu’ils quittent le mode Résilience.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="c9f6c-109">Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parcage d’appel qui est déployée dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="c9f6c-110">Par conséquent, les utilisateurs qui sont redirigés vers le pool de sauvegarde utilisent les paramètres de parcage d’appel qui sont configurés pour l’application de parcage d’appel dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="c9f6c-111">Le tableau suivant résume l’expérience de parcage d’appel pendant les phases de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="c9f6c-112">Expérience utilisateur durant la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="c9f6c-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9f6c-113">État de l’appel</span><span class="sxs-lookup"><span data-stu-id="c9f6c-113">Call state</span></span></th>
<th><span data-ttu-id="c9f6c-114">Lorsqu’une panne se produit</span><span class="sxs-lookup"><span data-stu-id="c9f6c-114">When outage occurs</span></span></th>
<th><span data-ttu-id="c9f6c-115">Durant le basculement</span><span class="sxs-lookup"><span data-stu-id="c9f6c-115">During failover</span></span></th>
<th><span data-ttu-id="c9f6c-116">Durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="c9f6c-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9f6c-117">Pour les appels non parqués</span><span class="sxs-lookup"><span data-stu-id="c9f6c-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-118">Les appels restent connectés, mais ne peuvent pas être parqués.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c9f6c-119">Durant le basculement, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c9f6c-120">Lorsque le basculement est terminé, les appels peuvent être parqués et récupérés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c9f6c-121">Durant la restauration automatique, les appels ne peuvent pas être parqués pendant que les utilisateurs sont en mode Résilience, mais ils peuvent être mis en attente et transférés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c9f6c-122">Lorsque la restauration automatique est terminée, les appels peuvent être parqués et récupérés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9f6c-123">Pour les appels parqués, mais non récupérés</span><span class="sxs-lookup"><span data-stu-id="c9f6c-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-124">Ces appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-125">Aucun appel ne reste dans cet état.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-126">Les appels restent parqués.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9f6c-127">Pour les appels parqués déjà récupérés</span><span class="sxs-lookup"><span data-stu-id="c9f6c-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-128">Ces appels restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-129">Ces appels restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c9f6c-130">Ces appels restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c9f6c-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

