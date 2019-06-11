---
title: 'Lync Server 2013: table TraceRoute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="e19a8-102">Tableau TraceRoute dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e19a8-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e19a8-103">_**Dernière modification de la rubrique:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="e19a8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="e19a8-104">La table TraceRoute contient les informations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="e19a8-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="e19a8-105">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19a8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e19a8-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e19a8-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e19a8-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e19a8-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e19a8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e19a8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e19a8-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e19a8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e19a8-113">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e19a8-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e19a8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-115">int</span><span class="sxs-lookup"><span data-stu-id="e19a8-115">int</span></span></p></td>
<td><p><span data-ttu-id="e19a8-116">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e19a8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e19a8-117">Identificateur unique permettant de faire la distinction entre plusieurs appels qui pouvaient avoir commencé à la même date et en même temps.</span><span class="sxs-lookup"><span data-stu-id="e19a8-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e19a8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e19a8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e19a8-120">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e19a8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e19a8-121">Représente le type de ligne vidéo utilisée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e19a8-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="e19a8-122">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e19a8-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e19a8-123">0-audio</span><span class="sxs-lookup"><span data-stu-id="e19a8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="e19a8-124">1-vidéo</span><span class="sxs-lookup"><span data-stu-id="e19a8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="e19a8-125">2-vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="e19a8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="e19a8-126">3 – partage de bureau et d’application</span><span class="sxs-lookup"><span data-stu-id="e19a8-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e19a8-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-128">bit</span><span class="sxs-lookup"><span data-stu-id="e19a8-128">bit</span></span></p></td>
<td><p><span data-ttu-id="e19a8-129">Principal</span><span class="sxs-lookup"><span data-stu-id="e19a8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="e19a8-130">Point de terminaison ayant placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="e19a8-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e19a8-131"><strong>Relais</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-132">int</span><span class="sxs-lookup"><span data-stu-id="e19a8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e19a8-133">Tronçon réseau/</span><span class="sxs-lookup"><span data-stu-id="e19a8-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e19a8-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-135">int</span><span class="sxs-lookup"><span data-stu-id="e19a8-135">int</span></span></p></td>
<td><p><span data-ttu-id="e19a8-136">Externes</span><span class="sxs-lookup"><span data-stu-id="e19a8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e19a8-137">Identificateur unique de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="e19a8-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="e19a8-138">Les informations d’adresse IP sont stockées dans la <a href="lync-server-2013-ipaddress-table.md">table IPAddress de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e19a8-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e19a8-139"><strong>TEMPS</strong></span><span class="sxs-lookup"><span data-stu-id="e19a8-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="e19a8-140">int</span><span class="sxs-lookup"><span data-stu-id="e19a8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e19a8-141">Durée de l’aller-retour.</span><span class="sxs-lookup"><span data-stu-id="e19a8-141">Roundtrip time.</span></span> <span data-ttu-id="e19a8-142">Le temps d’aller-retour mesure la durée pendant laquelle un paquet vocal atteint sa destination et renvoie la notification de réception.</span><span class="sxs-lookup"><span data-stu-id="e19a8-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

