---
title: 'Lync Server 2013 : table TraceRoute'
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
ms.openlocfilehash: 057253527615164b4b8b22a1fa13e7ea48778ee1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="0b540-102">Table TraceRoute dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b540-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b540-103">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="0b540-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="0b540-104">La table TraceRoute contient les informations de routage émanant des appels.</span><span class="sxs-lookup"><span data-stu-id="0b540-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="0b540-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b540-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b540-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0b540-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0b540-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0b540-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b540-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0b540-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b540-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="0b540-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0b540-113">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b540-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b540-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-115">int</span><span class="sxs-lookup"><span data-stu-id="0b540-115">int</span></span></p></td>
<td><p><span data-ttu-id="0b540-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="0b540-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0b540-117">Identificateur unique utilisé pour faire la distinction entre plusieurs appels qui peuvent avoir commencé à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="0b540-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b540-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b540-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b540-120">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="0b540-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0b540-p102">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b540-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0b540-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="0b540-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="0b540-124">1 – vidéo</span><span class="sxs-lookup"><span data-stu-id="0b540-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="0b540-125">2 – Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="0b540-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="0b540-126">3 – partage d’application/Bureau</span><span class="sxs-lookup"><span data-stu-id="0b540-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b540-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-128">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b540-128">bit</span></span></p></td>
<td><p><span data-ttu-id="0b540-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="0b540-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="0b540-130">Système d’extrémité qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b540-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b540-131"><strong>Bond</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-132">int</span><span class="sxs-lookup"><span data-stu-id="0b540-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0b540-133">Tronçon de réseau.</span><span class="sxs-lookup"><span data-stu-id="0b540-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b540-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-135">int</span><span class="sxs-lookup"><span data-stu-id="0b540-135">int</span></span></p></td>
<td><p><span data-ttu-id="0b540-136">Etranger</span><span class="sxs-lookup"><span data-stu-id="0b540-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0b540-137">Identificateur unique de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="0b540-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="0b540-138">Les informations relatives aux adresses IP sont stockées dans la <a href="lync-server-2013-ipaddress-table.md">table IPAddress de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0b540-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b540-139"><strong>TEMPS</strong></span><span class="sxs-lookup"><span data-stu-id="0b540-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="0b540-140">int</span><span class="sxs-lookup"><span data-stu-id="0b540-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0b540-p104">Durée de boucle. La durée de boucle mesure le temps nécessaire pour qu’un paquet vocal atteigne sa destination, puis renvoie une notification indiquant qu’il a été reçu.</span><span class="sxs-lookup"><span data-stu-id="0b540-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

