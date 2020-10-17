---
title: 'Lync Server 2013 : table table Videostream'
description: 'Lync Server 2013 : table table Videostream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567990"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="b2199-103">Table table Videostream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2199-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2199-104">_**Dernière modification de la rubrique :** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="b2199-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="b2199-105">Chaque enregistrement représente un flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-105">Each record represents one video stream.</span></span> <span data-ttu-id="b2199-106">Une ligne de support vidéo contient généralement deux flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2199-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b2199-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b2199-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b2199-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2199-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b2199-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b2199-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="b2199-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2199-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b2199-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-116">int</span><span class="sxs-lookup"><span data-stu-id="b2199-116">int</span></span></p></td>
<td><p><span data-ttu-id="b2199-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="b2199-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2199-118">R référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b2199-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b2199-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="b2199-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2199-122">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b2199-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-124">int</span><span class="sxs-lookup"><span data-stu-id="b2199-124">int</span></span></p></td>
<td><p><span data-ttu-id="b2199-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="b2199-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2199-126">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="b2199-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-128">type</span><span class="sxs-lookup"><span data-stu-id="b2199-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="b2199-129">Étranger, primaire</span><span class="sxs-lookup"><span data-stu-id="b2199-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="b2199-130">Description de la charge utile.</span><span class="sxs-lookup"><span data-stu-id="b2199-130">Payload description.</span></span> <span data-ttu-id="b2199-131">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2199-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-133">int</span><span class="sxs-lookup"><span data-stu-id="b2199-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-134">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="b2199-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-136">int</span><span class="sxs-lookup"><span data-stu-id="b2199-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-137">Gigue réseau maximale pendant la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-138"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-139">int</span><span class="sxs-lookup"><span data-stu-id="b2199-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-140">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="b2199-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-142">int</span><span class="sxs-lookup"><span data-stu-id="b2199-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-143">Temps d’aller-retour maximal pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-145">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-146">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-148">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-149">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-151">int</span><span class="sxs-lookup"><span data-stu-id="b2199-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-152">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="b2199-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-153"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-154">int</span><span class="sxs-lookup"><span data-stu-id="b2199-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-155">Estimations de bande passante pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-157">Char (9)</span><span class="sxs-lookup"><span data-stu-id="b2199-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-158">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="b2199-158">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="b2199-159">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="b2199-159">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-161">int</span><span class="sxs-lookup"><span data-stu-id="b2199-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-162">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-164">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-165">Fréquence d’images vidéo reçues.</span><span class="sxs-lookup"><span data-stu-id="b2199-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-167">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-168">Fréquence d’images vidéo envoyées.</span><span class="sxs-lookup"><span data-stu-id="b2199-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-170">int</span><span class="sxs-lookup"><span data-stu-id="b2199-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-171">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-173">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-174">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="b2199-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-176">légèrement</span><span class="sxs-lookup"><span data-stu-id="b2199-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-177">Non disponible.</span><span class="sxs-lookup"><span data-stu-id="b2199-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-179">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-180">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="b2199-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-182">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-183">Pourcentage de l’appel qui était à la résolution CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="b2199-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-185">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-186">Pourcentage de l’appel qui était à la résolution VGA.</span><span class="sxs-lookup"><span data-stu-id="b2199-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-188">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-189">Pourcentage de l’appel qui était à la résolution HD720.</span><span class="sxs-lookup"><span data-stu-id="b2199-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-191">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-192">Pourcentage de la durée de l’appel sans dépose d’image.</span><span class="sxs-lookup"><span data-stu-id="b2199-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-194">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-195">Pourcentage de la durée de l’appel avec une suppression d’image B.</span><span class="sxs-lookup"><span data-stu-id="b2199-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-197">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-198">Pourcentage de la durée de l’appel avec l’image BP.</span><span class="sxs-lookup"><span data-stu-id="b2199-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-200">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-201">Pourcentage de la durée de l’appel avec l’image BPSP.</span><span class="sxs-lookup"><span data-stu-id="b2199-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="b2199-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-204">Pourcentage de la durée de l’appel avec l’image BPSPI.</span><span class="sxs-lookup"><span data-stu-id="b2199-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-205"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-206">légèrement</span><span class="sxs-lookup"><span data-stu-id="b2199-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-207">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="b2199-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-208"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-209">légèrement</span><span class="sxs-lookup"><span data-stu-id="b2199-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-210">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="b2199-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-212">légèrement</span><span class="sxs-lookup"><span data-stu-id="b2199-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b2199-213">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b2199-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="b2199-214">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b2199-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-216">float</span><span class="sxs-lookup"><span data-stu-id="b2199-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-217">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="b2199-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="b2199-218">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-220">float</span><span class="sxs-lookup"><span data-stu-id="b2199-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-221">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="b2199-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="b2199-222">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-224">float</span><span class="sxs-lookup"><span data-stu-id="b2199-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-225">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="b2199-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="b2199-226">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-228">int</span><span class="sxs-lookup"><span data-stu-id="b2199-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-229">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b2199-230">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-232">int</span><span class="sxs-lookup"><span data-stu-id="b2199-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-233">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b2199-234">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-236">int</span><span class="sxs-lookup"><span data-stu-id="b2199-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-237">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b2199-238">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-240">int</span><span class="sxs-lookup"><span data-stu-id="b2199-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-241">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b2199-242">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-244">float</span><span class="sxs-lookup"><span data-stu-id="b2199-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-245">Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo multivue.</span><span class="sxs-lookup"><span data-stu-id="b2199-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="b2199-246">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-248">float</span><span class="sxs-lookup"><span data-stu-id="b2199-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p104">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-251">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-253">float</span><span class="sxs-lookup"><span data-stu-id="b2199-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p105">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-256">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-258">float</span><span class="sxs-lookup"><span data-stu-id="b2199-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p106">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-261">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-263">int</span><span class="sxs-lookup"><span data-stu-id="b2199-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p107">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-267">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-269">int</span><span class="sxs-lookup"><span data-stu-id="b2199-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p108">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-273">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-275">float</span><span class="sxs-lookup"><span data-stu-id="b2199-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p109">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-279">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-281">int</span><span class="sxs-lookup"><span data-stu-id="b2199-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p110">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-285">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-287">float</span><span class="sxs-lookup"><span data-stu-id="b2199-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p111">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-291">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-293">float</span><span class="sxs-lookup"><span data-stu-id="b2199-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-p112">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2199-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b2199-297">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-299">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b2199-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-300">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="b2199-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="b2199-301">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-303">int</span><span class="sxs-lookup"><span data-stu-id="b2199-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-304">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="b2199-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="b2199-305">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-307">type</span><span class="sxs-lookup"><span data-stu-id="b2199-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="b2199-308">Etranger</span><span class="sxs-lookup"><span data-stu-id="b2199-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2199-309">Type de codecs vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="b2199-310">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2199-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b2199-311">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-313">int</span><span class="sxs-lookup"><span data-stu-id="b2199-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-314">Largeur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="b2199-315">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-317">int</span><span class="sxs-lookup"><span data-stu-id="b2199-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-318">Hauteur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="b2199-319">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-321">float</span><span class="sxs-lookup"><span data-stu-id="b2199-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-322">Fréquence d’images vidéo moyenne utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="b2199-323">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-325">int</span><span class="sxs-lookup"><span data-stu-id="b2199-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-326">Vitesse de transmission maximale pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="b2199-327">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-329">int</span><span class="sxs-lookup"><span data-stu-id="b2199-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-330">Vitesse de transmission moyenne pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-332">int</span><span class="sxs-lookup"><span data-stu-id="b2199-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-333">Nombre maximal de flux vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="b2199-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="b2199-334">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-336">type</span><span class="sxs-lookup"><span data-stu-id="b2199-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="b2199-337">Etranger</span><span class="sxs-lookup"><span data-stu-id="b2199-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2199-338">Codes vidéo utilisés par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-338">Video codes used by the receiver.</span></span> <span data-ttu-id="b2199-339">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b2199-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b2199-340">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-342">int</span><span class="sxs-lookup"><span data-stu-id="b2199-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-343">Largeur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="b2199-344">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-346">int</span><span class="sxs-lookup"><span data-stu-id="b2199-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-347">Hauteur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="b2199-348">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-350">float</span><span class="sxs-lookup"><span data-stu-id="b2199-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-351">Fréquence d’images vidéo moyenne utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="b2199-352">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-354">int</span><span class="sxs-lookup"><span data-stu-id="b2199-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-355">Vitesse de transmission maximale pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="b2199-356">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-358">int</span><span class="sxs-lookup"><span data-stu-id="b2199-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-359">Vitesse de transmission moyenne pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="b2199-360">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-362">int</span><span class="sxs-lookup"><span data-stu-id="b2199-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-363">Nombre maximal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="b2199-364">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-366">int</span><span class="sxs-lookup"><span data-stu-id="b2199-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-367">Nombre minimal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="b2199-368">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-370">int</span><span class="sxs-lookup"><span data-stu-id="b2199-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-371">Mode vidéo (par exemple, Galerie ou flux unique) pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="b2199-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="b2199-372">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-374">float</span><span class="sxs-lookup"><span data-stu-id="b2199-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-375">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="b2199-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="b2199-376">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-378">float</span><span class="sxs-lookup"><span data-stu-id="b2199-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-379">Pourcentage de temps pendant lequel l’indicateur de capacité dynamique était actif.</span><span class="sxs-lookup"><span data-stu-id="b2199-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="b2199-380">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-382">Char (9)</span><span class="sxs-lookup"><span data-stu-id="b2199-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-383">Résolution minimale mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2199-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="b2199-384">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-386">float</span><span class="sxs-lookup"><span data-stu-id="b2199-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-387">Pourcentage de l’appel sous le seuil de taux de bits bas (70 kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="b2199-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="b2199-388">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-390">float</span><span class="sxs-lookup"><span data-stu-id="b2199-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-391">Pourcentage de l’appel en dessous du seuil de fréquence d’images faible (7,5 images par seconde, entrantes).</span><span class="sxs-lookup"><span data-stu-id="b2199-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="b2199-392">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-394">float</span><span class="sxs-lookup"><span data-stu-id="b2199-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-395">Pourcentage de l’appel qui s’est produit à la résolution la plus faible.</span><span class="sxs-lookup"><span data-stu-id="b2199-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="b2199-396">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="b2199-397">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2199-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-399">float</span><span class="sxs-lookup"><span data-stu-id="b2199-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-400">Longueur de l’appel en secondes.</span><span class="sxs-lookup"><span data-stu-id="b2199-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="b2199-401">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2199-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="b2199-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="b2199-403">légèrement</span><span class="sxs-lookup"><span data-stu-id="b2199-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2199-404">Indique si les données ont été regroupées à partir de plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="b2199-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="b2199-405">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2199-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

