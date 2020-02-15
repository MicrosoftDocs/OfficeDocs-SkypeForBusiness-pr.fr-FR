---
title: 'Lync Server 2013 : planification de la capacité pour la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 403a00887cb64b33075f173499e855eb8783bb20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="3310f-102">Planification de la capacité pour la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3310f-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3310f-103">_**Dernière modification de la rubrique :** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="3310f-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="3310f-104">Le tableau suivant décrit le modèle utilisateur de prise d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="3310f-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3310f-105">La prise d’appel de groupe est basée sur l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="3310f-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="3310f-106">N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel, y compris la prise d’appel de groupe, dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="3310f-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="3310f-107">Modèle utilisateur de prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="3310f-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3310f-108">Liées</span><span class="sxs-lookup"><span data-stu-id="3310f-108">Metric</span></span></th>
<th><span data-ttu-id="3310f-109">Par pool frontal (avec 8 serveurs frontaux)</span><span class="sxs-lookup"><span data-stu-id="3310f-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="3310f-110">Par serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3310f-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3310f-111">Nombre d’utilisateurs par groupe recommandé</span><span class="sxs-lookup"><span data-stu-id="3310f-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="3310f-112">50</span><span class="sxs-lookup"><span data-stu-id="3310f-112">50</span></span></p></td>
<td><p><span data-ttu-id="3310f-113">50</span><span class="sxs-lookup"><span data-stu-id="3310f-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3310f-114">Nombre recommandé de groupes</span><span class="sxs-lookup"><span data-stu-id="3310f-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="3310f-115">500</span><span class="sxs-lookup"><span data-stu-id="3310f-115">500</span></span></p></td>
<td><p><span data-ttu-id="3310f-116">60</span><span class="sxs-lookup"><span data-stu-id="3310f-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3310f-117">Nombre maximal d’utilisateurs par pool activé pour la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="3310f-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="3310f-118">25 000</span><span class="sxs-lookup"><span data-stu-id="3310f-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="3310f-119">3,000</span><span class="sxs-lookup"><span data-stu-id="3310f-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3310f-120">Taux maximal d’appels entrants vers le total des utilisateurs activés pour la prise d’appel de groupe par pool et par minute</span><span class="sxs-lookup"><span data-stu-id="3310f-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="3310f-121">500</span><span class="sxs-lookup"><span data-stu-id="3310f-121">500</span></span></p></td>
<td><p><span data-ttu-id="3310f-122">60</span><span class="sxs-lookup"><span data-stu-id="3310f-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3310f-123">Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute</span><span class="sxs-lookup"><span data-stu-id="3310f-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="3310f-124">200</span><span class="sxs-lookup"><span data-stu-id="3310f-124">200</span></span></p></td>
<td><p><span data-ttu-id="3310f-125">25</span><span class="sxs-lookup"><span data-stu-id="3310f-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="3310f-126">Pour les pools frontaux qui ont moins de huit serveurs frontaux, calculez les mesures de manière linéaire.</span><span class="sxs-lookup"><span data-stu-id="3310f-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="3310f-127">Par exemple, si votre pool frontal dispose d’un serveur frontal, calculez la charge maximale sur 1/8 des valeurs indiquées dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="3310f-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="3310f-128">Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre maximal d’utilisateurs par pool.</span><span class="sxs-lookup"><span data-stu-id="3310f-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="3310f-129">Par exemple, votre serveur Standard Edition peut avoir 120 groupes avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la prise d’appel de groupe se trouve toujours dans le maximum du modèle utilisateur (autrement dit, 120 groupes fois que 25 utilisateurs 3 000 sont activés pour la prise d’appel de groupe).</span><span class="sxs-lookup"><span data-stu-id="3310f-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

