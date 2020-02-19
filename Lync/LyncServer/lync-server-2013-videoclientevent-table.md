---
title: 'Lync Server 2013 : table table videoclientevent'
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
ms.openlocfilehash: a74c8e35af346d82c695f738a8db46bc328d691b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="76474-102">Table table videoclientevent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76474-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76474-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="76474-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="76474-104">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="76474-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="76474-105">En règle générale, un appel dispose de deux enregistrements, un pour l’appelant et un pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="76474-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76474-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="76474-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="76474-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="76474-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="76474-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="76474-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="76474-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="76474-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76474-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="76474-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="76474-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="76474-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="76474-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="76474-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="76474-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="76474-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76474-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="76474-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="76474-115">int</span><span class="sxs-lookup"><span data-stu-id="76474-115">int</span></span></p></td>
<td><p><span data-ttu-id="76474-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="76474-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="76474-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="76474-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76474-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="76474-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="76474-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="76474-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="76474-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="76474-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="76474-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="76474-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76474-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="76474-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="76474-123">légèrement</span><span class="sxs-lookup"><span data-stu-id="76474-123">bit</span></span></p></td>
<td><p><span data-ttu-id="76474-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="76474-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="76474-125">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="76474-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="76474-126">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="76474-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76474-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="76474-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="76474-128">Pourcentage de la session l’événement LowBandwidth a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="76474-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="76474-129">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="76474-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76474-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="76474-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="76474-131">Pourcentage de la session l’événement ReceiveSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="76474-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="76474-132">La qualité du réseau en termes de gigue ou de perte de paquets est importante et influe sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="76474-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

