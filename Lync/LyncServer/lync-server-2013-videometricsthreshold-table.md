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
ms.openlocfilehash: 58a054ba58ff7e1e839b0aeca88d0e61164e30b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="72f96-102">Table VideoMetricsThreshold dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72f96-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72f96-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="72f96-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="72f96-104">La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.</span><span class="sxs-lookup"><span data-stu-id="72f96-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72f96-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="72f96-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="72f96-107"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="72f96-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72f96-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-110">int</span><span class="sxs-lookup"><span data-stu-id="72f96-110">int</span></span></p></td>
<td><p><span data-ttu-id="72f96-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="72f96-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="72f96-112">Type d’appel passé.</span><span class="sxs-lookup"><span data-stu-id="72f96-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-114">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-115">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="72f96-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-117">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-118">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="72f96-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-120">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-121">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="72f96-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-123">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-124">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="72f96-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-126">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="72f96-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-127">La valeur par défaut est 12,0000.</span><span class="sxs-lookup"><span data-stu-id="72f96-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-129">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="72f96-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-130">La valeur par défaut est 7,0000.</span><span class="sxs-lookup"><span data-stu-id="72f96-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-132">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-133">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="72f96-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-135">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-136">La valeur par défaut est 10,0/</span><span class="sxs-lookup"><span data-stu-id="72f96-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-138">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-139">La valeur par défaut est 5,0.</span><span class="sxs-lookup"><span data-stu-id="72f96-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-141">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-142">La valeur par défaut est 10,0.</span><span class="sxs-lookup"><span data-stu-id="72f96-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-144">foat</span><span class="sxs-lookup"><span data-stu-id="72f96-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-145">La valeur par défaut est 0,05.</span><span class="sxs-lookup"><span data-stu-id="72f96-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-147">flottant</span><span class="sxs-lookup"><span data-stu-id="72f96-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-148">La valeur par défaut est 0,10.</span><span class="sxs-lookup"><span data-stu-id="72f96-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-150">flottant</span><span class="sxs-lookup"><span data-stu-id="72f96-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-151">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="72f96-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-153">flottant</span><span class="sxs-lookup"><span data-stu-id="72f96-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-154">La valeur par défaut est 7.</span><span class="sxs-lookup"><span data-stu-id="72f96-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72f96-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-156">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-157">La valeur par défaut est 5,00.</span><span class="sxs-lookup"><span data-stu-id="72f96-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72f96-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72f96-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72f96-159">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72f96-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72f96-160">La valeur par défaut est 10,00.</span><span class="sxs-lookup"><span data-stu-id="72f96-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

