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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="17f0b-102">Table table Videostream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17f0b-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17f0b-103">_**Dernière modification de la rubrique :** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="17f0b-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="17f0b-104">Chaque enregistrement représente un flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-104">Each record represents one video stream.</span></span> <span data-ttu-id="17f0b-105">Une ligne de support vidéo contient généralement deux flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17f0b-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="17f0b-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="17f0b-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="17f0b-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17f0b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="17f0b-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f0b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="17f0b-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17f0b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-115">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-115">int</span></span></p></td>
<td><p><span data-ttu-id="17f0b-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f0b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="17f0b-117">R référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17f0b-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="17f0b-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f0b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="17f0b-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17f0b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-123">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-123">int</span></span></p></td>
<td><p><span data-ttu-id="17f0b-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="17f0b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="17f0b-125">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="17f0b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-127">type</span><span class="sxs-lookup"><span data-stu-id="17f0b-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="17f0b-128">Étranger, primaire</span><span class="sxs-lookup"><span data-stu-id="17f0b-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="17f0b-129">Description de la charge utile.</span><span class="sxs-lookup"><span data-stu-id="17f0b-129">Payload description.</span></span> <span data-ttu-id="17f0b-130">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f0b-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-132">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-133">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="17f0b-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-135">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-136">Gigue réseau maximale pendant la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-137"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-138">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-139">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="17f0b-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-141">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-142">Temps d’aller-retour maximal pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-144">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-145">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-147">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-148">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-150">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-151">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="17f0b-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-152"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-153">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-154">Estimations de bande passante pour le flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-156">Char (9)</span><span class="sxs-lookup"><span data-stu-id="17f0b-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-157">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="17f0b-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="17f0b-158">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="17f0b-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-160">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-161">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-163">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-164">Fréquence d’images vidéo reçues.</span><span class="sxs-lookup"><span data-stu-id="17f0b-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-166">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-167">Fréquence d’images vidéo envoyées.</span><span class="sxs-lookup"><span data-stu-id="17f0b-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-169">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-170">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-172">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-173">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="17f0b-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-175">légèrement</span><span class="sxs-lookup"><span data-stu-id="17f0b-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-176">Non disponible.</span><span class="sxs-lookup"><span data-stu-id="17f0b-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-178">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-179">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="17f0b-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-181">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-182">Pourcentage de l’appel qui était à la résolution CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="17f0b-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-184">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-185">Pourcentage de l’appel qui était à la résolution VGA.</span><span class="sxs-lookup"><span data-stu-id="17f0b-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-187">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-188">Pourcentage de l’appel qui était à la résolution HD720.</span><span class="sxs-lookup"><span data-stu-id="17f0b-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-190">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-191">Pourcentage de la durée de l’appel sans dépose d’image.</span><span class="sxs-lookup"><span data-stu-id="17f0b-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-193">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-194">Pourcentage de la durée de l’appel avec une suppression d’image B.</span><span class="sxs-lookup"><span data-stu-id="17f0b-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-196">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-197">Pourcentage de la durée de l’appel avec l’image BP.</span><span class="sxs-lookup"><span data-stu-id="17f0b-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-199">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-200">Pourcentage de la durée de l’appel avec l’image BPSP.</span><span class="sxs-lookup"><span data-stu-id="17f0b-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-202">entier très petit</span><span class="sxs-lookup"><span data-stu-id="17f0b-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-203">Pourcentage de la durée de l’appel avec l’image BPSPI.</span><span class="sxs-lookup"><span data-stu-id="17f0b-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-204"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-205">légèrement</span><span class="sxs-lookup"><span data-stu-id="17f0b-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-206">Les données de flux du côté récepteur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="17f0b-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-207"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-208">légèrement</span><span class="sxs-lookup"><span data-stu-id="17f0b-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-209">Les données de flux du côté de l’expéditeur sont reçues.</span><span class="sxs-lookup"><span data-stu-id="17f0b-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-211">légèrement</span><span class="sxs-lookup"><span data-stu-id="17f0b-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17f0b-212">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="17f0b-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="17f0b-213">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="17f0b-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-215">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-216">Indique le pourcentage de temps pendant lequel l’appel se trouve dans un état de congestion de perte.</span><span class="sxs-lookup"><span data-stu-id="17f0b-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="17f0b-217">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-219">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-220">Indique le pourcentage de l’appel pendant lequel la congestion a été causée par le retard de l’arrivée des paquets réseau.</span><span class="sxs-lookup"><span data-stu-id="17f0b-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="17f0b-221">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-223">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-224">Indique le pourcentage de temps pendant lequel l’appel a eu accès aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="17f0b-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="17f0b-225">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-227">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-228">Quantité minimale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="17f0b-229">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-231">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-232">Quantité maximale d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="17f0b-233">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-235">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-236">Écart-type de l’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="17f0b-237">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-239">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-240">Quantité moyenne d’estimation de bande passante mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="17f0b-241">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-243">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-244">Pourcentage de l’appel où le point de terminaison a déterminé que la connexion réseau ne pouvait pas prendre en charge la vidéo multivue.</span><span class="sxs-lookup"><span data-stu-id="17f0b-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="17f0b-245">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-247">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p104">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-250">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-252">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p105">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-255">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-257">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p106">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-260">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-262">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p107">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-266">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-268">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p108">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-272">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-274">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p109">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-278">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-280">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p110">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-284">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-286">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p111">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-290">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-292">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-p112">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="17f0b-296">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-298">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="17f0b-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-299">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="17f0b-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="17f0b-300">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-302">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-303">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="17f0b-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="17f0b-304">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-306">type</span><span class="sxs-lookup"><span data-stu-id="17f0b-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="17f0b-307">Etranger</span><span class="sxs-lookup"><span data-stu-id="17f0b-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17f0b-308">Type de codecs vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="17f0b-309">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f0b-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="17f0b-310">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-312">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-313">Largeur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="17f0b-314">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-316">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-317">Hauteur de résolution utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="17f0b-318">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-320">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-321">Fréquence d’images vidéo moyenne utilisée par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="17f0b-322">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-324">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-325">Vitesse de transmission maximale pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="17f0b-326">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-328">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-329">Vitesse de transmission moyenne pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-331">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-332">Nombre maximal de flux vidéo utilisés par l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="17f0b-333">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-335">type</span><span class="sxs-lookup"><span data-stu-id="17f0b-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="17f0b-336">Etranger</span><span class="sxs-lookup"><span data-stu-id="17f0b-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17f0b-337">Codes vidéo utilisés par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-337">Video codes used by the receiver.</span></span> <span data-ttu-id="17f0b-338">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-codecdescription-table.md">table CodecDescription dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f0b-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="17f0b-339">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-341">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-342">Largeur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-343">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-345">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-346">Hauteur de résolution utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-347">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-349">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-350">Fréquence d’images vidéo moyenne utilisée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-351">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-353">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-354">Vitesse de transmission maximale pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-355">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-357">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-358">Vitesse de transmission moyenne pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-359">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-361">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-362">Nombre maximal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-363">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-365">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-366">Nombre minimal de flux vidéo pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-367">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-369">int</span><span class="sxs-lookup"><span data-stu-id="17f0b-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-370">Mode vidéo (par exemple, Galerie ou flux unique) pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="17f0b-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="17f0b-371">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-373">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-374">Taux de perte de paquets après la correction des erreurs de transfert a été appliquée.</span><span class="sxs-lookup"><span data-stu-id="17f0b-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="17f0b-375">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-377">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-378">Pourcentage de temps pendant lequel l’indicateur de capacité dynamique était actif.</span><span class="sxs-lookup"><span data-stu-id="17f0b-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="17f0b-379">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-381">Char (9)</span><span class="sxs-lookup"><span data-stu-id="17f0b-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-382">Résolution minimale mesurée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="17f0b-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="17f0b-383">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-385">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-386">Pourcentage de l’appel sous le seuil de taux de bits bas (70 kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="17f0b-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="17f0b-387">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-389">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-390">Pourcentage de l’appel en dessous du seuil de fréquence d’images faible (7,5 images par seconde, entrantes).</span><span class="sxs-lookup"><span data-stu-id="17f0b-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="17f0b-391">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-393">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-394">Pourcentage de l’appel qui s’est produit à la résolution la plus faible.</span><span class="sxs-lookup"><span data-stu-id="17f0b-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="17f0b-395">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="17f0b-396">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f0b-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-398">flottant</span><span class="sxs-lookup"><span data-stu-id="17f0b-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-399">Longueur de l’appel en secondes.</span><span class="sxs-lookup"><span data-stu-id="17f0b-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="17f0b-400">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f0b-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="17f0b-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="17f0b-402">légèrement</span><span class="sxs-lookup"><span data-stu-id="17f0b-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f0b-403">Indique si les données ont été regroupées à partir de plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="17f0b-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="17f0b-404">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17f0b-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

