---
title: 'Lync Server 2013 : table AudioStream'
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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502871"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="f4e76-102">Table AudioStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e76-102">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e76-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f4e76-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f4e76-104">Chaque enregistrement représente un flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-104">Each record represents one audio stream.</span></span> <span data-ttu-id="f4e76-105">Une ligne multimédia audio contient généralement deux flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4e76-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f4e76-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f4e76-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f4e76-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f4e76-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f4e76-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="f4e76-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f4e76-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e76-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-115">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-115">int</span></span></p></td>
<td><p><span data-ttu-id="f4e76-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="f4e76-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f4e76-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e76-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e76-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e76-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="f4e76-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f4e76-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e76-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-123">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-123">int</span></span></p></td>
<td><p><span data-ttu-id="f4e76-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="f4e76-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f4e76-125">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="f4e76-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-127">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-128">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="f4e76-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-130">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-131">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-133">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f4e76-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-134">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-136">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f4e76-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-137">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-139">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f4e76-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-140">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-142">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-143">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-145">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f4e76-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-146">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="f4e76-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-148">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-149">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="f4e76-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-151">Int</span><span class="sxs-lookup"><span data-stu-id="f4e76-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-152">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-153"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-154">Int</span><span class="sxs-lookup"><span data-stu-id="f4e76-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-155">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-157">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-p102">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-163">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-164">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-166">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-167">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="f4e76-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-169">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-170">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="f4e76-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-172">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-172">int</span></span></p></td>
<td><p><span data-ttu-id="f4e76-173">Etranger</span><span class="sxs-lookup"><span data-stu-id="f4e76-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4e76-174">Codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="f4e76-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-176">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-177">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-178"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-179">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-180">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="f4e76-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="f4e76-181">Pour une qualité acceptable, cette valeur doit être inférieure à 100 ms.</span><span class="sxs-lookup"><span data-stu-id="f4e76-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-183">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-184">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="f4e76-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-186">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-187">Note MOS qualité réseau moyenne en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="f4e76-188">Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé.</span><span class="sxs-lookup"><span data-stu-id="f4e76-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="f4e76-189">La plage est [1,0 to 5,0].</span><span class="sxs-lookup"><span data-stu-id="f4e76-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-191">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-192">Le MOS de réseau à large bande minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-194">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-195">Nombre moyen de scores de retour à la ligne pour l’audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="f4e76-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-197">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-198">SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-200">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-201">Nombre moyen de scores de retour à la ligne pour l’audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="f4e76-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-203">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-204">RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-206">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e76-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-207">Indicateur signalant si la fonction FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-209">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-210">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="f4e76-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-212">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-213">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="f4e76-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-215">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e76-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-216">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="f4e76-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-217"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-218">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e76-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-219">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="f4e76-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-220"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-221">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e76-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-222">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="f4e76-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-224">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e76-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f4e76-225">1 signifie que la direction du flux est entre l’appelant et l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e76-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="f4e76-226">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e76-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-228">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-229">Écart-type pour les heures d’arrivée de gigue.</span><span class="sxs-lookup"><span data-stu-id="f4e76-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="f4e76-230">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-232">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-233">Ratio maximal de paquets masqués par la réparation.</span><span class="sxs-lookup"><span data-stu-id="f4e76-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f4e76-234">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-236">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-237">Écart-type pour le rapport des paquets masqués par le réparer.</span><span class="sxs-lookup"><span data-stu-id="f4e76-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f4e76-238">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-240">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-241">Ratio de paquets supprimés par la réparation par rapport au nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="f4e76-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f4e76-242">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-244">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-245">Rapport entre les paquets de correction d’erreur de transfert utilisés et le nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="f4e76-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f4e76-246">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-248">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-249">Nombre maximal de paquets audio qui ont été compressés par le réparer.</span><span class="sxs-lookup"><span data-stu-id="f4e76-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="f4e76-250">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-252">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-253">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="f4e76-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f4e76-254">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-256">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-257">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="f4e76-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f4e76-258">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-260">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-261">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="f4e76-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f4e76-262">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-264">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-265">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f4e76-266">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-268">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-269">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f4e76-270">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-272">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-273">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f4e76-274">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-276">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-277">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e76-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f4e76-278">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-280">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p105">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-283">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-285">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p106">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-288">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-290">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p107">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-293">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-295">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p108">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-299">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-301">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p109">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-305">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-307">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p110">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-311">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-313">int</span><span class="sxs-lookup"><span data-stu-id="f4e76-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p111">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-317">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-319">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p112">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-323">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-325">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-p113">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4e76-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f4e76-329">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-331">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-332">Pourcentage de l’appel décodé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="f4e76-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="f4e76-333">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-335">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-336">Pourcentage de l’appel rendu stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="f4e76-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f4e76-337">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-339">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-340">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="f4e76-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f4e76-341">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e76-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-343">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-344">Pourcentage de l’appel codé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="f4e76-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="f4e76-345">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e76-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f4e76-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f4e76-347">float</span><span class="sxs-lookup"><span data-stu-id="f4e76-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4e76-348">Pourcentage de l’appel capturé en tant que stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="f4e76-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f4e76-349">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e76-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

