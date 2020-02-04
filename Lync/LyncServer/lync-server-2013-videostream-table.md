---
title: 'Lync Server 2013 : Table VideoStream'
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
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="2d368-102">Table VideoStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d368-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d368-103">_**Dernière modification de la rubrique :** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="2d368-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="2d368-104">Chaque enregistrement représente un flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-104">Each record represents one video stream.</span></span> <span data-ttu-id="2d368-105">Une ligne de média vidéo contient généralement deux flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d368-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2d368-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2d368-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2d368-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d368-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2d368-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2d368-112">Principal</span><span class="sxs-lookup"><span data-stu-id="2d368-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d368-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2d368-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-115">int</span><span class="sxs-lookup"><span data-stu-id="2d368-115">int</span></span></p></td>
<td><p><span data-ttu-id="2d368-116">Principal</span><span class="sxs-lookup"><span data-stu-id="2d368-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d368-117">R référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2d368-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2d368-120">Principal</span><span class="sxs-lookup"><span data-stu-id="2d368-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d368-121">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2d368-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-123">int</span><span class="sxs-lookup"><span data-stu-id="2d368-123">int</span></span></p></td>
<td><p><span data-ttu-id="2d368-124">Principal</span><span class="sxs-lookup"><span data-stu-id="2d368-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d368-125">IDENTIFIant unique dans une ligne de médias.</span><span class="sxs-lookup"><span data-stu-id="2d368-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-127">type</span><span class="sxs-lookup"><span data-stu-id="2d368-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="2d368-128">Étranger, primaire</span><span class="sxs-lookup"><span data-stu-id="2d368-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="2d368-129">Description de la charge utile.</span><span class="sxs-lookup"><span data-stu-id="2d368-129">Payload description.</span></span> <span data-ttu-id="2d368-130">Pour plus d’informations, voir la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2d368-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-132">int</span><span class="sxs-lookup"><span data-stu-id="2d368-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-133">Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="2d368-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-135">int</span><span class="sxs-lookup"><span data-stu-id="2d368-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-136">Scintillement du réseau maximum lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-138">int</span><span class="sxs-lookup"><span data-stu-id="2d368-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-139">Durée de l’aller-retour des statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="2d368-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-141">int</span><span class="sxs-lookup"><span data-stu-id="2d368-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-142">Durée de l’aller-retour maximal pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-144">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-145">Taux moyen de perte de paquets lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-147">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-148">Perte de paquets maximum observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-150">int</span><span class="sxs-lookup"><span data-stu-id="2d368-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-151">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="2d368-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-152"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-153">int</span><span class="sxs-lookup"><span data-stu-id="2d368-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-154">Estimations de bande passante pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-156">car (9)</span><span class="sxs-lookup"><span data-stu-id="2d368-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-157">Résolution de la vidéo, en pixels, de largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="2d368-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="2d368-158">Signalée en tant que chaîne.</span><span class="sxs-lookup"><span data-stu-id="2d368-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-160">int</span><span class="sxs-lookup"><span data-stu-id="2d368-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-161">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-163">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-164">Fréquence d’images vidéo reçues.</span><span class="sxs-lookup"><span data-stu-id="2d368-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-166">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-167">Fréquence d’images vidéo envoyées.</span><span class="sxs-lookup"><span data-stu-id="2d368-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-169">int</span><span class="sxs-lookup"><span data-stu-id="2d368-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-170">Débit vidéo maximum lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-172">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-173">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="2d368-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-175">bit</span><span class="sxs-lookup"><span data-stu-id="2d368-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-176">Non disponible.</span><span class="sxs-lookup"><span data-stu-id="2d368-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-178">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-179">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="2d368-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-182">Pourcentage de l’appel à la résolution CAF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="2d368-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-185">Pourcentage de l’appel à la résolution VGA.</span><span class="sxs-lookup"><span data-stu-id="2d368-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-188">Pourcentage de l’appel passé à la résolution HD720.</span><span class="sxs-lookup"><span data-stu-id="2d368-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-191">Pourcentage de la durée de l’appel sans cadre.</span><span class="sxs-lookup"><span data-stu-id="2d368-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-194">Pourcentage de la durée de l’appel avec la dépose de l’image B.</span><span class="sxs-lookup"><span data-stu-id="2d368-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-197">Pourcentage de la durée de l’appel avec la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2d368-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-200">Pourcentage de la durée de l’appel avec BPSP Frame.</span><span class="sxs-lookup"><span data-stu-id="2d368-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="2d368-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-203">Pourcentage de la durée de l’appel avec BPSPI Frame.</span><span class="sxs-lookup"><span data-stu-id="2d368-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-204"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-205">bit</span><span class="sxs-lookup"><span data-stu-id="2d368-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-206">Des données de flux sur le côté du destinataire sont reçues.</span><span class="sxs-lookup"><span data-stu-id="2d368-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-207"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-208">bit</span><span class="sxs-lookup"><span data-stu-id="2d368-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-209">Les données du flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="2d368-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-211">bit</span><span class="sxs-lookup"><span data-stu-id="2d368-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2d368-212">1 signifie que le sens du flux provient de l’appelant vers l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="2d368-213">0 : le sens du flux provient de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="2d368-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-215">float</span><span class="sxs-lookup"><span data-stu-id="2d368-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-216">Indique le pourcentage du temps pendant lequel l’appel a été dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="2d368-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="2d368-217">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-219">float</span><span class="sxs-lookup"><span data-stu-id="2d368-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-220">Indique le pourcentage de l’appel au cours duquel une congestion est causée par le retard de paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="2d368-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="2d368-221">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-223">float</span><span class="sxs-lookup"><span data-stu-id="2d368-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-224">Indique le pourcentage de temps pendant lequel l’appel a été compétitif pour les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="2d368-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="2d368-225">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-227">int</span><span class="sxs-lookup"><span data-stu-id="2d368-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-228">Quantité minimale d’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2d368-229">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-231">int</span><span class="sxs-lookup"><span data-stu-id="2d368-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-232">Quantité maximale d’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2d368-233">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-235">int</span><span class="sxs-lookup"><span data-stu-id="2d368-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-236">Écart type de l’estimation de la bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2d368-237">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-239">int</span><span class="sxs-lookup"><span data-stu-id="2d368-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-240">Quantité moyenne d’estimation de bande passante mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2d368-241">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-243">float</span><span class="sxs-lookup"><span data-stu-id="2d368-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-244">Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau n’a pas pu prendre en charge la vidéo multivue.</span><span class="sxs-lookup"><span data-stu-id="2d368-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="2d368-245">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-247">float</span><span class="sxs-lookup"><span data-stu-id="2d368-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-248">Quantité totale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="2d368-248">Total amount of one-way latency.</span></span> <span data-ttu-id="2d368-249">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-250">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-251"><strong>Moyenne unidirectionnelle relative</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-252">float</span><span class="sxs-lookup"><span data-stu-id="2d368-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-253">Quantité moyenne de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="2d368-253">Average amount of one-way latency.</span></span> <span data-ttu-id="2d368-254">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-255">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-257">float</span><span class="sxs-lookup"><span data-stu-id="2d368-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-258">Quantité maximale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="2d368-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="2d368-259">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-260">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-262">int</span><span class="sxs-lookup"><span data-stu-id="2d368-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-263">Nombre total d’occurrences de rafales à sens unique.</span><span class="sxs-lookup"><span data-stu-id="2d368-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="2d368-264">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="2d368-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2d368-265">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-266">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-268">int</span><span class="sxs-lookup"><span data-stu-id="2d368-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-269">Densité du Burst total unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="2d368-269">Total one-way burst density.</span></span> <span data-ttu-id="2d368-270">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="2d368-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2d368-271">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-272">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-274">float</span><span class="sxs-lookup"><span data-stu-id="2d368-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-275">Durée totale du Burst.</span><span class="sxs-lookup"><span data-stu-id="2d368-275">Total one-way burst duration.</span></span> <span data-ttu-id="2d368-276">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="2d368-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2d368-277">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-278">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-280">int</span><span class="sxs-lookup"><span data-stu-id="2d368-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-281">Nombre total d’occurrences de l’espacement unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="2d368-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="2d368-282">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="2d368-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2d368-283">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-284">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-286">float</span><span class="sxs-lookup"><span data-stu-id="2d368-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-287">Densité de l’intervalle total à sens unique.</span><span class="sxs-lookup"><span data-stu-id="2d368-287">Total one-way gap density.</span></span> <span data-ttu-id="2d368-288">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="2d368-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2d368-289">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-290">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-292">float</span><span class="sxs-lookup"><span data-stu-id="2d368-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-293">Durée totale de l’intervalle.</span><span class="sxs-lookup"><span data-stu-id="2d368-293">Total one-way gap duration.</span></span> <span data-ttu-id="2d368-294">Une transmission « Burst » est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu ; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="2d368-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2d368-295">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d368-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2d368-296">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-297"><strong>Cause du taux</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-298">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="2d368-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-299">Taux d’interruption des paquets vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="2d368-300">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-302">int</span><span class="sxs-lookup"><span data-stu-id="2d368-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-303">Quantité moyenne de bande passante allouée pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="2d368-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="2d368-304">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-306">type</span><span class="sxs-lookup"><span data-stu-id="2d368-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="2d368-307">Externes</span><span class="sxs-lookup"><span data-stu-id="2d368-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2d368-308">Type de codecs vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="2d368-309">Pour plus d’informations, voir la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2d368-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2d368-310">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-312">int</span><span class="sxs-lookup"><span data-stu-id="2d368-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-313">Largeur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="2d368-314">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-316">int</span><span class="sxs-lookup"><span data-stu-id="2d368-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-317">Hauteur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="2d368-318">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-320">float</span><span class="sxs-lookup"><span data-stu-id="2d368-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-321">Transmission moyenne de la fréquence d’images vidéo utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="2d368-322">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-324">int</span><span class="sxs-lookup"><span data-stu-id="2d368-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-325">Taux de bits maximal pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="2d368-326">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-328">int</span><span class="sxs-lookup"><span data-stu-id="2d368-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-329">Taux de bits moyen pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-331">int</span><span class="sxs-lookup"><span data-stu-id="2d368-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-332">Nombre maximal de flux vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d368-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="2d368-333">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-335">type</span><span class="sxs-lookup"><span data-stu-id="2d368-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="2d368-336">Externes</span><span class="sxs-lookup"><span data-stu-id="2d368-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2d368-337">Codes vidéo utilisés par le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-337">Video codes used by the receiver.</span></span> <span data-ttu-id="2d368-338">Pour plus d’informations, voir la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2d368-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2d368-339">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-341">int</span><span class="sxs-lookup"><span data-stu-id="2d368-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-342">Largeur de résolution utilisée par le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="2d368-343">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-345">int</span><span class="sxs-lookup"><span data-stu-id="2d368-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-346">Hauteur de résolution utilisée par le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="2d368-347">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-348"><strong>Cause reçues</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-349">float</span><span class="sxs-lookup"><span data-stu-id="2d368-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-350">Fréquence d’images vidéo moyenne utilisée par le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="2d368-351">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-353">int</span><span class="sxs-lookup"><span data-stu-id="2d368-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-354">Vitesse de transmission maximale du destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="2d368-355">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-357">int</span><span class="sxs-lookup"><span data-stu-id="2d368-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-358">Taux de bits moyen pour le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="2d368-359">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-361">int</span><span class="sxs-lookup"><span data-stu-id="2d368-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-362">Flux vidéo maximal pour le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="2d368-363">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-365">int</span><span class="sxs-lookup"><span data-stu-id="2d368-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-366">Flux vidéo minimal pour le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="2d368-367">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-369">int</span><span class="sxs-lookup"><span data-stu-id="2d368-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-370">Mode vidéo (par exemple, Galerie ou flux unique) pour le destinataire.</span><span class="sxs-lookup"><span data-stu-id="2d368-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="2d368-371">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-373">float</span><span class="sxs-lookup"><span data-stu-id="2d368-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-374">Taux de perte de paquets après application de la correction d’erreur de transfert.</span><span class="sxs-lookup"><span data-stu-id="2d368-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="2d368-375">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-376"><strong>Cause du pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-377">float</span><span class="sxs-lookup"><span data-stu-id="2d368-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-378">Pourcentage de temps pendant lequel l’indicateur de capacité dynamique a été actif.</span><span class="sxs-lookup"><span data-stu-id="2d368-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="2d368-379">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-381">car (9)</span><span class="sxs-lookup"><span data-stu-id="2d368-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-382">Résolution minimale mesurée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="2d368-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="2d368-383">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-385">float</span><span class="sxs-lookup"><span data-stu-id="2d368-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-386">Pourcentage de l’appel inférieur au seuil de faible taux de bits (70 kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="2d368-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="2d368-387">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-388"><strong>Cause du pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-389">float</span><span class="sxs-lookup"><span data-stu-id="2d368-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-390">Pourcentage de l’appel inférieur au seuil de fréquence d’images faible (7,5 images par seconde, entrant).</span><span class="sxs-lookup"><span data-stu-id="2d368-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="2d368-391">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-392"><strong>Cause du pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-393">float</span><span class="sxs-lookup"><span data-stu-id="2d368-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-394">Pourcentage de l’appel qui s’est produit à la résolution la plus basse.</span><span class="sxs-lookup"><span data-stu-id="2d368-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="2d368-395">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="2d368-396">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d368-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-398">float</span><span class="sxs-lookup"><span data-stu-id="2d368-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-399">Durée de l’appel en secondes.</span><span class="sxs-lookup"><span data-stu-id="2d368-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="2d368-400">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d368-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="2d368-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="2d368-402">bit</span><span class="sxs-lookup"><span data-stu-id="2d368-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d368-403">Indique si les données ont été agrégées à partir de plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="2d368-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="2d368-404">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d368-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

