---
title: 'Tableau Lync Server 2013 : AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="26d29-102">Table AppSharingMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d29-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d29-103">_**Dernière modification de la rubrique :** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="26d29-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="26d29-104">La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="26d29-105">Ces seuils sont utilisés pour déterminer si l’utilisation du partage d’application doit être considérée comme médiocre.</span><span class="sxs-lookup"><span data-stu-id="26d29-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="26d29-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26d29-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="26d29-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="26d29-109"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="26d29-110"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26d29-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-112">int</span><span class="sxs-lookup"><span data-stu-id="26d29-112">int</span></span></p></td>
<td><p><span data-ttu-id="26d29-113">Principal</span><span class="sxs-lookup"><span data-stu-id="26d29-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="26d29-114">Type d’appel placé.</span><span class="sxs-lookup"><span data-stu-id="26d29-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-116">int</span><span class="sxs-lookup"><span data-stu-id="26d29-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-117">Limite maximale de bande passante pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="26d29-118">La valeur par défaut est 1 million.</span><span class="sxs-lookup"><span data-stu-id="26d29-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-120">int</span><span class="sxs-lookup"><span data-stu-id="26d29-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-121">Limitation de bande passante acceptable pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="26d29-122">La valeur par défaut est 500000.</span><span class="sxs-lookup"><span data-stu-id="26d29-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-124">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="26d29-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-125">Taux de pourcentage optimal pour les vignettes « abîmées » permettant de classer une qualité de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="26d29-126">Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="26d29-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="26d29-127">Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement.</span><span class="sxs-lookup"><span data-stu-id="26d29-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="26d29-128">La valeur par défaut est 11%.</span><span class="sxs-lookup"><span data-stu-id="26d29-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-130">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="26d29-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-131">taux de cceptable pour les vignettes « abîmées » permettant de classer une qualité de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="26d29-132">Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="26d29-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="26d29-133">Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement.</span><span class="sxs-lookup"><span data-stu-id="26d29-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="26d29-134">La valeur par défaut est 36%.</span><span class="sxs-lookup"><span data-stu-id="26d29-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-136">int</span><span class="sxs-lookup"><span data-stu-id="26d29-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-137">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-139">int</span><span class="sxs-lookup"><span data-stu-id="26d29-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-140">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-142">float</span><span class="sxs-lookup"><span data-stu-id="26d29-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-143">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-145">float</span><span class="sxs-lookup"><span data-stu-id="26d29-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-146">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-148">float</span><span class="sxs-lookup"><span data-stu-id="26d29-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-149">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-151">float</span><span class="sxs-lookup"><span data-stu-id="26d29-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-152">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-154">float</span><span class="sxs-lookup"><span data-stu-id="26d29-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-155">Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="26d29-156">Il s’agit d’une mesure de latence sur un seul tronçon.</span><span class="sxs-lookup"><span data-stu-id="26d29-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="26d29-157">La valeur par défaut est 1,0 secondes.</span><span class="sxs-lookup"><span data-stu-id="26d29-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="26d29-158">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-160">float</span><span class="sxs-lookup"><span data-stu-id="26d29-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-161">Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="26d29-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="26d29-162">Il s’agit d’une mesure de latence sur un seul tronçon.</span><span class="sxs-lookup"><span data-stu-id="26d29-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="26d29-163">La valeur par défaut est 1,75 secondes.</span><span class="sxs-lookup"><span data-stu-id="26d29-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="26d29-164">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d29-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-166">float</span><span class="sxs-lookup"><span data-stu-id="26d29-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-167">Valeur optimale de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage.</span><span class="sxs-lookup"><span data-stu-id="26d29-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="26d29-168">La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="26d29-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="26d29-169">Une moyenne élevée indique un délai plus long pour l’expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="26d29-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="26d29-170">Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.</span><span class="sxs-lookup"><span data-stu-id="26d29-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="26d29-171">La valeur par défaut est 200 millions.</span><span class="sxs-lookup"><span data-stu-id="26d29-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="26d29-172">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d29-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="26d29-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="26d29-174">float</span><span class="sxs-lookup"><span data-stu-id="26d29-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d29-175">Valeur acceptable de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage.</span><span class="sxs-lookup"><span data-stu-id="26d29-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="26d29-176">La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="26d29-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="26d29-177">Une moyenne élevée indique un délai plus long pour l’expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="26d29-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="26d29-178">Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.</span><span class="sxs-lookup"><span data-stu-id="26d29-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="26d29-179">La valeur par défaut est 200 millions.</span><span class="sxs-lookup"><span data-stu-id="26d29-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="26d29-180">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d29-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

