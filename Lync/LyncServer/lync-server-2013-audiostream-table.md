---
title: 'Lync Server 2013 : table AudioStream'
description: 'Lync Server 2013 : table AudioStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552340"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="ada8b-103">Table AudioStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ada8b-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ada8b-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ada8b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ada8b-105">Chaque enregistrement représente un flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-105">Each record represents one audio stream.</span></span> <span data-ttu-id="ada8b-106">Une ligne multimédia audio contient généralement deux flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ada8b-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ada8b-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ada8b-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ada8b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ada8b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ada8b-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="ada8b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ada8b-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ada8b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-116">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-116">int</span></span></p></td>
<td><p><span data-ttu-id="ada8b-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="ada8b-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ada8b-118">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ada8b-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ada8b-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ada8b-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="ada8b-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="ada8b-122">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ada8b-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-124">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-124">int</span></span></p></td>
<td><p><span data-ttu-id="ada8b-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="ada8b-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="ada8b-126">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="ada8b-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-128">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-129">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="ada8b-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-131">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-132">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-134">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ada8b-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-135">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-137">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ada8b-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-138">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-140">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ada8b-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-141">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-143">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-144">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-146">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ada8b-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-147">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="ada8b-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-149">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-150">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="ada8b-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-152">Int</span><span class="sxs-lookup"><span data-stu-id="ada8b-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-153">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-154"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-155">Int</span><span class="sxs-lookup"><span data-stu-id="ada8b-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-156">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-158">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-p102">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-164">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-165">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-167">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-168">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="ada8b-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-170">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-171">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="ada8b-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-173">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-173">int</span></span></p></td>
<td><p><span data-ttu-id="ada8b-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="ada8b-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ada8b-175">Codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="ada8b-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-177">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-178">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-179"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-180">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-181">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="ada8b-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="ada8b-182">Pour une qualité acceptable, cette valeur doit être inférieure à 100 ms.</span><span class="sxs-lookup"><span data-stu-id="ada8b-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-184">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-185">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ada8b-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-187">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-188">Note MOS qualité réseau moyenne en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="ada8b-189">Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé.</span><span class="sxs-lookup"><span data-stu-id="ada8b-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="ada8b-190">La plage est [1,0 to 5,0].</span><span class="sxs-lookup"><span data-stu-id="ada8b-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-192">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-193">Le MOS de réseau à large bande minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-195">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-196">Nombre moyen de scores de retour à la ligne pour l’audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="ada8b-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-198">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-199">SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-201">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-202">Nombre moyen de scores de retour à la ligne pour l’audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="ada8b-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-204">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-205">RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-207">légèrement</span><span class="sxs-lookup"><span data-stu-id="ada8b-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-208">Indicateur signalant si la fonction FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-210">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-211">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="ada8b-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-213">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-214">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="ada8b-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-216">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ada8b-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-217">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="ada8b-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-218"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-219">légèrement</span><span class="sxs-lookup"><span data-stu-id="ada8b-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-220">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="ada8b-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-221"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-222">légèrement</span><span class="sxs-lookup"><span data-stu-id="ada8b-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-223">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="ada8b-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-225">légèrement</span><span class="sxs-lookup"><span data-stu-id="ada8b-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ada8b-226">1 signifie que la direction du flux est entre l’appelant et l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ada8b-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="ada8b-227">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ada8b-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-229">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-230">Écart-type pour les heures d’arrivée de gigue.</span><span class="sxs-lookup"><span data-stu-id="ada8b-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="ada8b-231">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-233">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-234">Ratio maximal de paquets masqués par la réparation.</span><span class="sxs-lookup"><span data-stu-id="ada8b-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="ada8b-235">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-237">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-238">Écart-type pour le rapport des paquets masqués par le réparer.</span><span class="sxs-lookup"><span data-stu-id="ada8b-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="ada8b-239">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-241">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-242">Ratio de paquets supprimés par la réparation par rapport au nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="ada8b-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="ada8b-243">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-245">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-246">Rapport entre les paquets de correction d’erreur de transfert utilisés et le nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="ada8b-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="ada8b-247">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-249">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-250">Nombre maximal de paquets audio qui ont été compressés par le réparer.</span><span class="sxs-lookup"><span data-stu-id="ada8b-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="ada8b-251">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-253">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-254">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="ada8b-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="ada8b-255">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-257">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-258">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="ada8b-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="ada8b-259">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-261">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-262">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="ada8b-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="ada8b-263">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-265">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-266">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ada8b-267">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-269">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-270">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ada8b-271">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-273">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-274">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ada8b-275">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-277">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-278">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ada8b-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ada8b-279">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-281">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p105">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-284">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-286">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p106">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-289">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-291">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p107">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-294">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-296">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p108">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-300">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-302">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p109">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-306">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-308">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p110">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-312">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-314">int</span><span class="sxs-lookup"><span data-stu-id="ada8b-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p111">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-318">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-320">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p112">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-324">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-326">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-p113">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ada8b-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ada8b-330">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-332">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-333">Pourcentage de l’appel décodé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="ada8b-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="ada8b-334">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-336">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-337">Pourcentage de l’appel rendu stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="ada8b-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="ada8b-338">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-340">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-341">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="ada8b-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="ada8b-342">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ada8b-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-344">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-345">Pourcentage de l’appel codé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="ada8b-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="ada8b-346">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada8b-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ada8b-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ada8b-348">float</span><span class="sxs-lookup"><span data-stu-id="ada8b-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada8b-349">Pourcentage de l’appel capturé en tant que stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="ada8b-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="ada8b-350">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ada8b-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

