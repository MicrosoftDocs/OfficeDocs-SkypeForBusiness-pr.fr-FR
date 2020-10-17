---
title: 'Lync Server 2013 : table TraceRoute'
description: 'Lync Server 2013 : table TraceRoute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549060"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="dcdfa-103">Table TraceRoute dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcdfa-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcdfa-104">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="dcdfa-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="dcdfa-105">La table TraceRoute contient les informations de routage émanant des appels.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="dcdfa-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcdfa-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dcdfa-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dcdfa-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dcdfa-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcdfa-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dcdfa-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="dcdfa-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-114">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcdfa-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-116">int</span><span class="sxs-lookup"><span data-stu-id="dcdfa-116">int</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="dcdfa-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-118">Identificateur unique utilisé pour faire la distinction entre plusieurs appels qui peuvent avoir commencé à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcdfa-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="dcdfa-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-121">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="dcdfa-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-p102">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="dcdfa-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcdfa-124">0 – audio</span><span class="sxs-lookup"><span data-stu-id="dcdfa-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="dcdfa-125">1 – vidéo</span><span class="sxs-lookup"><span data-stu-id="dcdfa-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="dcdfa-126">2 – Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="dcdfa-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="dcdfa-127">3 – partage d’application/Bureau</span><span class="sxs-lookup"><span data-stu-id="dcdfa-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcdfa-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-129">légèrement</span><span class="sxs-lookup"><span data-stu-id="dcdfa-129">bit</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="dcdfa-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-131">Système d’extrémité qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcdfa-132"><strong>Bond</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-133">int</span><span class="sxs-lookup"><span data-stu-id="dcdfa-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcdfa-134">Tronçon de réseau.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcdfa-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-136">int</span><span class="sxs-lookup"><span data-stu-id="dcdfa-136">int</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-137">Etranger</span><span class="sxs-lookup"><span data-stu-id="dcdfa-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcdfa-138">Identificateur unique de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="dcdfa-139">Les informations relatives aux adresses IP sont stockées dans la <a href="lync-server-2013-ipaddress-table.md">table IPAddress de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcdfa-140"><strong>TEMPS</strong></span><span class="sxs-lookup"><span data-stu-id="dcdfa-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="dcdfa-141">int</span><span class="sxs-lookup"><span data-stu-id="dcdfa-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcdfa-p104">Durée de boucle. La durée de boucle mesure le temps nécessaire pour qu’un paquet vocal atteigne sa destination, puis renvoie une notification indiquant qu’il a été reçu.</span><span class="sxs-lookup"><span data-stu-id="dcdfa-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

