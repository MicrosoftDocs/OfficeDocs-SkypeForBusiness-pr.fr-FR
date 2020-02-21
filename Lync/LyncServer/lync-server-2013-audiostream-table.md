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
ms.openlocfilehash: e2da0884915f44246e316f80cb9fd35fb7aecaad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="7b258-102">Table AudioStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b258-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b258-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7b258-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7b258-104">Chaque enregistrement représente un flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-104">Each record represents one audio stream.</span></span> <span data-ttu-id="7b258-105">Une ligne multimédia audio contient généralement deux flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b258-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7b258-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7b258-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7b258-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b258-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7b258-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7b258-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="7b258-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b258-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b258-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-115">int</span><span class="sxs-lookup"><span data-stu-id="7b258-115">int</span></span></p></td>
<td><p><span data-ttu-id="7b258-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="7b258-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b258-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b258-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="7b258-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7b258-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="7b258-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b258-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b258-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-123">int</span><span class="sxs-lookup"><span data-stu-id="7b258-123">int</span></span></p></td>
<td><p><span data-ttu-id="7b258-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="7b258-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b258-125">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="7b258-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-127">int</span><span class="sxs-lookup"><span data-stu-id="7b258-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-128">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="7b258-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-130">int</span><span class="sxs-lookup"><span data-stu-id="7b258-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-131">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-133">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7b258-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-134">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-136">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7b258-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-137">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-139">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b258-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-140">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-142">int</span><span class="sxs-lookup"><span data-stu-id="7b258-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-143">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-145">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b258-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-146">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="7b258-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-148">int</span><span class="sxs-lookup"><span data-stu-id="7b258-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-149">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="7b258-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-151">Int</span><span class="sxs-lookup"><span data-stu-id="7b258-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-152">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-153"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-154">Int</span><span class="sxs-lookup"><span data-stu-id="7b258-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-155">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-157">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-p102">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="7b258-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-163">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-164">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-166">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-167">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="7b258-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-169">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-170">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="7b258-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-172">int</span><span class="sxs-lookup"><span data-stu-id="7b258-172">int</span></span></p></td>
<td><p><span data-ttu-id="7b258-173">Etranger</span><span class="sxs-lookup"><span data-stu-id="7b258-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b258-174">Codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="7b258-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-176">int</span><span class="sxs-lookup"><span data-stu-id="7b258-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-177">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-178"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-179">int</span><span class="sxs-lookup"><span data-stu-id="7b258-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-180">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="7b258-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="7b258-181">Pour une qualité acceptable, cette valeur doit être inférieure à 100 ms.</span><span class="sxs-lookup"><span data-stu-id="7b258-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-183">int</span><span class="sxs-lookup"><span data-stu-id="7b258-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-184">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="7b258-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-186">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-187">Note MOS qualité réseau moyenne en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="7b258-188">Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé.</span><span class="sxs-lookup"><span data-stu-id="7b258-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="7b258-189">La plage est [1,0 to 5,0].</span><span class="sxs-lookup"><span data-stu-id="7b258-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-191">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-192">Le MOS de réseau à large bande minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-194">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-195">Nombre moyen de scores de retour à la ligne pour l’audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="7b258-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-197">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-198">SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-200">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-201">Nombre moyen de scores de retour à la ligne pour l’audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="7b258-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-203">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-204">RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-206">légèrement</span><span class="sxs-lookup"><span data-stu-id="7b258-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-207">Indicateur signalant si la fonction FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-209">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-210">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="7b258-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-212">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-213">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="7b258-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-215">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7b258-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-216">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="7b258-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-217"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-218">légèrement</span><span class="sxs-lookup"><span data-stu-id="7b258-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-219">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="7b258-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-220"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-221">légèrement</span><span class="sxs-lookup"><span data-stu-id="7b258-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-222">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="7b258-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-224">légèrement</span><span class="sxs-lookup"><span data-stu-id="7b258-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b258-225">1 signifie que la direction du flux est entre l’appelant et l’appelé.</span><span class="sxs-lookup"><span data-stu-id="7b258-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="7b258-226">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="7b258-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-228">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-229">Écart-type pour les heures d’arrivée de gigue.</span><span class="sxs-lookup"><span data-stu-id="7b258-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="7b258-230">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-232">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-233">Ratio maximal de paquets masqués par la réparation.</span><span class="sxs-lookup"><span data-stu-id="7b258-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7b258-234">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-236">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-237">Écart-type pour le rapport des paquets masqués par le réparer.</span><span class="sxs-lookup"><span data-stu-id="7b258-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7b258-238">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-240">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-241">Ratio de paquets supprimés par la réparation par rapport au nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="7b258-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7b258-242">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-244">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-245">Rapport entre les paquets de correction d’erreur de transfert utilisés et le nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="7b258-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7b258-246">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-248">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-249">Nombre maximal de paquets audio qui ont été compressés par le réparer.</span><span class="sxs-lookup"><span data-stu-id="7b258-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="7b258-250">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-252">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-253">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="7b258-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="7b258-254">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-256">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-257">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="7b258-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="7b258-258">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-260">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-261">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="7b258-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="7b258-262">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-264">int</span><span class="sxs-lookup"><span data-stu-id="7b258-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-265">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b258-266">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-268">int</span><span class="sxs-lookup"><span data-stu-id="7b258-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-269">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b258-270">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-272">int</span><span class="sxs-lookup"><span data-stu-id="7b258-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-273">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b258-274">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-276">int</span><span class="sxs-lookup"><span data-stu-id="7b258-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-277">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="7b258-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b258-278">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-280">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p105">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-283">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-285">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p106">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-288">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-290">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p107">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-293">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-295">int</span><span class="sxs-lookup"><span data-stu-id="7b258-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p108">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-299">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-301">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p109">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-305">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-307">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p110">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-311">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-313">int</span><span class="sxs-lookup"><span data-stu-id="7b258-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p111">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-317">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-319">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p112">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-323">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-325">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-p113">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b258-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b258-329">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-331">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-332">Pourcentage de l’appel décodé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="7b258-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="7b258-333">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-335">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-336">Pourcentage de l’appel rendu stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="7b258-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7b258-337">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-339">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-340">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="7b258-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="7b258-341">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b258-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-343">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-344">Pourcentage de l’appel codé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="7b258-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="7b258-345">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b258-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b258-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b258-347">flottant</span><span class="sxs-lookup"><span data-stu-id="7b258-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b258-348">Pourcentage de l’appel capturé en tant que stéréo par le suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="7b258-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7b258-349">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b258-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

