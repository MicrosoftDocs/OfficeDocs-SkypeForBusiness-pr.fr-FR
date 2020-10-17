---
title: 'Lync Server 2013 : table VideoMetricsThreshold'
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
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508511"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="86875-102">Table VideoMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86875-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86875-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="86875-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="86875-104">La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.</span><span class="sxs-lookup"><span data-stu-id="86875-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86875-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="86875-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="86875-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="86875-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="86875-107"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="86875-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="86875-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="86875-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86875-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="86875-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-110">int</span><span class="sxs-lookup"><span data-stu-id="86875-110">int</span></span></p></td>
<td><p><span data-ttu-id="86875-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="86875-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="86875-112">Type d’appel passé.</span><span class="sxs-lookup"><span data-stu-id="86875-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-114">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-115">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="86875-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-117">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-118">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="86875-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-120">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-121">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="86875-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-123">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-124">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="86875-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-126">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86875-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-127">La valeur par défaut est 12,0000.</span><span class="sxs-lookup"><span data-stu-id="86875-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-129">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86875-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-130">La valeur par défaut est 7,0000.</span><span class="sxs-lookup"><span data-stu-id="86875-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-132">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-133">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="86875-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-135">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-136">La valeur par défaut est 10,0/</span><span class="sxs-lookup"><span data-stu-id="86875-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-138">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-139">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="86875-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-141">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-142">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="86875-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-144">foat</span><span class="sxs-lookup"><span data-stu-id="86875-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-145">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="86875-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-147">float</span><span class="sxs-lookup"><span data-stu-id="86875-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-148">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="86875-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-150">float</span><span class="sxs-lookup"><span data-stu-id="86875-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-151">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="86875-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-153">float</span><span class="sxs-lookup"><span data-stu-id="86875-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-154">La valeur par défaut est 7.</span><span class="sxs-lookup"><span data-stu-id="86875-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86875-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="86875-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-156">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-157">La valeur par défaut est 5,00.</span><span class="sxs-lookup"><span data-stu-id="86875-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86875-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="86875-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="86875-159">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="86875-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86875-160">La valeur par défaut est 10,00.</span><span class="sxs-lookup"><span data-stu-id="86875-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

