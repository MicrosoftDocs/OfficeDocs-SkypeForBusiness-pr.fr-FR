---
title: 'Lync Server 2013 : vue VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8163915a7af190ad91da50f84bfdb4f57eb023b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="0b423-102">Vue VideoStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b423-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b423-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0b423-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0b423-104">L’affichage VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0b423-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="0b423-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b423-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b423-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="0b423-106">Column</span></span></th>
<th><span data-ttu-id="0b423-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="0b423-107">Data Type</span></span></th>
<th><span data-ttu-id="0b423-108">Description</span><span class="sxs-lookup"><span data-stu-id="0b423-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b423-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="0b423-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="0b423-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0b423-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b423-111">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0b423-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="0b423-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="0b423-113">int</span><span class="sxs-lookup"><span data-stu-id="0b423-113">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0b423-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="0b423-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="0b423-116">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0b423-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="0b423-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="0b423-119">int</span><span class="sxs-lookup"><span data-stu-id="0b423-119">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-120">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="0b423-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="0b423-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="0b423-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0b423-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b423-123">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="0b423-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="0b423-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="0b423-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0b423-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b423-126">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="0b423-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="0b423-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="0b423-128">int</span><span class="sxs-lookup"><span data-stu-id="0b423-128">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-129">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b423-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="0b423-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="0b423-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-132">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="0b423-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="0b423-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="0b423-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-135">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="0b423-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-136">Appelant</span><span class="sxs-lookup"><span data-stu-id="0b423-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="0b423-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0b423-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0b423-138">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-139">Appelé</span><span class="sxs-lookup"><span data-stu-id="0b423-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="0b423-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0b423-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0b423-141">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="0b423-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0b423-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-144">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0b423-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0b423-146">type</span><span class="sxs-lookup"><span data-stu-id="0b423-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="0b423-147">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-147">Type of caller’s user agent.</span></span> <span data-ttu-id="0b423-148">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0b423-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0b423-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0b423-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0b423-151">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-151">Category of caller’s user agent.</span></span> <span data-ttu-id="0b423-152">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="0b423-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="0b423-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-155">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="0b423-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="0b423-157">type</span><span class="sxs-lookup"><span data-stu-id="0b423-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="0b423-158">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-158">Type of callee’s user agent.</span></span> <span data-ttu-id="0b423-159">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="0b423-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="0b423-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0b423-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0b423-162">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-162">Category of callee’s user agent.</span></span> <span data-ttu-id="0b423-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0b423-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0b423-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-166">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="0b423-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="0b423-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-169">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-170">Appelants</span><span class="sxs-lookup"><span data-stu-id="0b423-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="0b423-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-172">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="0b423-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="0b423-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-175">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="0b423-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="0b423-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-178">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="0b423-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="0b423-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-181">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0b423-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0b423-183">type</span><span class="sxs-lookup"><span data-stu-id="0b423-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="0b423-184">Nombre de cœurs de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="0b423-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="0b423-186">type</span><span class="sxs-lookup"><span data-stu-id="0b423-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="0b423-187">Nombre de cœurs de l’UC du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="0b423-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0b423-189">int</span><span class="sxs-lookup"><span data-stu-id="0b423-189">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-190">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="0b423-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="0b423-192">int</span><span class="sxs-lookup"><span data-stu-id="0b423-192">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-193">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0b423-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0b423-195">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-196">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="0b423-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0b423-197">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="0b423-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="0b423-199">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-200">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="0b423-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="0b423-201">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="0b423-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="0b423-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-204">Informations sur le chemin de médias, telles que direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="0b423-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="0b423-205">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0b423-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0b423-207">int</span><span class="sxs-lookup"><span data-stu-id="0b423-207">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-p109">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="0b423-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="0b423-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="0b423-211">int</span><span class="sxs-lookup"><span data-stu-id="0b423-211">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-p110">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="0b423-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-214">Transport</span><span class="sxs-lookup"><span data-stu-id="0b423-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="0b423-215">int</span><span class="sxs-lookup"><span data-stu-id="0b423-215">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-216">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="0b423-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="0b423-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0b423-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="0b423-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0b423-219">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-219">IP address of the caller.</span></span> <span data-ttu-id="0b423-220">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="0b423-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="0b423-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="0b423-222">int</span><span class="sxs-lookup"><span data-stu-id="0b423-222">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-223">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="0b423-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="0b423-225">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-225">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-226">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="0b423-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="0b423-227">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="0b423-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="0b423-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0b423-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="0b423-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0b423-230">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-230">IP address of the callee.</span></span> <span data-ttu-id="0b423-231">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="0b423-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="0b423-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="0b423-233">int</span><span class="sxs-lookup"><span data-stu-id="0b423-233">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-234">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="0b423-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="0b423-236">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-236">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-237">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="0b423-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="0b423-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="0b423-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-240">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="0b423-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="0b423-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-243">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="0b423-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="0b423-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-246">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="0b423-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="0b423-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0b423-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="0b423-249">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0b423-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0b423-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="0b423-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0b423-252">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="0b423-253">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="0b423-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0b423-255">int</span><span class="sxs-lookup"><span data-stu-id="0b423-255">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-256">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="0b423-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="0b423-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="0b423-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="0b423-259">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="0b423-260">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b423-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="0b423-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="0b423-262">int</span><span class="sxs-lookup"><span data-stu-id="0b423-262">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-263">Port sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="0b423-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0b423-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-266">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="0b423-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0b423-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-269">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="0b423-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0b423-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-272">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="0b423-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0b423-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-275">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="0b423-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="0b423-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-278">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="0b423-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="0b423-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-281">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="0b423-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0b423-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-284">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="0b423-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="0b423-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0b423-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b423-287">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="0b423-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0b423-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0b423-289">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-290">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="0b423-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="0b423-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="0b423-292">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-292">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-293">Indique si l’appelant s’est connecté sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="0b423-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="0b423-294">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="0b423-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0b423-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0b423-296">décimal (18,)</span><span class="sxs-lookup"><span data-stu-id="0b423-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="0b423-297">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="0b423-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="0b423-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="0b423-299">entier très petit</span><span class="sxs-lookup"><span data-stu-id="0b423-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0b423-300">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="0b423-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="0b423-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="0b423-302">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-302">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-303">Indique si l’appelé est connecté ou non sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="0b423-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="0b423-304">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="0b423-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="0b423-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="0b423-306">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="0b423-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="0b423-307">Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en BPS).</span><span class="sxs-lookup"><span data-stu-id="0b423-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="0b423-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="0b423-309">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0b423-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="0b423-310">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="0b423-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="0b423-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="0b423-312">int</span><span class="sxs-lookup"><span data-stu-id="0b423-312">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-313">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="0b423-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="0b423-314">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="0b423-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="0b423-315">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="0b423-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="0b423-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="0b423-317">int</span><span class="sxs-lookup"><span data-stu-id="0b423-317">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-318">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="0b423-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="0b423-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="0b423-320">int</span><span class="sxs-lookup"><span data-stu-id="0b423-320">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-321">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b423-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-322">Retour</span><span class="sxs-lookup"><span data-stu-id="0b423-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="0b423-323">int</span><span class="sxs-lookup"><span data-stu-id="0b423-323">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-324">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="0b423-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="0b423-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="0b423-326">int</span><span class="sxs-lookup"><span data-stu-id="0b423-326">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-327">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="0b423-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="0b423-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="0b423-329">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0b423-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-330">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b423-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="0b423-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="0b423-332">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0b423-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-333">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="0b423-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="0b423-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="0b423-335">int</span><span class="sxs-lookup"><span data-stu-id="0b423-335">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-336">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="0b423-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-337">Bande passante</span><span class="sxs-lookup"><span data-stu-id="0b423-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="0b423-338">int</span><span class="sxs-lookup"><span data-stu-id="0b423-338">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-339">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="0b423-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="0b423-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="0b423-341">int</span><span class="sxs-lookup"><span data-stu-id="0b423-341">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-342">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0b423-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="0b423-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="0b423-344">Char (9)</span><span class="sxs-lookup"><span data-stu-id="0b423-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="0b423-345">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="0b423-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="0b423-346">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="0b423-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="0b423-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="0b423-348">int</span><span class="sxs-lookup"><span data-stu-id="0b423-348">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-349">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="0b423-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="0b423-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="0b423-351">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0b423-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-352">Fréquence d’images de la vidéo reçue.</span><span class="sxs-lookup"><span data-stu-id="0b423-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="0b423-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="0b423-354">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0b423-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-355">Fréquence d’images de la vidéo envoyée.</span><span class="sxs-lookup"><span data-stu-id="0b423-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="0b423-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="0b423-357">int</span><span class="sxs-lookup"><span data-stu-id="0b423-357">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-358">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="0b423-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="0b423-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="0b423-360">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0b423-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-361">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="0b423-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="0b423-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="0b423-363">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="0b423-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-364">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="0b423-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="0b423-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="0b423-366">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-366">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-367">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="0b423-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="0b423-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="0b423-369">int</span><span class="sxs-lookup"><span data-stu-id="0b423-369">int</span></span></p></td>
<td><p><span data-ttu-id="0b423-370">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="0b423-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b423-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="0b423-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="0b423-372">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="0b423-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="0b423-373">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="0b423-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b423-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="0b423-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="0b423-375">légèrement</span><span class="sxs-lookup"><span data-stu-id="0b423-375">bit</span></span></p></td>
<td><p><span data-ttu-id="0b423-376">Direction du flux pour les informations d’identité déclarées p.</span><span class="sxs-lookup"><span data-stu-id="0b423-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="0b423-377">1 signifie que la direction du flux est entre l’appelant et l’appelé ; 0 signifie que la direction du flux passe de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0b423-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

