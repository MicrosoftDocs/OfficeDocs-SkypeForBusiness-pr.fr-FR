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
ms.openlocfilehash: 311fb8fcd750261dbb5ef2e579fb092781526a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="ac1ac-102">Vue VideoStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac1ac-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac1ac-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ac1ac-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ac1ac-104">L’affichage VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="ac1ac-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac1ac-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="ac1ac-106">Column</span></span></th>
<th><span data-ttu-id="ac1ac-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="ac1ac-107">Data Type</span></span></th>
<th><span data-ttu-id="ac1ac-108">Description</span><span class="sxs-lookup"><span data-stu-id="ac1ac-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="ac1ac-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ac1ac-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-111">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="ac1ac-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-113">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-113">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="ac1ac-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-116">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="ac1ac-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-119">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-119">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-120">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="ac1ac-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ac1ac-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-123">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="ac1ac-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ac1ac-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-126">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="ac1ac-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-128">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-128">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-129">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="ac1ac-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-132">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="ac1ac-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-135">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-136">Appelant</span><span class="sxs-lookup"><span data-stu-id="ac1ac-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-138">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-139">Appelé</span><span class="sxs-lookup"><span data-stu-id="ac1ac-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-141">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="ac1ac-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-144">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ac1ac-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-146">type</span><span class="sxs-lookup"><span data-stu-id="ac1ac-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-147">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-147">Type of caller’s user agent.</span></span> <span data-ttu-id="ac1ac-148">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ac1ac-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-151">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-151">Category of caller’s user agent.</span></span> <span data-ttu-id="ac1ac-152">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="ac1ac-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-155">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ac1ac-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-157">type</span><span class="sxs-lookup"><span data-stu-id="ac1ac-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-158">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-158">Type of callee’s user agent.</span></span> <span data-ttu-id="ac1ac-159">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ac1ac-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-162">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-162">Category of callee’s user agent.</span></span> <span data-ttu-id="ac1ac-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ac1ac-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-166">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="ac1ac-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-169">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-170">Appelants</span><span class="sxs-lookup"><span data-stu-id="ac1ac-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-172">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="ac1ac-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-175">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="ac1ac-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-178">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="ac1ac-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-181">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ac1ac-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-183">type</span><span class="sxs-lookup"><span data-stu-id="ac1ac-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-184">Nombre de cœurs de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ac1ac-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-186">type</span><span class="sxs-lookup"><span data-stu-id="ac1ac-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-187">Nombre de cœurs de l’UC du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ac1ac-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-189">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-189">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-190">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ac1ac-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-192">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-192">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-193">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ac1ac-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-195">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-196">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ac1ac-197">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ac1ac-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-199">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-200">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ac1ac-201">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="ac1ac-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-204">Informations sur le chemin de médias, telles que direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="ac1ac-205">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ac1ac-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-207">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-207">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-p109">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ac1ac-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-211">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-211">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-p110">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-214">Transport</span><span class="sxs-lookup"><span data-stu-id="ac1ac-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-215">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-215">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-216">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="ac1ac-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-219">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-219">IP address of the caller.</span></span> <span data-ttu-id="ac1ac-220">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="ac1ac-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-222">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-222">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-223">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="ac1ac-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-225">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-225">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-226">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="ac1ac-227">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="ac1ac-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-230">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-230">IP address of the callee.</span></span> <span data-ttu-id="ac1ac-231">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="ac1ac-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-233">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-233">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-234">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="ac1ac-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-236">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-236">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-237">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="ac1ac-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-240">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="ac1ac-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-243">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="ac1ac-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-246">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="ac1ac-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ac1ac-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-249">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ac1ac-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-252">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="ac1ac-253">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="ac1ac-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-255">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-255">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-256">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ac1ac-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-259">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="ac1ac-260">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac1ac-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="ac1ac-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-262">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-262">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-263">Port sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ac1ac-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-266">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="ac1ac-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-269">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ac1ac-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-272">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ac1ac-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-275">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ac1ac-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-278">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="ac1ac-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-281">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ac1ac-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-284">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ac1ac-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-287">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ac1ac-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-289">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-290">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="ac1ac-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-292">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-292">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-293">Indique si l’appelant s’est connecté sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="ac1ac-294">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ac1ac-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-296">décimal (18,)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-297">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ac1ac-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-299">entier très petit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-300">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="ac1ac-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-302">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-302">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-303">Indique si l’appelé est connecté ou non sur un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="ac1ac-304">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ac1ac-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-306">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-307">Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en BPS).</span><span class="sxs-lookup"><span data-stu-id="ac1ac-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="ac1ac-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-309">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-310">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="ac1ac-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="ac1ac-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-312">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-312">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-313">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="ac1ac-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="ac1ac-314">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="ac1ac-315">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="ac1ac-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-317">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-317">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-318">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="ac1ac-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="ac1ac-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-320">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-320">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-321">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-322">Retour</span><span class="sxs-lookup"><span data-stu-id="ac1ac-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-323">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-323">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-324">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="ac1ac-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-326">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-326">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-327">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ac1ac-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-329">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-330">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="ac1ac-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-332">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-333">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="ac1ac-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-335">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-335">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-336">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="ac1ac-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-337">Bande passante</span><span class="sxs-lookup"><span data-stu-id="ac1ac-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-338">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-338">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-339">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="ac1ac-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-341">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-341">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-342">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="ac1ac-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-344">Char (9)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-345">Résolution de la vidéo en pixels largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="ac1ac-346">Signalée sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="ac1ac-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-348">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-348">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-349">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="ac1ac-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-351">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-352">Fréquence d’images de la vidéo reçue.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="ac1ac-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-354">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-355">Fréquence d’images de la vidéo envoyée.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="ac1ac-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-357">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-357">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-358">Vitesse de transmission vidéo maximale lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ac1ac-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-360">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-361">Vitesse à laquelle les paquets vidéo ont été perdus.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="ac1ac-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-363">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-364">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="ac1ac-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-366">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-366">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-367">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="ac1ac-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-369">int</span><span class="sxs-lookup"><span data-stu-id="ac1ac-369">int</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-370">Quantité moyenne de bande passante allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac1ac-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="ac1ac-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-372">décimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="ac1ac-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-373">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac1ac-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="ac1ac-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-375">légèrement</span><span class="sxs-lookup"><span data-stu-id="ac1ac-375">bit</span></span></p></td>
<td><p><span data-ttu-id="ac1ac-376">Direction du flux pour les informations d’identité déclarées p.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="ac1ac-377">1 signifie que la direction du flux est entre l’appelant et l’appelé ; 0 signifie que la direction du flux passe de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="ac1ac-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

