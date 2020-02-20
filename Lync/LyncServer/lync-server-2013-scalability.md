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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="2aeea-102">Évolutivité avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aeea-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aeea-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2aeea-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2aeea-104">Lync Server est proposé en deux éditions, Enterprise Edition et Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2aeea-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="2aeea-105">Elles sont chacune destinées à des organisations de différente taille.</span><span class="sxs-lookup"><span data-stu-id="2aeea-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="2aeea-106">Comme indiqué dans le tableau suivant, les deux éditions prennent en charge toutes les fonctionnalités pour toutes les charges de travail, à l’exception de la haute disponibilité et de la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="2aeea-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aeea-107">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="2aeea-107">Feature</span></span></th>
<th><span data-ttu-id="2aeea-108">Prise en charge dans Enterprise Edition ?</span><span class="sxs-lookup"><span data-stu-id="2aeea-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="2aeea-109">Prise en charge dans Standard Edition ?</span><span class="sxs-lookup"><span data-stu-id="2aeea-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aeea-110">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="2aeea-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="2aeea-111">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-112">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aeea-113">Vidéoconférence</span><span class="sxs-lookup"><span data-stu-id="2aeea-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="2aeea-114">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-115">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aeea-116">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="2aeea-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="2aeea-117">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-118">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aeea-119">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2aeea-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="2aeea-120">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-121">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aeea-122">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="2aeea-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="2aeea-123">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-124">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aeea-125">Virtualisation</span><span class="sxs-lookup"><span data-stu-id="2aeea-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="2aeea-126">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-127">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aeea-128">Haute disponibilité, basculement et récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="2aeea-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="2aeea-129">Oui</span><span class="sxs-lookup"><span data-stu-id="2aeea-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="2aeea-130">Non</span><span class="sxs-lookup"><span data-stu-id="2aeea-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

