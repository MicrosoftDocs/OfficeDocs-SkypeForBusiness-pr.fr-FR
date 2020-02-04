---
title: 'Lync Server 2013 : Table AudioStream'
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="21782-102">Table AudioStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21782-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21782-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="21782-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="21782-104">Chaque enregistrement représente un flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-104">Each record represents one audio stream.</span></span> <span data-ttu-id="21782-105">Une ligne de médias audio contient généralement deux flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21782-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="21782-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="21782-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="21782-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="21782-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="21782-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="21782-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="21782-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21782-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="21782-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="21782-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="21782-112">Principal</span><span class="sxs-lookup"><span data-stu-id="21782-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="21782-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="21782-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21782-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-115">int</span><span class="sxs-lookup"><span data-stu-id="21782-115">int</span></span></p></td>
<td><p><span data-ttu-id="21782-116">Principal</span><span class="sxs-lookup"><span data-stu-id="21782-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="21782-117">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="21782-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="21782-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="21782-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="21782-120">Principal</span><span class="sxs-lookup"><span data-stu-id="21782-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="21782-121">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="21782-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="21782-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-123">int</span><span class="sxs-lookup"><span data-stu-id="21782-123">int</span></span></p></td>
<td><p><span data-ttu-id="21782-124">Principal</span><span class="sxs-lookup"><span data-stu-id="21782-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="21782-125">IDENTIFIant unique dans une ligne de médias.</span><span class="sxs-lookup"><span data-stu-id="21782-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="21782-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-127">int</span><span class="sxs-lookup"><span data-stu-id="21782-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-128">Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="21782-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-130">int</span><span class="sxs-lookup"><span data-stu-id="21782-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-131">Scintillement du réseau maximum lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="21782-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-133">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="21782-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-134">Taux moyen de perte de paquets lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-136">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="21782-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-137">Perte de paquets maximum observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="21782-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-139">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="21782-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-140">Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="21782-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-142">int</span><span class="sxs-lookup"><span data-stu-id="21782-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-143">Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="21782-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-145">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="21782-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-146">Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="21782-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="21782-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-148">int</span><span class="sxs-lookup"><span data-stu-id="21782-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-149">Durée moyenne des espaces entre les pics de perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="21782-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="21782-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-151">Ent</span><span class="sxs-lookup"><span data-stu-id="21782-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-152">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-153"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="21782-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-154">Ent</span><span class="sxs-lookup"><span data-stu-id="21782-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-155">Estimations de bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-157">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-158">Baisse de la dégradation du réseau pour l’ensemble de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="21782-159">La plage est 0,0 à 5,0.</span><span class="sxs-lookup"><span data-stu-id="21782-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="21782-160">Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="21782-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="21782-161">Pour une qualité acceptable, elle doit être inférieure à 0,5.</span><span class="sxs-lookup"><span data-stu-id="21782-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-163">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-164">Dégradation du réseau maximal pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-166">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-167">Baisse de la dégradation du réseau à l’origine de gigue.</span><span class="sxs-lookup"><span data-stu-id="21782-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-169">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-170">Baisse de la dégradation du réseau à l’origine de la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="21782-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="21782-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-172">int</span><span class="sxs-lookup"><span data-stu-id="21782-172">int</span></span></p></td>
<td><p><span data-ttu-id="21782-173">Externes</span><span class="sxs-lookup"><span data-stu-id="21782-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21782-174">Le codec audio utilisé pour l’appel, référencé à partir de la table PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="21782-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="21782-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-176">int</span><span class="sxs-lookup"><span data-stu-id="21782-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-177">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="21782-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-179">int</span><span class="sxs-lookup"><span data-stu-id="21782-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-180">Durée de l’aller-retour des statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="21782-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="21782-181">Pour une qualité acceptable, il devrait être inférieur à 100 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="21782-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-183">int</span><span class="sxs-lookup"><span data-stu-id="21782-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-184">Durée de l’aller-retour maximal pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="21782-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="21782-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-186">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-187">MOS du réseau à bandes moyenne pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="21782-188">Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés.</span><span class="sxs-lookup"><span data-stu-id="21782-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="21782-189">La plage est [1,0 à 5,0].</span><span class="sxs-lookup"><span data-stu-id="21782-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="21782-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-191">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-192">Le réseau de bandes minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="21782-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-194">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-195">Le score d’écoute de la bande moyenne prédite pour le son envoyé, y compris le niveau de voix, le niveau de bruit et les caractéristiques de l’appareil de capture.</span><span class="sxs-lookup"><span data-stu-id="21782-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="21782-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-197">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-198">Le minimum SendListenMOS pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="21782-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-200">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-201">Le score d’écoute de la bande moyenne prédite pour le son reçu du réseau, notamment le niveau de voix, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.</span><span class="sxs-lookup"><span data-stu-id="21782-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="21782-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-203">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="21782-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-204">Le minimum RecvListenMOS pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="21782-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-206">bit</span><span class="sxs-lookup"><span data-stu-id="21782-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-207">Indicateur indiquant si l’audio FEC a été utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-209">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="21782-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-210">Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="21782-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-212">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="21782-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-213">Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="21782-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="21782-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-215">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="21782-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-216">Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="21782-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-217"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="21782-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-218">bit</span><span class="sxs-lookup"><span data-stu-id="21782-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-219">Des données de flux sur le côté du destinataire sont reçues.</span><span class="sxs-lookup"><span data-stu-id="21782-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-220"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="21782-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-221">bit</span><span class="sxs-lookup"><span data-stu-id="21782-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-222">Les données du flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="21782-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="21782-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-224">bit</span><span class="sxs-lookup"><span data-stu-id="21782-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21782-225">1 signifie que le sens du flux provient de l’appelant vers l’appelant.</span><span class="sxs-lookup"><span data-stu-id="21782-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="21782-226">0 : le sens du flux provient de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="21782-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="21782-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-228">float</span><span class="sxs-lookup"><span data-stu-id="21782-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-229">Écart type pour les heures d’arrivée de gigue.</span><span class="sxs-lookup"><span data-stu-id="21782-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="21782-230">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-232">float</span><span class="sxs-lookup"><span data-stu-id="21782-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-233">Taux maximal de paquets masqués par la correction.</span><span class="sxs-lookup"><span data-stu-id="21782-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="21782-234">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="21782-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-236">float</span><span class="sxs-lookup"><span data-stu-id="21782-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-237">Écart type pour le rapport de paquets masqués par la correction.</span><span class="sxs-lookup"><span data-stu-id="21782-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="21782-238">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21782-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-240">float</span><span class="sxs-lookup"><span data-stu-id="21782-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-241">Taux de paquets rejetés par le taux de correction par rapport au nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="21782-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="21782-242">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="21782-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-244">float</span><span class="sxs-lookup"><span data-stu-id="21782-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-245">Taux de paquets de correction d’erreur de transfert utilisés par rapport au nombre total de paquets reçus.</span><span class="sxs-lookup"><span data-stu-id="21782-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="21782-246">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="21782-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-248">float</span><span class="sxs-lookup"><span data-stu-id="21782-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-249">Nombre maximal de paquets audio compressés par le cicatrisé.</span><span class="sxs-lookup"><span data-stu-id="21782-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="21782-250">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-252">float</span><span class="sxs-lookup"><span data-stu-id="21782-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-253">Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="21782-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="21782-254">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-256">float</span><span class="sxs-lookup"><span data-stu-id="21782-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-257">Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="21782-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="21782-258">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-260">float</span><span class="sxs-lookup"><span data-stu-id="21782-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-261">Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="21782-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="21782-262">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="21782-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-264">int</span><span class="sxs-lookup"><span data-stu-id="21782-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-265">Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="21782-266">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-268">int</span><span class="sxs-lookup"><span data-stu-id="21782-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-269">Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="21782-270">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="21782-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-272">int</span><span class="sxs-lookup"><span data-stu-id="21782-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-273">Écart type de l’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="21782-274">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="21782-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-276">int</span><span class="sxs-lookup"><span data-stu-id="21782-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-277">Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="21782-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="21782-278">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="21782-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-280">float</span><span class="sxs-lookup"><span data-stu-id="21782-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-281">Quantité totale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="21782-281">Total amount of one-way latency.</span></span> <span data-ttu-id="21782-282">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-283">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-284"><strong>Moyenne unidirectionnelle relative</strong></span><span class="sxs-lookup"><span data-stu-id="21782-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-285">float</span><span class="sxs-lookup"><span data-stu-id="21782-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-286">Quantité moyenne de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="21782-286">Average amount of one-way latency.</span></span> <span data-ttu-id="21782-287">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-288">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="21782-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-290">float</span><span class="sxs-lookup"><span data-stu-id="21782-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-291">Quantité maximale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="21782-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="21782-292">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-293">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="21782-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-295">int</span><span class="sxs-lookup"><span data-stu-id="21782-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-296">Nombre total d’occurrences de rafales à sens unique.</span><span class="sxs-lookup"><span data-stu-id="21782-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="21782-297">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="21782-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="21782-298">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-299">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="21782-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-301">float</span><span class="sxs-lookup"><span data-stu-id="21782-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-302">Densité du Burst total unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="21782-302">Total one-way burst density.</span></span> <span data-ttu-id="21782-303">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="21782-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="21782-304">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-305">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="21782-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-307">float</span><span class="sxs-lookup"><span data-stu-id="21782-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-308">Durée totale du Burst.</span><span class="sxs-lookup"><span data-stu-id="21782-308">Total one-way burst duration.</span></span> <span data-ttu-id="21782-309">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="21782-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="21782-310">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-311">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="21782-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-313">int</span><span class="sxs-lookup"><span data-stu-id="21782-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-314">Nombre total d’occurrences de l’espacement unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="21782-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="21782-315">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="21782-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="21782-316">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-317">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="21782-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-319">float</span><span class="sxs-lookup"><span data-stu-id="21782-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-320">Densité de l’intervalle total à sens unique.</span><span class="sxs-lookup"><span data-stu-id="21782-320">Total one-way gap density.</span></span> <span data-ttu-id="21782-321">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="21782-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="21782-322">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-323">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="21782-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-325">float</span><span class="sxs-lookup"><span data-stu-id="21782-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-326">Durée totale de l’intervalle.</span><span class="sxs-lookup"><span data-stu-id="21782-326">Total one-way gap duration.</span></span> <span data-ttu-id="21782-327">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="21782-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="21782-328">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="21782-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="21782-329">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-331">float</span><span class="sxs-lookup"><span data-stu-id="21782-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-332">Pourcentage de l’appel décodé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="21782-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="21782-333">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-335">float</span><span class="sxs-lookup"><span data-stu-id="21782-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-336">Pourcentage de l’appel rendu en stéréo par l’suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="21782-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="21782-337">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="21782-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-339">float</span><span class="sxs-lookup"><span data-stu-id="21782-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-340">Taux de perte de paquets après application de la correction d’erreur de transfert.</span><span class="sxs-lookup"><span data-stu-id="21782-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="21782-341">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21782-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-343">float</span><span class="sxs-lookup"><span data-stu-id="21782-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-344">Pourcentage de l’appel encodé en stéréo.</span><span class="sxs-lookup"><span data-stu-id="21782-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="21782-345">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21782-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="21782-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="21782-347">float</span><span class="sxs-lookup"><span data-stu-id="21782-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21782-348">Pourcentage de l’appel capturé comme stéréo par l’suppresseur d’écho acoustique.</span><span class="sxs-lookup"><span data-stu-id="21782-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="21782-349">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21782-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

