---
title: 'Lync Server 2013 : table AppSharingMetricsThreshold'
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
ms.openlocfilehash: 6e7a2d73f09a3cb48b1d50f06aa530c91d779b28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529551"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="604b7-102">Table AppSharingMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604b7-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="604b7-103">_**Dernière modification de la rubrique :** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="604b7-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="604b7-p101">La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables des mesures de qualité de l’expérience (QoE) utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’expérience de partage d’application doit être qualifiée de médiocre.</span><span class="sxs-lookup"><span data-stu-id="604b7-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="604b7-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="604b7-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="604b7-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="604b7-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="604b7-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="604b7-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-112">int</span><span class="sxs-lookup"><span data-stu-id="604b7-112">int</span></span></p></td>
<td><p><span data-ttu-id="604b7-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="604b7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="604b7-114">Type d’appel passé.</span><span class="sxs-lookup"><span data-stu-id="604b7-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-116">int</span><span class="sxs-lookup"><span data-stu-id="604b7-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p102">Limite de bande passante optimale pour le partage d’application. La valeur par défaut est 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="604b7-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-120">int</span><span class="sxs-lookup"><span data-stu-id="604b7-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p103">Limite de bande passante acceptable pour le partage d’application. La valeur par défaut est 500 000.</span><span class="sxs-lookup"><span data-stu-id="604b7-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-124">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="604b7-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p104">Pourcentage optimal de mosaïques altérées pour la classification de la qualité d’un partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 11.</span><span class="sxs-lookup"><span data-stu-id="604b7-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-130">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="604b7-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p105">Pourcentage acceptable de mosaïques altérées pour la classification de la qualité d’un partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 36.</span><span class="sxs-lookup"><span data-stu-id="604b7-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-136">int</span><span class="sxs-lookup"><span data-stu-id="604b7-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-137">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-139">int</span><span class="sxs-lookup"><span data-stu-id="604b7-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-140">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-142">float</span><span class="sxs-lookup"><span data-stu-id="604b7-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-143">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-145">float</span><span class="sxs-lookup"><span data-stu-id="604b7-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-146">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-148">float</span><span class="sxs-lookup"><span data-stu-id="604b7-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-149">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-151">float</span><span class="sxs-lookup"><span data-stu-id="604b7-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-152">Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-154">float</span><span class="sxs-lookup"><span data-stu-id="604b7-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p106">Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 seconde.</span><span class="sxs-lookup"><span data-stu-id="604b7-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="604b7-158">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-160">float</span><span class="sxs-lookup"><span data-stu-id="604b7-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-p107">Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 s.</span><span class="sxs-lookup"><span data-stu-id="604b7-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="604b7-164">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="604b7-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-166">float</span><span class="sxs-lookup"><span data-stu-id="604b7-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-167">Valeur optimale de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage.</span><span class="sxs-lookup"><span data-stu-id="604b7-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="604b7-168">La latence est l’intervalle de temps entre le moment où le cadre de démarrage est encodé sur le serveur (partagé ou MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="604b7-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="604b7-p109">Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.</span><span class="sxs-lookup"><span data-stu-id="604b7-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="604b7-172">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="604b7-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="604b7-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="604b7-174">float</span><span class="sxs-lookup"><span data-stu-id="604b7-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="604b7-175">Valeur acceptable de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage.</span><span class="sxs-lookup"><span data-stu-id="604b7-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="604b7-176">La latence est l’intervalle de temps entre le moment où le cadre de démarrage est encodé sur le serveur (partagé ou MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="604b7-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="604b7-p111">Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.</span><span class="sxs-lookup"><span data-stu-id="604b7-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="604b7-180">La colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b7-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

