---
title: 'Lync Server 2013 : table VideoMetricsThreshold'
description: 'Lync Server 2013 : table VideoMetricsThreshold.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568000"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="2725c-103">Table VideoMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2725c-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2725c-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2725c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2725c-105">La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.</span><span class="sxs-lookup"><span data-stu-id="2725c-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2725c-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2725c-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2725c-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2725c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2725c-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-111">int</span><span class="sxs-lookup"><span data-stu-id="2725c-111">int</span></span></p></td>
<td><p><span data-ttu-id="2725c-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="2725c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2725c-113">Type d’appel passé.</span><span class="sxs-lookup"><span data-stu-id="2725c-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-115">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-116">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="2725c-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-118">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-119">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="2725c-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-121">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-122">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="2725c-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-124">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-125">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="2725c-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-127">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="2725c-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-128">La valeur par défaut est 12,0000.</span><span class="sxs-lookup"><span data-stu-id="2725c-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-130">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="2725c-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-131">La valeur par défaut est 7,0000.</span><span class="sxs-lookup"><span data-stu-id="2725c-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-133">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-134">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="2725c-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-136">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-137">La valeur par défaut est 10,0/</span><span class="sxs-lookup"><span data-stu-id="2725c-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-139">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-140">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="2725c-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-142">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-143">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="2725c-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-145">foat</span><span class="sxs-lookup"><span data-stu-id="2725c-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-146">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="2725c-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-148">float</span><span class="sxs-lookup"><span data-stu-id="2725c-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-149">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="2725c-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-151">float</span><span class="sxs-lookup"><span data-stu-id="2725c-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-152">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="2725c-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-154">float</span><span class="sxs-lookup"><span data-stu-id="2725c-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-155">La valeur par défaut est 7.</span><span class="sxs-lookup"><span data-stu-id="2725c-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2725c-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-157">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-158">La valeur par défaut est 5,00.</span><span class="sxs-lookup"><span data-stu-id="2725c-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2725c-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="2725c-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="2725c-160">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2725c-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2725c-161">La valeur par défaut est 10,00.</span><span class="sxs-lookup"><span data-stu-id="2725c-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

