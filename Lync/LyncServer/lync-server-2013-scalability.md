---
title: Évolutivité de Lync Server 2013
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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="b0aa1-102">Évolutivité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0aa1-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0aa1-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="b0aa1-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="b0aa1-104">Lync Server est proposé en deux éditions, Enterprise Edition et Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b0aa1-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="b0aa1-105">Elles sont chacune destinées à des organisations de différente taille.</span><span class="sxs-lookup"><span data-stu-id="b0aa1-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="b0aa1-106">Comme indiqué dans le tableau suivant, les deux éditions prennent en charge toutes les fonctionnalités pour toutes les charges de travail, à l’exception de la haute disponibilité et de la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b0aa1-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0aa1-107">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="b0aa1-107">Feature</span></span></th>
<th><span data-ttu-id="b0aa1-108">Prise en charge dans Enterprise Edition ?</span><span class="sxs-lookup"><span data-stu-id="b0aa1-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="b0aa1-109">Prise en charge dans Standard Edition ?</span><span class="sxs-lookup"><span data-stu-id="b0aa1-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0aa1-110">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="b0aa1-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-111">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-112">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aa1-113">Vidéoconférence</span><span class="sxs-lookup"><span data-stu-id="b0aa1-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-114">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-115">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aa1-116">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="b0aa1-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-117">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-118">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aa1-119">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="b0aa1-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-120">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-121">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aa1-122">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="b0aa1-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-123">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-124">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aa1-125">Virtualisation</span><span class="sxs-lookup"><span data-stu-id="b0aa1-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-126">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-127">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aa1-128">Haute disponibilité, basculement et récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="b0aa1-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-129">Oui</span><span class="sxs-lookup"><span data-stu-id="b0aa1-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0aa1-130">Non</span><span class="sxs-lookup"><span data-stu-id="b0aa1-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

