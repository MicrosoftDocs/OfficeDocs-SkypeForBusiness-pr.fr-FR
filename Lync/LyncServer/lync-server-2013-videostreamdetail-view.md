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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518521"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="5218a-102">Vue VideoStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5218a-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5218a-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5218a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5218a-104">L’affichage VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5218a-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="5218a-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5218a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5218a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="5218a-106">Column</span></span></th>
<th><span data-ttu-id="5218a-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="5218a-107">Data Type</span></span></th>
<th><span data-ttu-id="5218a-108">Description</span><span class="sxs-lookup"><span data-stu-id="5218a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5218a-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="5218a-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="5218a-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5218a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5218a-111">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5218a-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="5218a-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="5218a-113">int</span><span class="sxs-lookup"><span data-stu-id="5218a-113">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5218a-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="5218a-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="5218a-116">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5218a-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="5218a-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="5218a-119">int</span><span class="sxs-lookup"><span data-stu-id="5218a-119">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-120">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="5218a-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="5218a-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="5218a-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5218a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="5218a-123">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="5218a-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="5218a-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="5218a-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5218a-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="5218a-126">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="5218a-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="5218a-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="5218a-128">int</span><span class="sxs-lookup"><span data-stu-id="5218a-128">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-129">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="5218a-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="5218a-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="5218a-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-132">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="5218a-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="5218a-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="5218a-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-135">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="5218a-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-136">Appelant</span><span class="sxs-lookup"><span data-stu-id="5218a-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="5218a-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5218a-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5218a-138">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-139">Appelé</span><span class="sxs-lookup"><span data-stu-id="5218a-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="5218a-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5218a-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5218a-141">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="5218a-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="5218a-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-144">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="5218a-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="5218a-146">type</span><span class="sxs-lookup"><span data-stu-id="5218a-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="5218a-147">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-147">Type of caller’s user agent.</span></span> <span data-ttu-id="5218a-148">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="5218a-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="5218a-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5218a-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5218a-151">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-151">Category of caller’s user agent.</span></span> <span data-ttu-id="5218a-152">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="5218a-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="5218a-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-155">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="5218a-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="5218a-157">type</span><span class="sxs-lookup"><span data-stu-id="5218a-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="5218a-158">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-158">Type of callee’s user agent.</span></span> <span data-ttu-id="5218a-159">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="5218a-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="5218a-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5218a-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5218a-162">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-162">Category of callee’s user agent.</span></span> <span data-ttu-id="5218a-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="5218a-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="5218a-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-166">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="5218a-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="5218a-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-169">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-170">Appelants</span><span class="sxs-lookup"><span data-stu-id="5218a-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="5218a-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-172">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="5218a-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="5218a-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-175">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="5218a-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="5218a-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-178">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="5218a-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="5218a-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-181">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="5218a-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="5218a-183">type</span><span class="sxs-lookup"><span data-stu-id="5218a-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="5218a-184">Nombre de cœurs de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="5218a-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="5218a-186">type</span><span class="sxs-lookup"><span data-stu-id="5218a-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="5218a-187">Nombre de cœurs de l’UC du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="5218a-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="5218a-189">int</span><span class="sxs-lookup"><span data-stu-id="5218a-189">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-190">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="5218a-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="5218a-192">int</span><span class="sxs-lookup"><span data-stu-id="5218a-192">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-193">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="5218a-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="5218a-195">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-196">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="5218a-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="5218a-197">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="5218a-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="5218a-199">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-200">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="5218a-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="5218a-201">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="5218a-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="5218a-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-204">Informations sur le chemin de médias, telles que direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="5218a-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="5218a-205">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5218a-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5218a-207">int</span><span class="sxs-lookup"><span data-stu-id="5218a-207">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-p109">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="5218a-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5218a-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5218a-211">int</span><span class="sxs-lookup"><span data-stu-id="5218a-211">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-p110">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="5218a-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-214">Transport</span><span class="sxs-lookup"><span data-stu-id="5218a-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="5218a-215">int</span><span class="sxs-lookup"><span data-stu-id="5218a-215">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-216">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="5218a-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="5218a-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5218a-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="5218a-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5218a-219">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-219">IP address of the caller.</span></span> <span data-ttu-id="5218a-220">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="5218a-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="5218a-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="5218a-222">int</span><span class="sxs-lookup"><span data-stu-id="5218a-222">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-223">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="5218a-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="5218a-225">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-225">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-226">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="5218a-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="5218a-227">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="5218a-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="5218a-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5218a-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="5218a-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5218a-230">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-230">IP address of the callee.</span></span> <span data-ttu-id="5218a-231">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="5218a-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="5218a-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="5218a-233">int</span><span class="sxs-lookup"><span data-stu-id="5218a-233">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-234">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="5218a-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="5218a-236">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-236">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-237">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="5218a-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="5218a-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="5218a-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-240">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="5218a-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="5218a-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-243">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="5218a-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="5218a-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-246">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="5218a-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="5218a-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5218a-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5218a-249">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5218a-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5218a-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="5218a-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5218a-252">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="5218a-253">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="5218a-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5218a-255">int</span><span class="sxs-lookup"><span data-stu-id="5218a-255">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-256">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5218a-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5218a-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="5218a-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5218a-259">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="5218a-260">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5218a-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5218a-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5218a-262">int</span><span class="sxs-lookup"><span data-stu-id="5218a-262">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-263">Port sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5218a-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5218a-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-266">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="5218a-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5218a-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-269">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5218a-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5218a-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-272">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5218a-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5218a-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-275">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5218a-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5218a-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-278">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="5218a-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5218a-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-281">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5218a-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5218a-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-284">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5218a-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5218a-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5218a-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5218a-287">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5218a-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="5218a-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="5218a-289">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-290">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="5218a-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="5218a-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="5218a-292">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-292">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-293">Indique si l’appelant s’est connecté sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="5218a-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="5218a-294">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="5218a-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="5218a-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="5218a-296">décimal (18,)</span><span class="sxs-lookup"><span data-stu-id="5218a-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="5218a-297">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="5218a-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="5218a-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="5218a-299">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5218a-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5218a-300">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="5218a-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="5218a-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="5218a-302">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-302">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-303">Indique si l’appelé est connecté ou non sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="5218a-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="5218a-304">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="5218a-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="5218a-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="5218a-306">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="5218a-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="5218a-307">Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en BPS).</span><span class="sxs-lookup"><span data-stu-id="5218a-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="5218a-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="5218a-309">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5218a-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="5218a-310">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="5218a-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="5218a-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="5218a-312">int</span><span class="sxs-lookup"><span data-stu-id="5218a-312">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-313">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="5218a-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="5218a-314">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="5218a-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="5218a-315">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="5218a-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="5218a-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="5218a-317">int</span><span class="sxs-lookup"><span data-stu-id="5218a-317">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-318">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="5218a-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="5218a-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="5218a-320">int</span><span class="sxs-lookup"><span data-stu-id="5218a-320">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-321">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="5218a-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-322">Retour</span><span class="sxs-lookup"><span data-stu-id="5218a-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="5218a-323">int</span><span class="sxs-lookup"><span data-stu-id="5218a-323">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-324">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="5218a-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="5218a-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="5218a-326">int</span><span class="sxs-lookup"><span data-stu-id="5218a-326">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-327">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="5218a-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="5218a-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="5218a-329">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5218a-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-330">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="5218a-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="5218a-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="5218a-332">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5218a-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-333">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="5218a-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="5218a-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="5218a-335">int</span><span class="sxs-lookup"><span data-stu-id="5218a-335">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-336">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="5218a-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-337">Bande passante</span><span class="sxs-lookup"><span data-stu-id="5218a-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="5218a-338">int</span><span class="sxs-lookup"><span data-stu-id="5218a-338">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-339">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="5218a-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="5218a-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="5218a-341">int</span><span class="sxs-lookup"><span data-stu-id="5218a-341">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-342">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5218a-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="5218a-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="5218a-344">Char (9)</span><span class="sxs-lookup"><span data-stu-id="5218a-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="5218a-345">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="5218a-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="5218a-346">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="5218a-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="5218a-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5218a-348">int</span><span class="sxs-lookup"><span data-stu-id="5218a-348">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-349">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="5218a-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="5218a-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5218a-351">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5218a-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-352">Fréquence d’images de la vidéo reçue.</span><span class="sxs-lookup"><span data-stu-id="5218a-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="5218a-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5218a-354">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5218a-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-355">Fréquence d’images de la vidéo envoyée.</span><span class="sxs-lookup"><span data-stu-id="5218a-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="5218a-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="5218a-357">int</span><span class="sxs-lookup"><span data-stu-id="5218a-357">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-358">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="5218a-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="5218a-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="5218a-360">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5218a-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-361">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="5218a-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="5218a-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="5218a-363">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="5218a-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-364">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="5218a-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="5218a-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="5218a-366">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-366">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-367">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="5218a-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="5218a-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="5218a-369">int</span><span class="sxs-lookup"><span data-stu-id="5218a-369">int</span></span></p></td>
<td><p><span data-ttu-id="5218a-370">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="5218a-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5218a-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="5218a-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="5218a-372">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="5218a-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="5218a-373">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="5218a-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5218a-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="5218a-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="5218a-375">légèrement</span><span class="sxs-lookup"><span data-stu-id="5218a-375">bit</span></span></p></td>
<td><p><span data-ttu-id="5218a-376">Direction du flux pour les informations d’identité déclarées p.</span><span class="sxs-lookup"><span data-stu-id="5218a-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="5218a-377">1 signifie que la direction du flux est entre l’appelant et l’appelé ; 0 signifie que la direction du flux passe de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5218a-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

