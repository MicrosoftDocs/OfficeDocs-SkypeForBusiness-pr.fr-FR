---
title: 'Tableau Lync Server 2013 : VideoMetricsThreshold'
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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="6fa16-102">Table VideoMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fa16-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fa16-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6fa16-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6fa16-104">La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité de l’utilisation des appels vidéo.</span><span class="sxs-lookup"><span data-stu-id="6fa16-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fa16-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6fa16-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6fa16-107"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6fa16-108"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-110">int</span><span class="sxs-lookup"><span data-stu-id="6fa16-110">int</span></span></p></td>
<td><p><span data-ttu-id="6fa16-111">Principal</span><span class="sxs-lookup"><span data-stu-id="6fa16-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="6fa16-112">Type d’appel placé.</span><span class="sxs-lookup"><span data-stu-id="6fa16-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-114">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-115">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="6fa16-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-117">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-118">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="6fa16-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-120">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-121">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="6fa16-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-123">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-124">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="6fa16-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-126">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="6fa16-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-127">La valeur par défaut est 12,0000.</span><span class="sxs-lookup"><span data-stu-id="6fa16-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-129">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="6fa16-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-130">La valeur par défaut est 7,0000.</span><span class="sxs-lookup"><span data-stu-id="6fa16-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-132">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-133">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="6fa16-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-135">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-136">La valeur par défaut est 10.0/</span><span class="sxs-lookup"><span data-stu-id="6fa16-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-138">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-139">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="6fa16-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-141">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-142">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="6fa16-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-144">foat</span><span class="sxs-lookup"><span data-stu-id="6fa16-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-145">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="6fa16-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-147">float</span><span class="sxs-lookup"><span data-stu-id="6fa16-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-148">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="6fa16-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-150">float</span><span class="sxs-lookup"><span data-stu-id="6fa16-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-151">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="6fa16-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-153">float</span><span class="sxs-lookup"><span data-stu-id="6fa16-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-154">La valeur par défaut est 7.</span><span class="sxs-lookup"><span data-stu-id="6fa16-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fa16-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-156">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-157">La valeur par défaut est 5,00.</span><span class="sxs-lookup"><span data-stu-id="6fa16-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fa16-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6fa16-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6fa16-159">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="6fa16-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6fa16-160">La valeur par défaut est 10,00.</span><span class="sxs-lookup"><span data-stu-id="6fa16-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

