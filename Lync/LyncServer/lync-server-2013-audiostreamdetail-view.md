---
title: 'Affichage Lync Server 2013 : AudioStreamDetail'
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
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e5c48-102">Affichage AudioStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5c48-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c48-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e5c48-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e5c48-104">Le mode AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5c48-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="e5c48-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c48-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5c48-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e5c48-106">Column</span></span></th>
<th><span data-ttu-id="e5c48-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="e5c48-107">Data Type</span></span></th>
<th><span data-ttu-id="e5c48-108">Détails</span><span class="sxs-lookup"><span data-stu-id="e5c48-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e5c48-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e5c48-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-111">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e5c48-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e5c48-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e5c48-113">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-113">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-114">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e5c48-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="e5c48-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e5c48-116">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-116">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-117">IDENTIFIant unique dans une ligne de médias.</span><span class="sxs-lookup"><span data-stu-id="e5c48-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="e5c48-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e5c48-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-120">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="e5c48-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="e5c48-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e5c48-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5c48-123">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e5c48-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="e5c48-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="e5c48-125">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-125">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-126">Catégorie de boîte de dialogue : 0 est le serveur Lync en jambes du serveur de médiation ; 1 est le serveur de médiation pour le tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="e5c48-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="e5c48-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="e5c48-128">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-128">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-129">Indicateur indiquant si l’appel a été ignoré ou non.</span><span class="sxs-lookup"><span data-stu-id="e5c48-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="e5c48-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="e5c48-131">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-131">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-132">Le cas échéant, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent.</span><span class="sxs-lookup"><span data-stu-id="e5c48-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e5c48-133">Une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="e5c48-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="e5c48-134">0x0001-ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="e5c48-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e5c48-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e5c48-136">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-136">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-137">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e5c48-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e5c48-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-140">Nom de domaine complet du pool d’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e5c48-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e5c48-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-143">Nom de domaine complet (FQDN) du pool d’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-144">Appelant</span><span class="sxs-lookup"><span data-stu-id="e5c48-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="e5c48-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5c48-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-146">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-147">Appelé</span><span class="sxs-lookup"><span data-stu-id="e5c48-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="e5c48-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5c48-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-149">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e5c48-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e5c48-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-152">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e5c48-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e5c48-154">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-155">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="e5c48-156">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e5c48-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e5c48-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e5c48-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-159">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="e5c48-160">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e5c48-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e5c48-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-163">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e5c48-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e5c48-165">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-166">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-166">Type of callee’s user agent.</span></span> <span data-ttu-id="e5c48-167">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e5c48-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e5c48-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e5c48-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-170">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-170">Category of callee’s user agent.</span></span> <span data-ttu-id="e5c48-171">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e5c48-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-174">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e5c48-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-177">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-178">Appelant</span><span class="sxs-lookup"><span data-stu-id="e5c48-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-180">Système d’exploitation (se) du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-183">Système d’exploitation (se) du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e5c48-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e5c48-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-186">Nom de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e5c48-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e5c48-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-189">Nom de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e5c48-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e5c48-191">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-192">Nombre de cœurs d’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e5c48-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e5c48-194">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-195">Nombre de cœurs d’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e5c48-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5c48-197">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-197">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-198">Vitesse de processeur de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e5c48-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5c48-200">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-200">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-201">Vitesse de processeur de l’UC du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e5c48-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e5c48-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-204">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e5c48-205">Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e5c48-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e5c48-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-208">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e5c48-209">Pour plus d’informations, voir la <a href="lync-server-2013-endpoint-table.md">table Endpoint dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="e5c48-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5c48-211">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="e5c48-211">Correlation key.</span></span> <span data-ttu-id="e5c48-212">Fait référence à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table SessionCorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e5c48-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e5c48-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e5c48-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-215">Des informations sur le chemin multimédia, par exemple direct ou relayé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="e5c48-216">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e5c48-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e5c48-218">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-218">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-219">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="e5c48-220">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="e5c48-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e5c48-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e5c48-222">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-222">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-223">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="e5c48-224">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="e5c48-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-225">Transport</span><span class="sxs-lookup"><span data-stu-id="e5c48-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="e5c48-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-227">Le type de transport : 0 correspond au protocole UDP ; 1 est le protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5c48-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5c48-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="e5c48-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-230">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-230">IP address of the caller.</span></span> <span data-ttu-id="e5c48-231">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="e5c48-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e5c48-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e5c48-233">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-233">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-234">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e5c48-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e5c48-236">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-237">Indique si l’appelant se trouve à l’intérieur du réseau intervalle : 1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="e5c48-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5c48-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5c48-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="e5c48-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-240">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-240">IP address of the callee.</span></span> <span data-ttu-id="e5c48-241">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="e5c48-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e5c48-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e5c48-243">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-243">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-244">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e5c48-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e5c48-246">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-246">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-247">Indique si l’appelant se trouve à l’intérieur de l’intervalle réseau : 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="e5c48-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e5c48-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e5c48-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-250">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e5c48-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e5c48-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-253">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e5c48-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e5c48-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-256">Nom du site du ou des appelants.</span><span class="sxs-lookup"><span data-stu-id="e5c48-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e5c48-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e5c48-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e5c48-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-259">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5c48-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5c48-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="e5c48-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-262">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e5c48-263">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e5c48-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e5c48-265">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-265">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-266">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5c48-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5c48-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="e5c48-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-269">Clé d’adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e5c48-270">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e5c48-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e5c48-272">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-272">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-273">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e5c48-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e5c48-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-276">Nom de l’appareil de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e5c48-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e5c48-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-279">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5c48-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5c48-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-282">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="e5c48-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="e5c48-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-285">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e5c48-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e5c48-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-288">Nom de l’appareil de capture du destinataire.</span><span class="sxs-lookup"><span data-stu-id="e5c48-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e5c48-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e5c48-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-291">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5c48-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5c48-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-294">Nom du pilote de l’appareil de capture du appelé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5c48-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5c48-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5c48-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-297">Nom du pilote du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e5c48-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e5c48-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-300">Type de connexion réseau de l’appelant : 0 est filaire, 1 est un réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="e5c48-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e5c48-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e5c48-302">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-303">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="e5c48-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e5c48-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5c48-305">décimale (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e5c48-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-306">Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.</span><span class="sxs-lookup"><span data-stu-id="e5c48-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e5c48-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e5c48-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-309">Type de connexion réseau du ou du destinataire : 0 est filaire, 1 est un téléphone sans fil.</span><span class="sxs-lookup"><span data-stu-id="e5c48-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e5c48-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e5c48-311">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-311">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-312">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="e5c48-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e5c48-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5c48-314">décimale (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e5c48-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-315">Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.</span><span class="sxs-lookup"><span data-stu-id="e5c48-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-317">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-318">La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="e5c48-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e5c48-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-320">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-320">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-321">Bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="e5c48-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="e5c48-322">Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="e5c48-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="e5c48-323">Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitant l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="e5c48-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e5c48-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e5c48-325">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-325">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-326">Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="e5c48-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e5c48-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e5c48-328">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-328">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-329">Scintillement du réseau maximum lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-331">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="e5c48-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-332">Taux moyen de perte de paquets lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e5c48-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e5c48-334">décimale (5 ; 4)</span><span class="sxs-lookup"><span data-stu-id="e5c48-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-335">Perte de paquets maximum observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="e5c48-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="e5c48-337">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="e5c48-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-338">Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="e5c48-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="e5c48-340">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-340">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-341">Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="e5c48-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="e5c48-343">décimale (9 ; 4)</span><span class="sxs-lookup"><span data-stu-id="e5c48-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-344">Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="e5c48-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="e5c48-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="e5c48-346">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-346">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-347">Durée moyenne des espaces entre les pics de perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="e5c48-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e5c48-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e5c48-349">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-349">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-350">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e5c48-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-351">Bande passante</span><span class="sxs-lookup"><span data-stu-id="e5c48-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e5c48-352">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-352">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-353">Estimations de bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e5c48-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-355">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-356">Baisse de la dégradation du réseau pour l’ensemble de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="e5c48-357">La plage est 0,0 à 5,0.</span><span class="sxs-lookup"><span data-stu-id="e5c48-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="e5c48-358">Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="e5c48-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="e5c48-359">Pour une qualité acceptable, elle doit être inférieure à 0,5.</span><span class="sxs-lookup"><span data-stu-id="e5c48-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="e5c48-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="e5c48-361">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-362">Dégradation du réseau maximal pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-364">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-365">Baisse de la dégradation du réseau à l’origine de gigue.</span><span class="sxs-lookup"><span data-stu-id="e5c48-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-367">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-368">Baisse de la dégradation du réseau à l’origine de la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="e5c48-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e5c48-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e5c48-370">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-370">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-371">Le codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e5c48-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-373">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-373">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-374">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e5c48-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-376">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-376">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-377">Le niveau du signal audio après le contrôle de gain analogique pour le son envoyé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="e5c48-378">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-379">Pour une qualité acceptable, il devrait représenter au moins 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5c48-380">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-382">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-382">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-383">Niveau du signal audio de l’appelant reçu.</span><span class="sxs-lookup"><span data-stu-id="e5c48-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="e5c48-384">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-385">Pour une qualité acceptable, il devrait représenter au moins 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5c48-386">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-388">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-388">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-389">Le niveau sonore de contrôle du bruit de l’appelant envoyé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="e5c48-390">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-391">Pour une qualité acceptable, elle doit être inférieure à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5c48-392">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-394">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-394">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-395">Le niveau de bruit audio de contrôle de gain analogique pour le son reçu par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="e5c48-396">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-397">Pour une qualité acceptable, elle doit être inférieure à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5c48-398">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e5c48-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e5c48-400">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-400">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-401">Amélioration de la perte d’écho pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="e5c48-402">L’unité de cette métrique est dB.</span><span class="sxs-lookup"><span data-stu-id="e5c48-402">The unit for this metric is dB.</span></span> <span data-ttu-id="e5c48-403">Les valeurs inférieures représentent moins d’écho.</span><span class="sxs-lookup"><span data-stu-id="e5c48-403">Lower values represent less echo.</span></span> <span data-ttu-id="e5c48-404">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-406">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-406">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-407">Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="e5c48-408">Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="e5c48-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e5c48-409">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-411">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-411">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-412">Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="e5c48-413">Pour une qualité optimale, il devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="e5c48-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e5c48-414">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e5c48-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e5c48-416">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-417">Taux d’utilisation de l’horloge du périphérique microphone de l’appelant par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e5c48-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e5c48-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e5c48-419">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-420">Taux d’horloge des périphériques de haut-parleurs de l’appelant par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e5c48-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e5c48-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e5c48-422">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-423">Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e5c48-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e5c48-425">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-426">Moyenne de l’erreur d’horodatage du flux de haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e5c48-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e5c48-428">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-429">Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite.</span><span class="sxs-lookup"><span data-stu-id="e5c48-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e5c48-430">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e5c48-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e5c48-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-433">Causes d’un événement ECHO pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="e5c48-434">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e5c48-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e5c48-436">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-437">Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du microphone de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="e5c48-438">Si le casque est utilisé, la valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="e5c48-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e5c48-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e5c48-440">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-441">Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="e5c48-442">Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="e5c48-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-444">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-444">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-445">Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant ; Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e5c48-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e5c48-446">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5c48-447">Pour une qualité optimale, la plage acceptable doit être comprise entre-30 et-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-449">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-449">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-450">Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="e5c48-451">Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e5c48-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e5c48-452">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5c48-453">Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e5c48-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e5c48-455">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-455">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-456">Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e5c48-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-458">float</span><span class="sxs-lookup"><span data-stu-id="e5c48-458">float</span></span></p></td>
<td><p><span data-ttu-id="e5c48-459">Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-461">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-461">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-462">Représente le niveau du signal audio du contrôle du gain sur le son de l’appel envoyé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="e5c48-463">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-464">Pour une qualité acceptable, il devrait représenter au moins 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5c48-465">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-467">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-467">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-468">Niveau du signal audio pour le son de l’appelant reçu.</span><span class="sxs-lookup"><span data-stu-id="e5c48-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="e5c48-469">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-470">Pour une qualité acceptable, il devrait représenter au moins 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5c48-471">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-473">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-473">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-474">Le niveau sonore de contrôle du bruit d’après-analogue pour le son de l’appel envoyé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="e5c48-475">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-476">Pour une qualité acceptable, elle doit être inférieure à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5c48-477">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-479">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-479">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-480">Le niveau sonore du contrôle du bruit de la fonction de gain analogique pour le son de l’appelant reçu.</span><span class="sxs-lookup"><span data-stu-id="e5c48-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="e5c48-481">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5c48-482">Pour une qualité acceptable, elle doit être inférieure à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5c48-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5c48-483">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e5c48-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e5c48-485">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-485">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-486">Extension du retour de l’écho pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="e5c48-487">L’unité de cette métrique est dB.</span><span class="sxs-lookup"><span data-stu-id="e5c48-487">The unit for this metric is dB.</span></span> <span data-ttu-id="e5c48-488">Les valeurs inférieures représentent moins d’écho.</span><span class="sxs-lookup"><span data-stu-id="e5c48-488">Lower values represent less echo.</span></span> <span data-ttu-id="e5c48-489">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-491">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-491">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-492">Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="e5c48-493">Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="e5c48-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e5c48-494">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5c48-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5c48-496">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-496">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-497">Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="e5c48-498">Pour une qualité optimale, il devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="e5c48-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e5c48-499">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e5c48-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e5c48-501">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-502">Taux d’utilisation de l’horloge du périphérique du micro du destinataire, par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e5c48-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e5c48-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e5c48-504">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-505">Taux d’horloge de l’horloge du périphérique du présentateur, par rapport à l’horloge du processeur.</span><span class="sxs-lookup"><span data-stu-id="e5c48-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e5c48-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e5c48-507">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-508">Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e5c48-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e5c48-510">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-511">Moyenne de l’erreur d’horodatage du flux de rendu du haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e5c48-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e5c48-513">type</span><span class="sxs-lookup"><span data-stu-id="e5c48-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-514">Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite.</span><span class="sxs-lookup"><span data-stu-id="e5c48-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e5c48-515">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e5c48-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e5c48-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5c48-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5c48-518">Causes d’un événement ECHO pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="e5c48-519">Pour plus d’informations, voir la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5c48-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e5c48-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e5c48-521">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-522">Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du micro de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="e5c48-523">Si le casque est utilisé, la valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="e5c48-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e5c48-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e5c48-525">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-526">Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé du destinataire du appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="e5c48-527">Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="e5c48-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-529">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-529">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-530">Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant ; Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e5c48-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e5c48-531">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5c48-532">Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5c48-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5c48-534">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-534">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-535">Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="e5c48-536">Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e5c48-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e5c48-537">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5c48-538">Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5c48-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e5c48-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e5c48-540">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-540">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-541">Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e5c48-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e5c48-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-543">float</span><span class="sxs-lookup"><span data-stu-id="e5c48-543">float</span></span></p></td>
<td><p><span data-ttu-id="e5c48-544">Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-546">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-547">Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="e5c48-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-549">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-550">Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="e5c48-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5c48-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5c48-552">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-553">Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.</span><span class="sxs-lookup"><span data-stu-id="e5c48-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="e5c48-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e5c48-555">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-555">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-556">Durée de l’aller-retour des statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="e5c48-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e5c48-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e5c48-558">int</span><span class="sxs-lookup"><span data-stu-id="e5c48-558">int</span></span></p></td>
<td><p><span data-ttu-id="e5c48-559">Durée de l’aller-retour maximal pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e5c48-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-561">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-562">MOS du réseau à bandes moyenne pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="e5c48-563">Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés.</span><span class="sxs-lookup"><span data-stu-id="e5c48-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="e5c48-564">La plage est 1,0 à 5,0.</span><span class="sxs-lookup"><span data-stu-id="e5c48-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-566">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-567">Débit du réseau à large bande minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-569">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-570">Score d’écoute de la bande moyenne prédite pour le son envoyé, avec les caractéristiques de niveau de voix, de niveau de bruit et de périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="e5c48-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e5c48-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e5c48-572">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-573">SendListenMOS minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="e5c48-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e5c48-575">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-576">Score d’écoute de la bande moyenne prédite pour le son reçu du réseau, y compris le niveau de synthèse vocale, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.</span><span class="sxs-lookup"><span data-stu-id="e5c48-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e5c48-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e5c48-578">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e5c48-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5c48-579">RecvListenMOS minimum pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c48-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="e5c48-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="e5c48-581">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-581">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-582">Indique si l’audio FEC a été utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5c48-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c48-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e5c48-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e5c48-584">bit</span><span class="sxs-lookup"><span data-stu-id="e5c48-584">bit</span></span></p></td>
<td><p><span data-ttu-id="e5c48-585">Indique la direction des informations d’identification par le biais de la déclaration p ; 1 signifie que le sens du flux provient de l’appelant vers l’appelant ; 0 : le sens du flux provient de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e5c48-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

