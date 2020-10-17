---
title: 'Lync Server 2013 : table table videoclientevent'
description: 'Lync Server 2013 : table table videoclientevent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568490"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="c5214-103">Table table videoclientevent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5214-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5214-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c5214-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c5214-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="c5214-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="c5214-106">En règle générale, un appel dispose de deux enregistrements, un pour l’appelant et un pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="c5214-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5214-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c5214-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c5214-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c5214-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5214-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5214-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5214-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5214-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="c5214-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5214-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c5214-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5214-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5214-116">int</span><span class="sxs-lookup"><span data-stu-id="c5214-116">int</span></span></p></td>
<td><p><span data-ttu-id="c5214-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="c5214-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5214-118">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c5214-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5214-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c5214-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="c5214-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c5214-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="c5214-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5214-122">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c5214-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5214-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="c5214-124">légèrement</span><span class="sxs-lookup"><span data-stu-id="c5214-124">bit</span></span></p></td>
<td><p><span data-ttu-id="c5214-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="c5214-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5214-126">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="c5214-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="c5214-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="c5214-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5214-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c5214-129">Pourcentage de la session l’événement LowBandwidth a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="c5214-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c5214-130">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="c5214-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5214-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c5214-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c5214-132">Pourcentage de la session l’événement ReceiveSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="c5214-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c5214-133">La qualité du réseau en termes de gigue ou de perte de paquets est importante et influe sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="c5214-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

