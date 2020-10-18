---
title: 'Lync Server 2013 : vue AudioStreamDetail'
description: 'Lync Server 2013 : vue AudioStreamDetail.'
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573050"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="4b9d6-103">Vue AudioStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b9d6-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9d6-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4b9d6-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4b9d6-105">L’affichage AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="4b9d6-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b9d6-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="4b9d6-107">Column</span></span></th>
<th><span data-ttu-id="4b9d6-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="4b9d6-108">Data Type</span></span></th>
<th><span data-ttu-id="4b9d6-109">Détails</span><span class="sxs-lookup"><span data-stu-id="4b9d6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="4b9d6-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4b9d6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-112">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="4b9d6-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-114">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-114">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-115">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="4b9d6-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-117">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-117">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-118">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="4b9d6-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4b9d6-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-121">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="4b9d6-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4b9d6-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-124">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="4b9d6-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-126">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-126">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-127">Catégorie de boîte de dialogue : 0 est le serveur Lync Server vers le tronçon de serveur de médiation ; 1 est le serveur de médiation pour la partie passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="4b9d6-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-129">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-129">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-130">Indicateur signalant si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="4b9d6-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-132">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-132">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p102">Si une valeur est présente, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="4b9d6-135">0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="4b9d6-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-137">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-137">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-138">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="4b9d6-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-141">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="4b9d6-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-144">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-145">Appelant</span><span class="sxs-lookup"><span data-stu-id="4b9d6-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-147">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-148">Appelé</span><span class="sxs-lookup"><span data-stu-id="4b9d6-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-150">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="4b9d6-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-153">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4b9d6-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-155">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-156">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="4b9d6-157">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4b9d6-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-160">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="4b9d6-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="4b9d6-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-164">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4b9d6-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-166">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-167">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-167">Type of callee’s user agent.</span></span> <span data-ttu-id="4b9d6-168">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4b9d6-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-171">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-171">Category of callee’s user agent.</span></span> <span data-ttu-id="4b9d6-172">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d6-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-175">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d6-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-178">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-179">Appelants</span><span class="sxs-lookup"><span data-stu-id="4b9d6-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-181">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-183">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-184">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="4b9d6-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-186">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-187">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="4b9d6-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-189">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-190">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4b9d6-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-192">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-193">Nombre de cœurs de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4b9d6-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-195">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-196">Nombre de cœurs de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="4b9d6-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-198">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-198">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-199">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="4b9d6-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-201">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-201">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-202">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4b9d6-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-204">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-205">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4b9d6-206">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4b9d6-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-208">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-209">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4b9d6-210">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="4b9d6-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b9d6-212">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-212">Correlation key.</span></span> <span data-ttu-id="4b9d6-213">Référencé à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table table sessioncorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="4b9d6-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-215">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-216">Informations de connexion sur le chemin d’accès des médias : directe ou mise en attente, par exemple.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="4b9d6-217">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4b9d6-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-219">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-219">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p111">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4b9d6-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-223">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-223">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p112">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-226">Transport</span><span class="sxs-lookup"><span data-stu-id="4b9d6-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-227">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-228">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="4b9d6-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-231">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-231">IP address of the caller.</span></span> <span data-ttu-id="4b9d6-232">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="4b9d6-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-234">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-234">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-235">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="4b9d6-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-237">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-237">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-238">Indique si l’appelant se trouve à l’intérieur du réseau interne : 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="4b9d6-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-241">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-241">IP address of the callee.</span></span> <span data-ttu-id="4b9d6-242">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="4b9d6-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-244">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-244">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-245">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="4b9d6-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-247">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-247">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-248">Indique si l’appelé se trouve à l’intérieur du réseau interne : 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="4b9d6-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-250">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-251">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="4b9d6-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-253">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-254">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="4b9d6-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-256">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-257">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="4b9d6-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-259">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4b9d6-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-260">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4b9d6-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-263">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4b9d6-264">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="4b9d6-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-266">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-266">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-267">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4b9d6-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-270">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4b9d6-271">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4b9d6-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-273">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-273">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-274">Port utilisé sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4b9d6-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-277">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="4b9d6-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-280">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4b9d6-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-283">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="4b9d6-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-286">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4b9d6-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-289">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="4b9d6-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-292">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4b9d6-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-295">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4b9d6-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-298">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4b9d6-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-300">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-301">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="4b9d6-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-303">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-303">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-304">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4b9d6-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-306">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-307">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4b9d6-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-309">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-310">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="4b9d6-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-312">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-312">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-313">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4b9d6-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-315">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-316">Vitesse de la liaison réseau pour le système d’extrémité de l’appelé, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-318">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-319">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-321">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-321">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p117">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="4b9d6-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-326">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-326">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-327">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="4b9d6-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-329">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-329">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-330">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-332">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-333">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="4b9d6-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-335">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-336">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="4b9d6-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-338">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-339">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="4b9d6-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-341">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-341">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-342">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="4b9d6-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-344">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-345">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="4b9d6-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-347">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-347">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-348">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="4b9d6-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-350">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-350">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-351">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-352">Bande passante</span><span class="sxs-lookup"><span data-stu-id="4b9d6-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-353">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-353">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-354">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-356">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p118">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="4b9d6-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-362">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-363">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-365">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-366">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-368">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-369">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="4b9d6-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-371">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-371">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-372">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-374">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-374">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-375">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-377">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-377">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p119">Niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-383">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-383">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p120">Niveau de signal audio pour les données audio reçues par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-389">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-389">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p121">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-395">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-395">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p122">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé reçu par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="4b9d6-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-401">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-401">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p123">Amélioration de la perte du retour d’écho pour l’appelant. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-407">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-407">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p124">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-412">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-412">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p125">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="4b9d6-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-417">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-418">Débit de dérive de l’horloge du microphone de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="4b9d6-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-420">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-421">Débit de dérive de l’horloge du haut-parleur de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="4b9d6-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-423">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-424">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="4b9d6-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-426">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-427">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelant, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="4b9d6-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-429">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-430">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="4b9d6-431">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="4b9d6-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-433">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-434">Causes d’un événement d’écho pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="4b9d6-435">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="4b9d6-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-437">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p128">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelant. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="4b9d6-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-441">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p129">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelant. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-445">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-445">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p130">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-450">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-450">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p131">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="4b9d6-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-456">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-456">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-457">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-459">float</span><span class="sxs-lookup"><span data-stu-id="4b9d6-459">float</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-460">Valeur quadratique moyenne du signal entant pour l’appelant au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-462">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-462">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p132">Représente le niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-468">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-468">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p133">Niveau de signal audio pour les données audio reçues par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-474">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-474">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p134">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-480">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-480">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p135">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio reçu par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="4b9d6-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-486">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-486">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p136">Amélioration de la perte du retour d’écho pour l’appelé. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-492">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-492">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p137">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4b9d6-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-497">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-497">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p138">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="4b9d6-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-502">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-503">Débit de dérive de l’horloge du microphone de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="4b9d6-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-505">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-506">Débit de dérive de l’horloge du haut-parleur de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="4b9d6-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-508">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-509">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="4b9d6-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-511">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-512">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelé, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="4b9d6-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-514">type</span><span class="sxs-lookup"><span data-stu-id="4b9d6-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-515">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="4b9d6-516">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="4b9d6-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-518">entier très petit</span><span class="sxs-lookup"><span data-stu-id="4b9d6-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-519">Causes d’un événement d’écho pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="4b9d6-520">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="4b9d6-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-522">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p141">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelé. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="4b9d6-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-526">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p142">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-530">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-530">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p143">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4b9d6-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-535">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-535">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p144">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="4b9d6-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-541">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-541">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-542">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-544">float</span><span class="sxs-lookup"><span data-stu-id="4b9d6-544">float</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-545">Valeur quadratique moyenne du signal entant pour l’appelé au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-547">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-548">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-550">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-551">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4b9d6-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-553">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-554">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-555">Retour</span><span class="sxs-lookup"><span data-stu-id="4b9d6-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-556">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-556">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-557">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="4b9d6-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-559">int</span><span class="sxs-lookup"><span data-stu-id="4b9d6-559">int</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-560">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-562">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-p145">Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est comprise entre 1.0 et 5.0.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-567">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-568">Note MOS qualité réseau minimale en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-570">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-571">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="4b9d6-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-573">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-574">Valeur SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="4b9d6-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-576">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-577">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="4b9d6-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-579">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4b9d6-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-580">Valeur RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b9d6-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="4b9d6-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-582">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-582">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-583">Indique si la FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b9d6-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="4b9d6-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-585">légèrement</span><span class="sxs-lookup"><span data-stu-id="4b9d6-585">bit</span></span></p></td>
<td><p><span data-ttu-id="4b9d6-586">Indique la direction des informations PAI (P-Asserted-Identity) : 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

