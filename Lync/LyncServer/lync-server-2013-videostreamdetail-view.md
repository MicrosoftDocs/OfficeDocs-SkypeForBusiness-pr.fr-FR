---
title: 'Lync Server 2013 : vue VideoStreamDetail'
description: 'Lync Server 2013 : vue VideoStreamDetail.'
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567970"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="59e02-103">Vue VideoStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59e02-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59e02-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="59e02-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="59e02-105">L’affichage VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="59e02-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="59e02-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59e02-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59e02-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="59e02-107">Column</span></span></th>
<th><span data-ttu-id="59e02-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="59e02-108">Data Type</span></span></th>
<th><span data-ttu-id="59e02-109">Description</span><span class="sxs-lookup"><span data-stu-id="59e02-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59e02-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="59e02-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="59e02-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="59e02-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="59e02-112">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="59e02-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="59e02-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="59e02-114">int</span><span class="sxs-lookup"><span data-stu-id="59e02-114">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-115">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="59e02-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="59e02-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="59e02-117">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-118">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="59e02-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="59e02-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="59e02-120">int</span><span class="sxs-lookup"><span data-stu-id="59e02-120">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-121">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="59e02-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="59e02-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="59e02-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="59e02-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="59e02-124">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="59e02-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="59e02-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="59e02-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="59e02-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="59e02-127">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="59e02-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="59e02-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="59e02-129">int</span><span class="sxs-lookup"><span data-stu-id="59e02-129">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-130">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="59e02-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="59e02-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="59e02-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-133">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="59e02-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="59e02-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="59e02-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-136">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="59e02-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-137">Appelant</span><span class="sxs-lookup"><span data-stu-id="59e02-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="59e02-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="59e02-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="59e02-139">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-140">Appelé</span><span class="sxs-lookup"><span data-stu-id="59e02-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="59e02-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="59e02-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="59e02-142">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="59e02-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="59e02-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-145">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="59e02-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="59e02-147">type</span><span class="sxs-lookup"><span data-stu-id="59e02-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="59e02-148">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-148">Type of caller’s user agent.</span></span> <span data-ttu-id="59e02-149">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="59e02-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="59e02-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="59e02-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="59e02-152">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-152">Category of caller’s user agent.</span></span> <span data-ttu-id="59e02-153">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="59e02-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="59e02-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-156">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="59e02-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="59e02-158">type</span><span class="sxs-lookup"><span data-stu-id="59e02-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="59e02-159">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-159">Type of callee’s user agent.</span></span> <span data-ttu-id="59e02-160">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="59e02-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="59e02-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="59e02-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="59e02-163">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-163">Category of callee’s user agent.</span></span> <span data-ttu-id="59e02-164">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="59e02-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="59e02-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-167">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="59e02-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="59e02-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-170">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-171">Appelants</span><span class="sxs-lookup"><span data-stu-id="59e02-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="59e02-172">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-173">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="59e02-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="59e02-175">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-176">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="59e02-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="59e02-178">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-179">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="59e02-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="59e02-181">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-182">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="59e02-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="59e02-184">type</span><span class="sxs-lookup"><span data-stu-id="59e02-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="59e02-185">Nombre de cœurs de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="59e02-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="59e02-187">type</span><span class="sxs-lookup"><span data-stu-id="59e02-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="59e02-188">Nombre de cœurs de l’UC du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="59e02-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="59e02-190">int</span><span class="sxs-lookup"><span data-stu-id="59e02-190">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-191">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="59e02-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="59e02-193">int</span><span class="sxs-lookup"><span data-stu-id="59e02-193">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-194">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="59e02-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="59e02-196">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-197">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="59e02-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="59e02-198">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="59e02-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="59e02-200">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-201">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="59e02-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="59e02-202">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="59e02-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="59e02-204">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-205">Informations sur le chemin de médias, telles que direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="59e02-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="59e02-206">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="59e02-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="59e02-208">int</span><span class="sxs-lookup"><span data-stu-id="59e02-208">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-p109">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="59e02-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="59e02-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="59e02-212">int</span><span class="sxs-lookup"><span data-stu-id="59e02-212">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-p110">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="59e02-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-215">Transport</span><span class="sxs-lookup"><span data-stu-id="59e02-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="59e02-216">int</span><span class="sxs-lookup"><span data-stu-id="59e02-216">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-217">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="59e02-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="59e02-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="59e02-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="59e02-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="59e02-220">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-220">IP address of the caller.</span></span> <span data-ttu-id="59e02-221">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="59e02-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="59e02-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="59e02-223">int</span><span class="sxs-lookup"><span data-stu-id="59e02-223">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-224">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="59e02-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="59e02-226">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-226">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-227">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="59e02-227">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="59e02-228">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="59e02-228">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="59e02-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="59e02-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="59e02-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="59e02-231">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-231">IP address of the callee.</span></span> <span data-ttu-id="59e02-232">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="59e02-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="59e02-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="59e02-234">int</span><span class="sxs-lookup"><span data-stu-id="59e02-234">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-235">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="59e02-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="59e02-237">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-237">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-238">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="59e02-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="59e02-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="59e02-240">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-241">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="59e02-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="59e02-243">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-244">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="59e02-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="59e02-246">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-247">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="59e02-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="59e02-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="59e02-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="59e02-250">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="59e02-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="59e02-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="59e02-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="59e02-253">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="59e02-254">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="59e02-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="59e02-256">int</span><span class="sxs-lookup"><span data-stu-id="59e02-256">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-257">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="59e02-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="59e02-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="59e02-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="59e02-260">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="59e02-261">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="59e02-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="59e02-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="59e02-263">int</span><span class="sxs-lookup"><span data-stu-id="59e02-263">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-264">Port sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="59e02-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="59e02-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-267">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="59e02-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="59e02-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-270">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="59e02-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="59e02-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-273">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="59e02-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="59e02-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-276">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="59e02-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="59e02-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-279">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="59e02-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="59e02-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-282">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="59e02-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="59e02-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-285">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="59e02-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="59e02-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="59e02-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="59e02-288">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="59e02-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="59e02-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="59e02-290">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-291">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="59e02-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="59e02-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="59e02-293">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-293">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-294">Indique si l’appelant s’est connecté sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="59e02-294">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="59e02-295">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="59e02-295">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="59e02-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="59e02-297">décimal (18,)</span><span class="sxs-lookup"><span data-stu-id="59e02-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="59e02-298">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="59e02-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="59e02-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="59e02-300">entier très petit</span><span class="sxs-lookup"><span data-stu-id="59e02-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59e02-301">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="59e02-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="59e02-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="59e02-303">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-303">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-304">Indique si l’appelé est connecté ou non sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="59e02-304">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="59e02-305">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="59e02-305">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="59e02-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="59e02-307">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="59e02-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="59e02-308">Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en BPS).</span><span class="sxs-lookup"><span data-stu-id="59e02-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="59e02-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="59e02-310">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="59e02-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="59e02-311">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="59e02-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="59e02-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="59e02-313">int</span><span class="sxs-lookup"><span data-stu-id="59e02-313">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-314">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="59e02-314">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="59e02-315">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="59e02-315">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="59e02-316">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="59e02-316">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="59e02-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="59e02-318">int</span><span class="sxs-lookup"><span data-stu-id="59e02-318">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-319">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="59e02-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="59e02-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="59e02-321">int</span><span class="sxs-lookup"><span data-stu-id="59e02-321">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-322">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="59e02-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-323">Retour</span><span class="sxs-lookup"><span data-stu-id="59e02-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="59e02-324">int</span><span class="sxs-lookup"><span data-stu-id="59e02-324">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-325">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="59e02-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="59e02-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="59e02-327">int</span><span class="sxs-lookup"><span data-stu-id="59e02-327">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-328">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="59e02-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="59e02-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="59e02-330">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="59e02-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-331">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="59e02-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="59e02-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="59e02-333">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="59e02-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-334">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="59e02-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="59e02-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="59e02-336">int</span><span class="sxs-lookup"><span data-stu-id="59e02-336">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-337">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="59e02-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-338">Bande passante</span><span class="sxs-lookup"><span data-stu-id="59e02-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="59e02-339">int</span><span class="sxs-lookup"><span data-stu-id="59e02-339">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-340">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="59e02-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="59e02-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="59e02-342">int</span><span class="sxs-lookup"><span data-stu-id="59e02-342">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-343">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="59e02-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="59e02-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="59e02-345">Char (9)</span><span class="sxs-lookup"><span data-stu-id="59e02-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="59e02-346">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="59e02-346">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="59e02-347">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="59e02-347">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="59e02-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="59e02-349">int</span><span class="sxs-lookup"><span data-stu-id="59e02-349">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-350">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="59e02-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="59e02-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="59e02-352">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="59e02-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-353">Fréquence d’images de la vidéo reçue.</span><span class="sxs-lookup"><span data-stu-id="59e02-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="59e02-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="59e02-355">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="59e02-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-356">Fréquence d’images de la vidéo envoyée.</span><span class="sxs-lookup"><span data-stu-id="59e02-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="59e02-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="59e02-358">int</span><span class="sxs-lookup"><span data-stu-id="59e02-358">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-359">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="59e02-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="59e02-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="59e02-361">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="59e02-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-362">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="59e02-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="59e02-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="59e02-364">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="59e02-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-365">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="59e02-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="59e02-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="59e02-367">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-367">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-368">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="59e02-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="59e02-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="59e02-370">int</span><span class="sxs-lookup"><span data-stu-id="59e02-370">int</span></span></p></td>
<td><p><span data-ttu-id="59e02-371">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="59e02-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59e02-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="59e02-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="59e02-373">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="59e02-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="59e02-374">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="59e02-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59e02-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="59e02-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="59e02-376">légèrement</span><span class="sxs-lookup"><span data-stu-id="59e02-376">bit</span></span></p></td>
<td><p><span data-ttu-id="59e02-377">Direction du flux pour les informations d’identité déclarées p.</span><span class="sxs-lookup"><span data-stu-id="59e02-377">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="59e02-378">1 signifie que la direction du flux est entre l’appelant et l’appelé ; 0 signifie que la direction du flux passe de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="59e02-378">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

