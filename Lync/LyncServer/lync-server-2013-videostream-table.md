---
title: 'Lync Server 2013 : table table Videostream'
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
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518561"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="53a50-102">Table table Videostream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a50-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a50-103">_**Dernière modification de la rubrique :** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="53a50-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="53a50-104">Chaque enregistrement représente un flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-104">Each record represents one video stream.</span></span> <span data-ttu-id="53a50-105">Une ligne de support vidéo contient généralement deux flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53a50-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="53a50-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="53a50-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="53a50-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a50-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="53a50-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a50-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="53a50-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="53a50-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53a50-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-115">int</span><span class="sxs-lookup"><span data-stu-id="53a50-115">int</span></span></p></td>
<td><p><span data-ttu-id="53a50-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="53a50-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="53a50-117">R référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53a50-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="53a50-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="53a50-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="53a50-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="53a50-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-123">int</span><span class="sxs-lookup"><span data-stu-id="53a50-123">int</span></span></p></td>
<td><p><span data-ttu-id="53a50-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="53a50-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="53a50-125">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="53a50-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-127">type</span><span class="sxs-lookup"><span data-stu-id="53a50-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a50-128">Étranger, primaire</span><span class="sxs-lookup"><span data-stu-id="53a50-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="53a50-129">Description de la charge utile.</span><span class="sxs-lookup"><span data-stu-id="53a50-129">Payload description.</span></span> <span data-ttu-id="53a50-130">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53a50-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-132">int</span><span class="sxs-lookup"><span data-stu-id="53a50-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-133">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="53a50-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-135">int</span><span class="sxs-lookup"><span data-stu-id="53a50-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-136">Gigue réseau maximale pendant la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-137"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-138">int</span><span class="sxs-lookup"><span data-stu-id="53a50-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-139">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="53a50-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-141">int</span><span class="sxs-lookup"><span data-stu-id="53a50-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-142">Temps d’aller-retour maximal pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-144">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-145">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-147">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-148">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-150">int</span><span class="sxs-lookup"><span data-stu-id="53a50-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-151">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="53a50-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-152"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-153">int</span><span class="sxs-lookup"><span data-stu-id="53a50-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-154">Estimations de bande passante pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-156">Char (9)</span><span class="sxs-lookup"><span data-stu-id="53a50-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-157">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="53a50-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="53a50-158">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="53a50-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-160">int</span><span class="sxs-lookup"><span data-stu-id="53a50-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-161">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-163">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-164">Fréquence d’images vidéo reçues.</span><span class="sxs-lookup"><span data-stu-id="53a50-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-166">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-167">Fréquence d’images vidéo envoyées.</span><span class="sxs-lookup"><span data-stu-id="53a50-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-169">int</span><span class="sxs-lookup"><span data-stu-id="53a50-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-170">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-172">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-173">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="53a50-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-175">légèrement</span><span class="sxs-lookup"><span data-stu-id="53a50-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-176">Non disponible.</span><span class="sxs-lookup"><span data-stu-id="53a50-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-178">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-179">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="53a50-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-181">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-182">Pourcentage de l’appel qui était à la résolution CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="53a50-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-184">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-185">Pourcentage de l’appel qui était à la résolution VGA.</span><span class="sxs-lookup"><span data-stu-id="53a50-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-187">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-188">Pourcentage de l’appel qui était à la résolution HD720.</span><span class="sxs-lookup"><span data-stu-id="53a50-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-190">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-191">Pourcentage de la durée de l’appel sans dépose d’image.</span><span class="sxs-lookup"><span data-stu-id="53a50-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-193">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-194">Pourcentage de la durée de l’appel avec une suppression d’image B.</span><span class="sxs-lookup"><span data-stu-id="53a50-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-196">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-197">Pourcentage de la durée de l’appel avec l’image BP.</span><span class="sxs-lookup"><span data-stu-id="53a50-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-199">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-200">Pourcentage de la durée de l’appel avec l’image BPSP.</span><span class="sxs-lookup"><span data-stu-id="53a50-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-202">entier très petit</span><span class="sxs-lookup"><span data-stu-id="53a50-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-203">Pourcentage de la durée de l’appel avec l’image BPSPI.</span><span class="sxs-lookup"><span data-stu-id="53a50-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-204"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-205">légèrement</span><span class="sxs-lookup"><span data-stu-id="53a50-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-206">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="53a50-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-207"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-208">légèrement</span><span class="sxs-lookup"><span data-stu-id="53a50-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-209">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="53a50-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-211">légèrement</span><span class="sxs-lookup"><span data-stu-id="53a50-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="53a50-212">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="53a50-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="53a50-213">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="53a50-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-215">float</span><span class="sxs-lookup"><span data-stu-id="53a50-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-216">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="53a50-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="53a50-217">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-219">float</span><span class="sxs-lookup"><span data-stu-id="53a50-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-220">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="53a50-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="53a50-221">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-223">float</span><span class="sxs-lookup"><span data-stu-id="53a50-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-224">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="53a50-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="53a50-225">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-227">int</span><span class="sxs-lookup"><span data-stu-id="53a50-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-228">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="53a50-229">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-231">int</span><span class="sxs-lookup"><span data-stu-id="53a50-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-232">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="53a50-233">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-235">int</span><span class="sxs-lookup"><span data-stu-id="53a50-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-236">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="53a50-237">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-239">int</span><span class="sxs-lookup"><span data-stu-id="53a50-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-240">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="53a50-241">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-243">float</span><span class="sxs-lookup"><span data-stu-id="53a50-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-244">Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo multivue.</span><span class="sxs-lookup"><span data-stu-id="53a50-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="53a50-245">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-247">float</span><span class="sxs-lookup"><span data-stu-id="53a50-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p104">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-250">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-252">float</span><span class="sxs-lookup"><span data-stu-id="53a50-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p105">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-255">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-257">float</span><span class="sxs-lookup"><span data-stu-id="53a50-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p106">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-260">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-262">int</span><span class="sxs-lookup"><span data-stu-id="53a50-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p107">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-266">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-268">int</span><span class="sxs-lookup"><span data-stu-id="53a50-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p108">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-272">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-274">float</span><span class="sxs-lookup"><span data-stu-id="53a50-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p109">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-278">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-280">int</span><span class="sxs-lookup"><span data-stu-id="53a50-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p110">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-284">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-286">float</span><span class="sxs-lookup"><span data-stu-id="53a50-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p111">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-290">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-292">float</span><span class="sxs-lookup"><span data-stu-id="53a50-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-p112">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="53a50-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="53a50-296">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-298">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="53a50-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-299">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="53a50-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="53a50-300">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-302">int</span><span class="sxs-lookup"><span data-stu-id="53a50-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-303">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="53a50-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="53a50-304">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-306">type</span><span class="sxs-lookup"><span data-stu-id="53a50-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a50-307">Etranger</span><span class="sxs-lookup"><span data-stu-id="53a50-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53a50-308">Type de codecs vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="53a50-309">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53a50-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="53a50-310">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-312">int</span><span class="sxs-lookup"><span data-stu-id="53a50-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-313">Largeur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="53a50-314">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-316">int</span><span class="sxs-lookup"><span data-stu-id="53a50-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-317">Hauteur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="53a50-318">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-320">float</span><span class="sxs-lookup"><span data-stu-id="53a50-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-321">Fréquence d’images vidéo moyenne utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="53a50-322">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-324">int</span><span class="sxs-lookup"><span data-stu-id="53a50-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-325">Vitesse de transmission maximale pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="53a50-326">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-328">int</span><span class="sxs-lookup"><span data-stu-id="53a50-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-329">Vitesse de transmission moyenne pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-331">int</span><span class="sxs-lookup"><span data-stu-id="53a50-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-332">Nombre maximal de flux vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="53a50-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="53a50-333">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-335">type</span><span class="sxs-lookup"><span data-stu-id="53a50-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a50-336">Etranger</span><span class="sxs-lookup"><span data-stu-id="53a50-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53a50-337">Codes vidéo utilisés par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-337">Video codes used by the receiver.</span></span> <span data-ttu-id="53a50-338">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="53a50-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="53a50-339">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-341">int</span><span class="sxs-lookup"><span data-stu-id="53a50-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-342">Largeur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="53a50-343">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-345">int</span><span class="sxs-lookup"><span data-stu-id="53a50-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-346">Hauteur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="53a50-347">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-349">float</span><span class="sxs-lookup"><span data-stu-id="53a50-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-350">Fréquence d’images vidéo moyenne utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="53a50-351">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-353">int</span><span class="sxs-lookup"><span data-stu-id="53a50-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-354">Vitesse de transmission maximale pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="53a50-355">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-357">int</span><span class="sxs-lookup"><span data-stu-id="53a50-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-358">Vitesse de transmission moyenne pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="53a50-359">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-361">int</span><span class="sxs-lookup"><span data-stu-id="53a50-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-362">Nombre maximal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="53a50-363">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-365">int</span><span class="sxs-lookup"><span data-stu-id="53a50-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-366">Nombre minimal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="53a50-367">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-369">int</span><span class="sxs-lookup"><span data-stu-id="53a50-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-370">Mode vidéo (par exemple, Galerie ou flux unique) pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="53a50-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="53a50-371">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-373">float</span><span class="sxs-lookup"><span data-stu-id="53a50-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-374">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="53a50-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="53a50-375">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-377">float</span><span class="sxs-lookup"><span data-stu-id="53a50-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-378">Pourcentage de temps pendant lequel l’indicateur de capacité dynamique était actif.</span><span class="sxs-lookup"><span data-stu-id="53a50-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="53a50-379">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-381">Char (9)</span><span class="sxs-lookup"><span data-stu-id="53a50-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-382">Résolution minimale mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="53a50-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="53a50-383">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-385">float</span><span class="sxs-lookup"><span data-stu-id="53a50-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-386">Pourcentage de l’appel sous le seuil de taux de bits bas (70 kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="53a50-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="53a50-387">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-389">float</span><span class="sxs-lookup"><span data-stu-id="53a50-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-390">Pourcentage de l’appel en dessous du seuil de fréquence d’images faible (7,5 images par seconde, entrantes).</span><span class="sxs-lookup"><span data-stu-id="53a50-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="53a50-391">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-393">float</span><span class="sxs-lookup"><span data-stu-id="53a50-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-394">Pourcentage de l’appel qui s’est produit à la résolution la plus faible.</span><span class="sxs-lookup"><span data-stu-id="53a50-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="53a50-395">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="53a50-396">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a50-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-398">float</span><span class="sxs-lookup"><span data-stu-id="53a50-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-399">Longueur de l’appel en secondes.</span><span class="sxs-lookup"><span data-stu-id="53a50-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="53a50-400">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a50-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="53a50-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="53a50-402">légèrement</span><span class="sxs-lookup"><span data-stu-id="53a50-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53a50-403">Indique si les données ont été regroupées à partir de plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="53a50-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="53a50-404">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a50-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

