---
title: Évolutivité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="d5476-102">Évolutivité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5476-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5476-103">_**Dernière modification de la rubrique:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d5476-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d5476-104">Lync Server est disponible en deux éditions, Enterprise Edition et Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d5476-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="d5476-105">Les différentes éditions sont principalement destinées aux différentes tailles d’organisations.</span><span class="sxs-lookup"><span data-stu-id="d5476-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="d5476-106">Comme indiqué dans le tableau suivant, les deux éditions prennent en charge toutes les fonctionnalités de toutes les charges de travail, à l’exception de haute disponibilité et de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="d5476-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5476-107">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="d5476-107">Feature</span></span></th>
<th><span data-ttu-id="d5476-108">Prise en charge dans l’édition Enterprise?</span><span class="sxs-lookup"><span data-stu-id="d5476-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="d5476-109">Prise en charge dans les éditions standard?</span><span class="sxs-lookup"><span data-stu-id="d5476-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5476-110">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="d5476-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="d5476-111">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-112">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5476-113">Conférence</span><span class="sxs-lookup"><span data-stu-id="d5476-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="d5476-114">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-115">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5476-116">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="d5476-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="d5476-117">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-118">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5476-119">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="d5476-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="d5476-120">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-121">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5476-122">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="d5476-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="d5476-123">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-124">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5476-125">La virtualisation</span><span class="sxs-lookup"><span data-stu-id="d5476-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="d5476-126">Oui </span><span class="sxs-lookup"><span data-stu-id="d5476-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-127">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5476-128">Haute disponibilité, basculement et reprise après sinistre</span><span class="sxs-lookup"><span data-stu-id="d5476-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="d5476-129">Oui</span><span class="sxs-lookup"><span data-stu-id="d5476-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5476-130">Non</span><span class="sxs-lookup"><span data-stu-id="d5476-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

