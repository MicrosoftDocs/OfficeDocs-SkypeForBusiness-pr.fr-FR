---
title: Évolutivité de Lync Server 2013
description: Évolutivité de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543790"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="53bbf-103">Évolutivité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53bbf-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53bbf-104">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="53bbf-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="53bbf-105">Lync Server est proposé en deux éditions, Enterprise Edition et Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="53bbf-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="53bbf-106">Elles sont chacune destinées à des organisations de différente taille.</span><span class="sxs-lookup"><span data-stu-id="53bbf-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="53bbf-107">Comme indiqué dans le tableau suivant, les deux éditions prennent en charge toutes les fonctionnalités pour toutes les charges de travail, à l’exception de la haute disponibilité et de la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="53bbf-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53bbf-108">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="53bbf-108">Feature</span></span></th>
<th><span data-ttu-id="53bbf-109">Prise en charge dans Enterprise Edition ?</span><span class="sxs-lookup"><span data-stu-id="53bbf-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="53bbf-110">Prise en charge dans Standard Edition ?</span><span class="sxs-lookup"><span data-stu-id="53bbf-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53bbf-111">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="53bbf-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="53bbf-112">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-113">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53bbf-114">Conférence</span><span class="sxs-lookup"><span data-stu-id="53bbf-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="53bbf-115">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-116">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53bbf-117">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="53bbf-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="53bbf-118">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-119">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53bbf-120">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="53bbf-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="53bbf-121">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-122">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53bbf-123">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="53bbf-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="53bbf-124">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-125">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53bbf-126">Virtualisation</span><span class="sxs-lookup"><span data-stu-id="53bbf-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="53bbf-127">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-128">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53bbf-129">Haute disponibilité, basculement et récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="53bbf-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="53bbf-130">Oui</span><span class="sxs-lookup"><span data-stu-id="53bbf-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="53bbf-131">Non</span><span class="sxs-lookup"><span data-stu-id="53bbf-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

