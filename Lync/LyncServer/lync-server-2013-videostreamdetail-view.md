---
title: 'Affichage Lync Server 2013 : VideoStreamDetail'
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
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="8e91b-102">Affichage VideoStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e91b-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e91b-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8e91b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8e91b-104">Le mode VideoStreamDetail stocke les informations relatives à chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="8e91b-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="8e91b-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e91b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e91b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="8e91b-106">Column</span></span></th>
<th><span data-ttu-id="8e91b-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="8e91b-107">Data Type</span></span></th>
<th><span data-ttu-id="8e91b-108">Description</span><span class="sxs-lookup"><span data-stu-id="8e91b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="8e91b-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8e91b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-111">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8e91b-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="8e91b-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="8e91b-113">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-113">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-114">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8e91b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="8e91b-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="8e91b-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-117">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8e91b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="8e91b-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="8e91b-119">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-119">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-120">IDENTIFIant unique dans une ligne de médias.</span><span class="sxs-lookup"><span data-stu-id="8e91b-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="8e91b-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8e91b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-123">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="8e91b-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="8e91b-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8e91b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="8e91b-126">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="8e91b-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="8e91b-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="8e91b-128">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-128">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-129">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="8e91b-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="8e91b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-132">Nom de domaine complet du pool d’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="8e91b-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="8e91b-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-135">Nom de domaine complet (FQDN) du pool d’appel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-136">Appelant</span><span class="sxs-lookup"><span data-stu-id="8e91b-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="8e91b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8e91b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-138">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-139">Appelé</span><span class="sxs-lookup"><span data-stu-id="8e91b-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="8e91b-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8e91b-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-141">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="8e91b-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8e91b-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-144">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8e91b-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8e91b-146">type</span><span class="sxs-lookup"><span data-stu-id="8e91b-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-147">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-147">Type of caller’s user agent.</span></span> <span data-ttu-id="8e91b-148">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8e91b-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8e91b-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8e91b-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-151">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-151">Category of caller’s user agent.</span></span> <span data-ttu-id="8e91b-152">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="8e91b-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8e91b-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-155">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8e91b-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8e91b-157">type</span><span class="sxs-lookup"><span data-stu-id="8e91b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-158">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-158">Type of callee’s user agent.</span></span> <span data-ttu-id="8e91b-159">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8e91b-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8e91b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8e91b-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-162">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-162">Category of callee’s user agent.</span></span> <span data-ttu-id="8e91b-163">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8e91b-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-166">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="8e91b-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-169">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-170">Appelant</span><span class="sxs-lookup"><span data-stu-id="8e91b-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="8e91b-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-172">Système d’exploitation (se) du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="8e91b-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="8e91b-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-175">Système d’exploitation (se) du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="8e91b-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="8e91b-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-178">Nom de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="8e91b-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="8e91b-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-181">Nom de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8e91b-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8e91b-183">type</span><span class="sxs-lookup"><span data-stu-id="8e91b-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-184">Nombre de cœurs d’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8e91b-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8e91b-186">type</span><span class="sxs-lookup"><span data-stu-id="8e91b-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-187">Nombre de cœurs d’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8e91b-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8e91b-189">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-189">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-190">Vitesse de processeur de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8e91b-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8e91b-192">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-192">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-193">Vitesse de processeur de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8e91b-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8e91b-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-196">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8e91b-197">Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8e91b-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8e91b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-200">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8e91b-201">Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="8e91b-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="8e91b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-204">Des informations sur le chemin multimédia, par exemple direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="8e91b-205">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8e91b-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8e91b-207">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-207">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-208">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="8e91b-209">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="8e91b-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8e91b-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8e91b-211">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-211">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-212">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="8e91b-213">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="8e91b-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-214">Transport</span><span class="sxs-lookup"><span data-stu-id="8e91b-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="8e91b-215">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-215">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-216">Le type de transport : 0 correspond au protocole UDP ; 1 est le protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="8e91b-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="8e91b-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8e91b-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="8e91b-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-219">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-219">IP address of the caller.</span></span> <span data-ttu-id="8e91b-220">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e91b-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="8e91b-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="8e91b-222">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-222">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-223">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="8e91b-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="8e91b-225">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-226">Indique si l’appelant se trouve au sein du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8e91b-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="8e91b-227">1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="8e91b-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="8e91b-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8e91b-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="8e91b-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-230">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-230">IP address of the callee.</span></span> <span data-ttu-id="8e91b-231">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e91b-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="8e91b-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="8e91b-233">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-233">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-234">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="8e91b-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="8e91b-236">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-236">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-237">Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appel se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="8e91b-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="8e91b-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="8e91b-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-240">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="8e91b-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="8e91b-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-243">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="8e91b-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="8e91b-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-246">Nom du site du ou des appelants.</span><span class="sxs-lookup"><span data-stu-id="8e91b-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="8e91b-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="8e91b-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8e91b-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-249">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8e91b-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8e91b-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="8e91b-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-252">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="8e91b-253">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="8e91b-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8e91b-255">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-255">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-256">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8e91b-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8e91b-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="8e91b-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-259">Clé d’adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="8e91b-260">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8e91b-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="8e91b-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8e91b-262">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-262">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-263">Port sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8e91b-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8e91b-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-266">Nom de l’appareil de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="8e91b-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8e91b-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-269">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8e91b-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8e91b-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-272">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8e91b-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8e91b-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-275">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8e91b-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8e91b-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-278">Nom de l’appareil de capture du destinataire.</span><span class="sxs-lookup"><span data-stu-id="8e91b-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="8e91b-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8e91b-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-281">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8e91b-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8e91b-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-284">Nom du pilote de l’appareil de capture du appelé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8e91b-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8e91b-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e91b-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-287">Nom du pilote du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8e91b-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8e91b-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-290">Type de connexion réseau de l’appelant : 0 est filaire, 1 est un réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="8e91b-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="8e91b-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="8e91b-292">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-292">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-293">Indique si l’appelant s’est connecté via un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="8e91b-294">1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="8e91b-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8e91b-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8e91b-296">décimale (18)</span><span class="sxs-lookup"><span data-stu-id="8e91b-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-297">Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.</span><span class="sxs-lookup"><span data-stu-id="8e91b-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8e91b-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8e91b-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e91b-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8e91b-300">Type de connexion réseau du ou du destinataire : 0 est filaire, 1 est un téléphone sans fil.</span><span class="sxs-lookup"><span data-stu-id="8e91b-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="8e91b-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="8e91b-302">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-302">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-303">Indique si l’appelant est connecté via un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="8e91b-304">1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="8e91b-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8e91b-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8e91b-306">décimale (18, 0)</span><span class="sxs-lookup"><span data-stu-id="8e91b-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-307">Vitesse de liaison réseau pour le point de terminaison de l’appelant (en BPS).</span><span class="sxs-lookup"><span data-stu-id="8e91b-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="8e91b-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="8e91b-309">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8e91b-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-310">La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="8e91b-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="8e91b-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-312">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-312">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-313">Bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="8e91b-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="8e91b-314">Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="8e91b-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="8e91b-315">Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="8e91b-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="8e91b-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="8e91b-317">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-317">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-318">Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="8e91b-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="8e91b-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="8e91b-320">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-320">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-321">Scintillement du réseau maximum lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="8e91b-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="8e91b-323">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-323">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-324">Durée de l’aller-retour des statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="8e91b-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="8e91b-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="8e91b-326">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-326">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-327">Durée de l’aller-retour maximal pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="8e91b-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="8e91b-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8e91b-329">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-330">Taux moyen de perte de paquets lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="8e91b-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="8e91b-332">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-333">Perte de paquets maximum observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="8e91b-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="8e91b-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="8e91b-335">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-335">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-336">Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="8e91b-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-337">Bande passante</span><span class="sxs-lookup"><span data-stu-id="8e91b-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="8e91b-338">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-338">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-339">Estimations de bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="8e91b-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="8e91b-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="8e91b-341">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-341">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-342">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8e91b-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="8e91b-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="8e91b-344">car (9)</span><span class="sxs-lookup"><span data-stu-id="8e91b-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-345">Résolution de la vidéo, en pixels, de largeur multipliée par la hauteur en pixels.</span><span class="sxs-lookup"><span data-stu-id="8e91b-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="8e91b-346">Signalée en tant que chaîne.</span><span class="sxs-lookup"><span data-stu-id="8e91b-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="8e91b-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8e91b-348">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-348">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-349">Vitesse de transmission moyenne du flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="8e91b-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="8e91b-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8e91b-351">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-352">Fréquence d’images de la vidéo reçue.</span><span class="sxs-lookup"><span data-stu-id="8e91b-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="8e91b-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8e91b-354">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-355">Fréquence d’images de la vidéo envoyée.</span><span class="sxs-lookup"><span data-stu-id="8e91b-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="8e91b-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="8e91b-357">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-357">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-358">Débit vidéo maximum lors de la session vidéo.</span><span class="sxs-lookup"><span data-stu-id="8e91b-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-359">Cause du taux</span><span class="sxs-lookup"><span data-stu-id="8e91b-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8e91b-360">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-361">Taux d’interruption des paquets vidéo.</span><span class="sxs-lookup"><span data-stu-id="8e91b-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="8e91b-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="8e91b-363">décimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-364">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="8e91b-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="8e91b-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="8e91b-366">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-366">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-367">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="8e91b-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="8e91b-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="8e91b-369">int</span><span class="sxs-lookup"><span data-stu-id="8e91b-369">int</span></span></p></td>
<td><p><span data-ttu-id="8e91b-370">Quantité moyenne de bande passante allouée pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="8e91b-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e91b-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="8e91b-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="8e91b-372">décimale (9.4)</span><span class="sxs-lookup"><span data-stu-id="8e91b-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="8e91b-373">Pourcentage du nombre total de trames vidéo perdues.</span><span class="sxs-lookup"><span data-stu-id="8e91b-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e91b-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="8e91b-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="8e91b-375">bit</span><span class="sxs-lookup"><span data-stu-id="8e91b-375">bit</span></span></p></td>
<td><p><span data-ttu-id="8e91b-376">Direction du flux pour les informations d’identité affirmées p.</span><span class="sxs-lookup"><span data-stu-id="8e91b-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="8e91b-377">1 signifie que le sens du flux provient de l’appelant vers l’appelant ; 0 : le sens du flux provient de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8e91b-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

