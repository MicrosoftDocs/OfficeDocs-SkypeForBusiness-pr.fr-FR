---
title: 'Lync Server 2013: planification de la capacité pour le prélèvement d’appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="3cd8a-102">Planification de la capacité pour le prélèvement d’appels de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cd8a-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cd8a-103">_**Dernière modification de la rubrique:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="3cd8a-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="3cd8a-104">Le tableau suivant décrit le modèle d’utilisateur de capture d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3cd8a-105">Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="3cd8a-106">N’oubliez pas que, pour la planification de la capacité de reprise après sinistre, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail pour les services de parking d’appel, y compris le regroupement des appels de groupe, dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="3cd8a-107">Modèle utilisateur de cueillette d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="3cd8a-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cd8a-108">Mesure</span><span class="sxs-lookup"><span data-stu-id="3cd8a-108">Metric</span></span></th>
<th><span data-ttu-id="3cd8a-109">Par pool frontal (avec 8 serveurs frontaux)</span><span class="sxs-lookup"><span data-stu-id="3cd8a-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="3cd8a-110">Par serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3cd8a-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cd8a-111">Nombre recommandé d’utilisateurs par groupe</span><span class="sxs-lookup"><span data-stu-id="3cd8a-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-112">50</span><span class="sxs-lookup"><span data-stu-id="3cd8a-112">50</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-113">50</span><span class="sxs-lookup"><span data-stu-id="3cd8a-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cd8a-114">Nombre recommandé de groupes</span><span class="sxs-lookup"><span data-stu-id="3cd8a-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-115">500</span><span class="sxs-lookup"><span data-stu-id="3cd8a-115">500</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-116">60</span><span class="sxs-lookup"><span data-stu-id="3cd8a-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cd8a-117">Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="3cd8a-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-118">25 000</span><span class="sxs-lookup"><span data-stu-id="3cd8a-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-119">3 000</span><span class="sxs-lookup"><span data-stu-id="3cd8a-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cd8a-120">Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute</span><span class="sxs-lookup"><span data-stu-id="3cd8a-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-121">500</span><span class="sxs-lookup"><span data-stu-id="3cd8a-121">500</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-122">60</span><span class="sxs-lookup"><span data-stu-id="3cd8a-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cd8a-123">Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute</span><span class="sxs-lookup"><span data-stu-id="3cd8a-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-124">200</span><span class="sxs-lookup"><span data-stu-id="3cd8a-124">200</span></span></p></td>
<td><p><span data-ttu-id="3cd8a-125">1,25</span><span class="sxs-lookup"><span data-stu-id="3cd8a-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="3cd8a-126">Pour les pools front-end possédant moins de huit serveurs frontaux, calculez les métriques de manière linéaire.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="3cd8a-127">Par exemple, si votre pool frontal comporte un serveur frontal, calculez le chargement maximum comme 1/8 de valeurs affichées dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="3cd8a-128">Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool.</span><span class="sxs-lookup"><span data-stu-id="3cd8a-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="3cd8a-129">Par exemple, votre serveur édition standard peut avoir des groupes 120 avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la capture d’appels de groupe est toujours au maximum au niveau du modèle utilisateur (c’est-à-dire, 120 3 000 groupes).</span><span class="sxs-lookup"><span data-stu-id="3cd8a-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

