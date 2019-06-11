---
title: 'Tableau Lync Server 2013: VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="15b66-102">Table VideoMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b66-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b66-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="15b66-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="15b66-104">La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité de l’utilisation des appels vidéo.</span><span class="sxs-lookup"><span data-stu-id="15b66-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15b66-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="15b66-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="15b66-107"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="15b66-108"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15b66-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-110">int</span><span class="sxs-lookup"><span data-stu-id="15b66-110">int</span></span></p></td>
<td><p><span data-ttu-id="15b66-111">Principal</span><span class="sxs-lookup"><span data-stu-id="15b66-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="15b66-112">Type d’appel placé.</span><span class="sxs-lookup"><span data-stu-id="15b66-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-114">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-115">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="15b66-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-117">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-118">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="15b66-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-120">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-121">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="15b66-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-123">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-124">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="15b66-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-126">décimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="15b66-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-127">La valeur par défaut est 12,0000.</span><span class="sxs-lookup"><span data-stu-id="15b66-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-129">décimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="15b66-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-130">La valeur par défaut est 7,0000.</span><span class="sxs-lookup"><span data-stu-id="15b66-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-132">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-133">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="15b66-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-135">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-136">La valeur par défaut est 10.0/</span><span class="sxs-lookup"><span data-stu-id="15b66-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-138">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-139">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="15b66-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-141">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-142">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="15b66-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-144">foat</span><span class="sxs-lookup"><span data-stu-id="15b66-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-145">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="15b66-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-147">float</span><span class="sxs-lookup"><span data-stu-id="15b66-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-148">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="15b66-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-150">float</span><span class="sxs-lookup"><span data-stu-id="15b66-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-151">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="15b66-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-153">float</span><span class="sxs-lookup"><span data-stu-id="15b66-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-154">La valeur par défaut est 7.</span><span class="sxs-lookup"><span data-stu-id="15b66-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b66-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-156">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-157">La valeur par défaut est 5,00.</span><span class="sxs-lookup"><span data-stu-id="15b66-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b66-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="15b66-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="15b66-159">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="15b66-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15b66-160">La valeur par défaut est 10,00.</span><span class="sxs-lookup"><span data-stu-id="15b66-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

