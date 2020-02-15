---
title: 'Lync Server 2013 : vue AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11279857e7bf217d311f4f2eb0a54a5d5f628084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="91215-102">Vue AudioStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91215-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91215-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="91215-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="91215-104">L’affichage AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="91215-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="91215-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91215-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91215-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="91215-106">Column</span></span></th>
<th><span data-ttu-id="91215-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="91215-107">Data Type</span></span></th>
<th><span data-ttu-id="91215-108">Détails</span><span class="sxs-lookup"><span data-stu-id="91215-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91215-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="91215-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="91215-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="91215-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="91215-111">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="91215-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="91215-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="91215-113">int</span><span class="sxs-lookup"><span data-stu-id="91215-113">int</span></span></p></td>
<td><p><span data-ttu-id="91215-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="91215-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="91215-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="91215-116">int</span><span class="sxs-lookup"><span data-stu-id="91215-116">int</span></span></p></td>
<td><p><span data-ttu-id="91215-117">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="91215-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="91215-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="91215-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="91215-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="91215-120">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="91215-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="91215-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="91215-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="91215-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="91215-123">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="91215-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="91215-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="91215-125">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-125">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-126">Catégorie de boîte de dialogue : 0 est le serveur Lync Server vers le tronçon de serveur de médiation ; 1 est le serveur de médiation pour la partie passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="91215-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="91215-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="91215-128">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-128">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-129">Indicateur signalant si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="91215-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="91215-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="91215-131">int</span><span class="sxs-lookup"><span data-stu-id="91215-131">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p102">Si une valeur est présente, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="91215-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="91215-134">0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="91215-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="91215-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="91215-136">int</span><span class="sxs-lookup"><span data-stu-id="91215-136">int</span></span></p></td>
<td><p><span data-ttu-id="91215-137">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="91215-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="91215-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-140">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="91215-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="91215-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="91215-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-143">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="91215-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-144">Appelant</span><span class="sxs-lookup"><span data-stu-id="91215-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="91215-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91215-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91215-146">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-147">Appelé</span><span class="sxs-lookup"><span data-stu-id="91215-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="91215-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91215-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91215-149">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="91215-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="91215-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-152">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="91215-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="91215-154">type</span><span class="sxs-lookup"><span data-stu-id="91215-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-155">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="91215-156">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="91215-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="91215-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="91215-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="91215-159">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="91215-160">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="91215-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="91215-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-163">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="91215-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="91215-165">type</span><span class="sxs-lookup"><span data-stu-id="91215-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-166">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-166">Type of callee’s user agent.</span></span> <span data-ttu-id="91215-167">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="91215-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="91215-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="91215-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="91215-170">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-170">Category of callee’s user agent.</span></span> <span data-ttu-id="91215-171">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="91215-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="91215-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-174">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="91215-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="91215-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-177">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-178">Appelants</span><span class="sxs-lookup"><span data-stu-id="91215-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="91215-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-180">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="91215-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="91215-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-183">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="91215-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="91215-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-186">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="91215-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="91215-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-189">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="91215-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="91215-191">type</span><span class="sxs-lookup"><span data-stu-id="91215-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-192">Nombre de cœurs de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="91215-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="91215-194">type</span><span class="sxs-lookup"><span data-stu-id="91215-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-195">Nombre de cœurs de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="91215-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="91215-197">int</span><span class="sxs-lookup"><span data-stu-id="91215-197">int</span></span></p></td>
<td><p><span data-ttu-id="91215-198">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="91215-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="91215-200">int</span><span class="sxs-lookup"><span data-stu-id="91215-200">int</span></span></p></td>
<td><p><span data-ttu-id="91215-201">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="91215-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="91215-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-204">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="91215-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="91215-205">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="91215-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="91215-207">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-208">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="91215-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="91215-209">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="91215-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91215-211">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="91215-211">Correlation key.</span></span> <span data-ttu-id="91215-212">Référencé à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table table sessioncorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="91215-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="91215-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="91215-214">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-215">Informations de connexion sur le chemin d’accès des médias : directe ou mise en attente, par exemple.</span><span class="sxs-lookup"><span data-stu-id="91215-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="91215-216">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="91215-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="91215-218">int</span><span class="sxs-lookup"><span data-stu-id="91215-218">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p111">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="91215-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="91215-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="91215-222">int</span><span class="sxs-lookup"><span data-stu-id="91215-222">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p112">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="91215-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-225">Transport</span><span class="sxs-lookup"><span data-stu-id="91215-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="91215-226">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-227">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="91215-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="91215-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="91215-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="91215-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="91215-230">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-230">IP address of the caller.</span></span> <span data-ttu-id="91215-231">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="91215-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="91215-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="91215-233">int</span><span class="sxs-lookup"><span data-stu-id="91215-233">int</span></span></p></td>
<td><p><span data-ttu-id="91215-234">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="91215-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="91215-236">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-236">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-237">Indique si l’appelant se trouve à l’intérieur du réseau interne : 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="91215-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="91215-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="91215-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="91215-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="91215-240">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-240">IP address of the callee.</span></span> <span data-ttu-id="91215-241">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="91215-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="91215-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="91215-243">int</span><span class="sxs-lookup"><span data-stu-id="91215-243">int</span></span></p></td>
<td><p><span data-ttu-id="91215-244">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="91215-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="91215-246">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-246">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-247">Indique si l’appelé se trouve à l’intérieur du réseau interne : 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="91215-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="91215-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="91215-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-250">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="91215-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="91215-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-253">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="91215-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="91215-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-256">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="91215-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="91215-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91215-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="91215-259">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="91215-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="91215-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="91215-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="91215-262">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="91215-263">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="91215-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="91215-265">int</span><span class="sxs-lookup"><span data-stu-id="91215-265">int</span></span></p></td>
<td><p><span data-ttu-id="91215-266">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="91215-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="91215-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="91215-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="91215-269">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="91215-270">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="91215-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="91215-272">int</span><span class="sxs-lookup"><span data-stu-id="91215-272">int</span></span></p></td>
<td><p><span data-ttu-id="91215-273">Port utilisé sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="91215-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="91215-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-276">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="91215-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="91215-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-279">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="91215-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="91215-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-282">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="91215-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="91215-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-285">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="91215-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="91215-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-288">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="91215-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="91215-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-291">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="91215-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="91215-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-294">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="91215-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="91215-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91215-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91215-297">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="91215-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="91215-299">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-300">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="91215-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="91215-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="91215-302">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-302">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-303">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="91215-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="91215-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="91215-305">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="91215-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="91215-306">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="91215-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="91215-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="91215-308">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-309">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="91215-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="91215-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="91215-311">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-311">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-312">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="91215-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="91215-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="91215-314">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="91215-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="91215-315">Vitesse de la liaison réseau pour le système d’extrémité de l’appelé, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="91215-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="91215-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="91215-317">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-318">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="91215-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="91215-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="91215-320">int</span><span class="sxs-lookup"><span data-stu-id="91215-320">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p117">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="91215-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="91215-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="91215-325">int</span><span class="sxs-lookup"><span data-stu-id="91215-325">int</span></span></p></td>
<td><p><span data-ttu-id="91215-326">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="91215-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="91215-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="91215-328">int</span><span class="sxs-lookup"><span data-stu-id="91215-328">int</span></span></p></td>
<td><p><span data-ttu-id="91215-329">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="91215-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="91215-331">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="91215-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="91215-332">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="91215-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="91215-334">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="91215-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="91215-335">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="91215-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="91215-337">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="91215-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="91215-338">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="91215-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="91215-340">int</span><span class="sxs-lookup"><span data-stu-id="91215-340">int</span></span></p></td>
<td><p><span data-ttu-id="91215-341">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="91215-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="91215-343">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="91215-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="91215-344">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="91215-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="91215-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="91215-346">int</span><span class="sxs-lookup"><span data-stu-id="91215-346">int</span></span></p></td>
<td><p><span data-ttu-id="91215-347">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="91215-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="91215-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="91215-349">int</span><span class="sxs-lookup"><span data-stu-id="91215-349">int</span></span></p></td>
<td><p><span data-ttu-id="91215-350">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="91215-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-351">Bande passante</span><span class="sxs-lookup"><span data-stu-id="91215-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="91215-352">int</span><span class="sxs-lookup"><span data-stu-id="91215-352">int</span></span></p></td>
<td><p><span data-ttu-id="91215-353">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="91215-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="91215-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-355">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p118">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="91215-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="91215-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="91215-361">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-362">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="91215-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-364">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-365">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="91215-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="91215-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-367">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-368">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="91215-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="91215-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="91215-370">int</span><span class="sxs-lookup"><span data-stu-id="91215-370">int</span></span></p></td>
<td><p><span data-ttu-id="91215-371">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="91215-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="91215-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="91215-373">int</span><span class="sxs-lookup"><span data-stu-id="91215-373">int</span></span></p></td>
<td><p><span data-ttu-id="91215-374">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="91215-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-376">int</span><span class="sxs-lookup"><span data-stu-id="91215-376">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p119">Niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-382">int</span><span class="sxs-lookup"><span data-stu-id="91215-382">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p120">Niveau de signal audio pour les données audio reçues par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-388">int</span><span class="sxs-lookup"><span data-stu-id="91215-388">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p121">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-394">int</span><span class="sxs-lookup"><span data-stu-id="91215-394">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p122">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé reçu par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="91215-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="91215-400">int</span><span class="sxs-lookup"><span data-stu-id="91215-400">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p123">Amélioration de la perte du retour d’écho pour l’appelant. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="91215-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="91215-406">int</span><span class="sxs-lookup"><span data-stu-id="91215-406">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p124">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="91215-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="91215-411">int</span><span class="sxs-lookup"><span data-stu-id="91215-411">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p125">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="91215-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="91215-416">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-417">Débit de dérive de l’horloge du microphone de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="91215-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="91215-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="91215-419">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-420">Débit de dérive de l’horloge du haut-parleur de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="91215-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="91215-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="91215-422">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-423">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="91215-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="91215-425">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-426">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelant, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="91215-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="91215-428">type</span><span class="sxs-lookup"><span data-stu-id="91215-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-429">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="91215-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="91215-430">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="91215-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="91215-432">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-433">Causes d’un événement d’écho pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="91215-434">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="91215-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="91215-436">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p128">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelant. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="91215-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="91215-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="91215-440">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p129">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelant. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="91215-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-444">int</span><span class="sxs-lookup"><span data-stu-id="91215-444">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p130">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="91215-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-449">int</span><span class="sxs-lookup"><span data-stu-id="91215-449">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p131">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="91215-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="91215-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="91215-455">int</span><span class="sxs-lookup"><span data-stu-id="91215-455">int</span></span></p></td>
<td><p><span data-ttu-id="91215-456">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="91215-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="91215-458">flottant</span><span class="sxs-lookup"><span data-stu-id="91215-458">float</span></span></p></td>
<td><p><span data-ttu-id="91215-459">Valeur quadratique moyenne du signal entant pour l’appelant au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-461">int</span><span class="sxs-lookup"><span data-stu-id="91215-461">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p132">Représente le niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-467">int</span><span class="sxs-lookup"><span data-stu-id="91215-467">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p133">Niveau de signal audio pour les données audio reçues par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-473">int</span><span class="sxs-lookup"><span data-stu-id="91215-473">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p134">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-479">int</span><span class="sxs-lookup"><span data-stu-id="91215-479">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p135">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio reçu par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="91215-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="91215-485">int</span><span class="sxs-lookup"><span data-stu-id="91215-485">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p136">Amélioration de la perte du retour d’écho pour l’appelé. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="91215-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="91215-491">int</span><span class="sxs-lookup"><span data-stu-id="91215-491">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p137">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="91215-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="91215-496">int</span><span class="sxs-lookup"><span data-stu-id="91215-496">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p138">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="91215-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="91215-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="91215-501">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-502">Débit de dérive de l’horloge du microphone de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="91215-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="91215-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="91215-504">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-505">Débit de dérive de l’horloge du haut-parleur de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="91215-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="91215-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="91215-507">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-508">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="91215-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="91215-510">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-511">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelé, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="91215-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="91215-513">type</span><span class="sxs-lookup"><span data-stu-id="91215-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="91215-514">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="91215-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="91215-515">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="91215-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="91215-517">entier très petit</span><span class="sxs-lookup"><span data-stu-id="91215-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="91215-518">Causes d’un événement d’écho pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="91215-519">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91215-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="91215-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="91215-521">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p141">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelé. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="91215-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="91215-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="91215-525">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p142">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="91215-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="91215-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-529">int</span><span class="sxs-lookup"><span data-stu-id="91215-529">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p143">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="91215-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="91215-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="91215-534">int</span><span class="sxs-lookup"><span data-stu-id="91215-534">int</span></span></p></td>
<td><p><span data-ttu-id="91215-p144">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="91215-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="91215-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="91215-540">int</span><span class="sxs-lookup"><span data-stu-id="91215-540">int</span></span></p></td>
<td><p><span data-ttu-id="91215-541">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="91215-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="91215-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="91215-543">flottant</span><span class="sxs-lookup"><span data-stu-id="91215-543">float</span></span></p></td>
<td><p><span data-ttu-id="91215-544">Valeur quadratique moyenne du signal entant pour l’appelé au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="91215-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-546">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-547">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="91215-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="91215-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-549">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-550">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="91215-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="91215-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="91215-552">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-553">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="91215-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-554">Retour</span><span class="sxs-lookup"><span data-stu-id="91215-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="91215-555">int</span><span class="sxs-lookup"><span data-stu-id="91215-555">int</span></span></p></td>
<td><p><span data-ttu-id="91215-556">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="91215-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="91215-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="91215-558">int</span><span class="sxs-lookup"><span data-stu-id="91215-558">int</span></span></p></td>
<td><p><span data-ttu-id="91215-559">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="91215-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="91215-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="91215-561">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-p145">Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est comprise entre 1.0 et 5.0.</span><span class="sxs-lookup"><span data-stu-id="91215-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="91215-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="91215-566">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-567">Note MOS qualité réseau minimale en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="91215-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="91215-569">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-570">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="91215-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="91215-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="91215-572">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-573">Valeur SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="91215-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="91215-575">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-576">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="91215-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="91215-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="91215-578">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="91215-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="91215-579">Valeur RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91215-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="91215-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="91215-581">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-581">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-582">Indique si la FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="91215-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91215-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="91215-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="91215-584">légèrement</span><span class="sxs-lookup"><span data-stu-id="91215-584">bit</span></span></p></td>
<td><p><span data-ttu-id="91215-585">Indique la direction des informations PAI (P-Asserted-Identity) : 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="91215-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

