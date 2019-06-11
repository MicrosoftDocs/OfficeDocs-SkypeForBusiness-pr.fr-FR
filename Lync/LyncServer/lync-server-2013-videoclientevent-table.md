---
title: 'Lync Server 2013 : Table VideoClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b428a639cee6fb0df04cc969b529c5bbbfb2c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="28396-102">Table VideoClientEvent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28396-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28396-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="28396-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="28396-104">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo.</span><span class="sxs-lookup"><span data-stu-id="28396-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="28396-105">En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="28396-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28396-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="28396-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="28396-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="28396-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="28396-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="28396-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="28396-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="28396-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28396-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="28396-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28396-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28396-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="28396-112">Principal</span><span class="sxs-lookup"><span data-stu-id="28396-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="28396-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28396-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28396-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="28396-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="28396-115">int</span><span class="sxs-lookup"><span data-stu-id="28396-115">int</span></span></p></td>
<td><p><span data-ttu-id="28396-116">Principal</span><span class="sxs-lookup"><span data-stu-id="28396-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="28396-117">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28396-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28396-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="28396-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="28396-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="28396-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="28396-120">Principal</span><span class="sxs-lookup"><span data-stu-id="28396-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="28396-121">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28396-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28396-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="28396-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="28396-123">bit</span><span class="sxs-lookup"><span data-stu-id="28396-123">bit</span></span></p></td>
<td><p><span data-ttu-id="28396-124">Principal</span><span class="sxs-lookup"><span data-stu-id="28396-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="28396-125">0: données du destinataire</span><span class="sxs-lookup"><span data-stu-id="28396-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="28396-126">1: données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="28396-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28396-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="28396-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28396-128">Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="28396-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="28396-129">La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="28396-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28396-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="28396-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28396-131">Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="28396-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="28396-132">La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son reçu.</span><span class="sxs-lookup"><span data-stu-id="28396-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

