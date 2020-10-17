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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515781"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e3d0c-102">Vue AudioStreamDetail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3d0c-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3d0c-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e3d0c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e3d0c-104">L’affichage AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="e3d0c-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3d0c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e3d0c-106">Column</span></span></th>
<th><span data-ttu-id="e3d0c-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="e3d0c-107">Data Type</span></span></th>
<th><span data-ttu-id="e3d0c-108">Détails</span><span class="sxs-lookup"><span data-stu-id="e3d0c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e3d0c-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3d0c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-111">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e3d0c-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-113">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-113">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="e3d0c-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-116">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-116">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-117">ID unique dans une ligne de média.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="e3d0c-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3d0c-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-120">Heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="e3d0c-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3d0c-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-123">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="e3d0c-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-125">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-125">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-126">Catégorie de boîte de dialogue : 0 est le serveur Lync Server vers le tronçon de serveur de médiation ; 1 est le serveur de médiation pour la partie passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="e3d0c-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-128">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-128">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-129">Indicateur signalant si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="e3d0c-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-131">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-131">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p102">Si une valeur est présente, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="e3d0c-134">0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e3d0c-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-136">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-136">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-137">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e3d0c-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-140">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e3d0c-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-143">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-144">Appelant</span><span class="sxs-lookup"><span data-stu-id="e3d0c-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-146">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-147">Appelé</span><span class="sxs-lookup"><span data-stu-id="e3d0c-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-149">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e3d0c-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-152">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e3d0c-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-154">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-155">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="e3d0c-156">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e3d0c-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-159">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="e3d0c-160">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e3d0c-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-163">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e3d0c-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-165">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-166">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-166">Type of callee’s user agent.</span></span> <span data-ttu-id="e3d0c-167">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e3d0c-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-170">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-170">Category of callee’s user agent.</span></span> <span data-ttu-id="e3d0c-171">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e3d0c-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-174">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e3d0c-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-177">Nom du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-178">Appelants</span><span class="sxs-lookup"><span data-stu-id="e3d0c-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-180">Système d’exploitation (OS) du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-183">Système d’exploitation (OS) du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e3d0c-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-186">Nom de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e3d0c-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-189">Nom de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e3d0c-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-191">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-192">Nombre de cœurs de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e3d0c-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-194">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-195">Nombre de cœurs de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e3d0c-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-197">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-197">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-198">Vitesse du processeur de l’UC du système d’extrémité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e3d0c-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-200">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-200">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-201">Vitesse du processeur de l’UC du système d’extrémité de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e3d0c-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-203">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-204">Indique si le système de l’appelant s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e3d0c-205">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e3d0c-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-207">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-208">Indique si le système de l’appelé s’exécute dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e3d0c-209">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-endpoint-table.md">tableau de points de terminaison dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="e3d0c-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3d0c-211">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-211">Correlation key.</span></span> <span data-ttu-id="e3d0c-212">Référencé à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table table sessioncorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e3d0c-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-214">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-215">Informations de connexion sur le chemin d’accès des médias : directe ou mise en attente, par exemple.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="e3d0c-216">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e3d0c-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-218">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-218">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p111">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e3d0c-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-222">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-222">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p112">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-225">Transport</span><span class="sxs-lookup"><span data-stu-id="e3d0c-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-226">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-227">Type de transport : 0 correspond à UDP, 1 correspond à TCP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e3d0c-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-230">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-230">IP address of the caller.</span></span> <span data-ttu-id="e3d0c-231">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e3d0c-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-233">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-233">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-234">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e3d0c-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-236">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-237">Indique si l’appelant se trouve à l’intérieur du réseau interne : 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e3d0c-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-240">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-240">IP address of the callee.</span></span> <span data-ttu-id="e3d0c-241">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e3d0c-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-243">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-243">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-244">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e3d0c-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-246">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-246">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-247">Indique si l’appelé se trouve à l’intérieur du réseau interne : 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e3d0c-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-250">Nom du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e3d0c-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-253">Nom du pays/de la région du site de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e3d0c-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-256">Nom du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e3d0c-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3d0c-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-259">Nom du pays/de la région du site de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e3d0c-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-262">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e3d0c-263">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e3d0c-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-265">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-265">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-266">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e3d0c-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-269">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e3d0c-270">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e3d0c-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-272">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-272">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-273">Port utilisé sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e3d0c-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-276">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e3d0c-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-279">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e3d0c-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-282">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="e3d0c-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-285">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e3d0c-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-288">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e3d0c-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-291">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e3d0c-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-294">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e3d0c-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-297">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e3d0c-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-299">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-300">Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e3d0c-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-302">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-303">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e3d0c-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-305">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-306">Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e3d0c-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-308">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-309">Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e3d0c-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-311">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-311">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-312">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e3d0c-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-314">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-315">Vitesse de la liaison réseau pour le système d’extrémité de l’appelé, en bits/s.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-317">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-318">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="e3d0c-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-320">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-320">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p117">Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e3d0c-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-325">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-325">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-326">Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="e3d0c-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e3d0c-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-328">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-328">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-329">Gigue réseau maximum pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-331">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-332">Taux moyen de perte de paquets pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e3d0c-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-334">décimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-335">Perte maximale de paquets observée pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="e3d0c-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-337">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-338">Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="e3d0c-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-340">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-340">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-341">Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="e3d0c-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-343">décimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-344">Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="e3d0c-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-346">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-346">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-347">Durée moyenne des intervalles entre les rafales de pertes de paquets.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e3d0c-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-349">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-349">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-350">Nombre de paquets pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-351">Bande passante</span><span class="sxs-lookup"><span data-stu-id="e3d0c-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-352">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-352">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-353">Estimations de la bande passante pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-355">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p118">Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="e3d0c-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-361">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-362">Dégradation de la note MOS qualité réseau maximale pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-364">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-365">Dégradation de la note MOS qualité réseau causée par la gigue.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-367">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-368">Dégradation de la note MOS qualité réseau causée par la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e3d0c-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-370">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-370">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-371">Codec audio utilisé pour l’appel, référencé à partir de la <a href="lync-server-2013-payloaddescription-table.md">table PayloadDescription dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-373">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-373">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-374">Taux d’échantillonnage pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-376">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-376">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p119">Niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-382">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-382">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p120">Niveau de signal audio pour les données audio reçues par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-388">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-388">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p121">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-394">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-394">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p122">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé reçu par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e3d0c-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-400">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-400">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p123">Amélioration de la perte du retour d’écho pour l’appelant. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-406">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-406">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p124">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-411">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-411">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p125">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e3d0c-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-416">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-417">Débit de dérive de l’horloge du microphone de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e3d0c-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-419">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-420">Débit de dérive de l’horloge du haut-parleur de l’appelant, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e3d0c-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-422">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-423">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e3d0c-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-425">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-426">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelant, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e3d0c-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-428">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-429">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e3d0c-430">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e3d0c-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-432">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-433">Causes d’un événement d’écho pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="e3d0c-434">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e3d0c-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-436">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p128">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelant. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e3d0c-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-440">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p129">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelant. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-444">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-444">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p130">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-449">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-449">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p131">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelant. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e3d0c-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-455">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-455">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-456">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-458">float</span><span class="sxs-lookup"><span data-stu-id="e3d0c-458">float</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-459">Valeur quadratique moyenne du signal entant pour l’appelant au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-461">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-461">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p132">Représente le niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-467">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-467">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p133">Niveau de signal audio pour les données audio reçues par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-473">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-473">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p134">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-479">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-479">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p135">Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio reçu par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e3d0c-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-485">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-485">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p136">Amélioration de la perte du retour d’écho pour l’appelé. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-491">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-491">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p137">Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e3d0c-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-496">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-496">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p138">Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e3d0c-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-501">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-502">Débit de dérive de l’horloge du microphone de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e3d0c-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-504">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-505">Débit de dérive de l’horloge du haut-parleur de l’appelé, relativement à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e3d0c-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-507">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-508">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e3d0c-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-510">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-511">Durée moyenne d’erreur d’horodatage du flux de capture du rendu des haut-parleurs de l’appelé, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e3d0c-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-513">type</span><span class="sxs-lookup"><span data-stu-id="e3d0c-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-514">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e3d0c-515">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e3d0c-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-517">entier très petit</span><span class="sxs-lookup"><span data-stu-id="e3d0c-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-518">Causes d’un événement d’écho pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="e3d0c-519">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3d0c-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e3d0c-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-521">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p141">Pourcentage de temps pendant lequel un écho est détecté dans le flux de capture du microphone de l’appelé. Si un casque est utilisé, cette valeur doit être faible.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e3d0c-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-525">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p142">Pourcentage de temps pendant lequel un écho est détecté dans le flux d’envoi de l’appelé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-529">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-529">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p143">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e3d0c-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-534">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-534">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p144">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour le contenu audio de l’appelé. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e3d0c-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-540">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-540">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-541">Réglage de la puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-543">float</span><span class="sxs-lookup"><span data-stu-id="e3d0c-543">float</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-544">Valeur quadratique moyenne du signal entant pour l’appelé au cours des 30 premières secondes au maximum de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-546">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-547">Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-549">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-550">Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e3d0c-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-552">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-553">Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-554">Retour</span><span class="sxs-lookup"><span data-stu-id="e3d0c-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-555">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-555">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-556">Durée d’aller-retour d’après les statistiques RTCP.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e3d0c-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-558">int</span><span class="sxs-lookup"><span data-stu-id="e3d0c-558">int</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-559">Durée d’aller-retour maximale pour le flux audio.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-561">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-p145">Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est comprise entre 1.0 et 5.0.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-566">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-567">Note MOS qualité réseau minimale en large bande pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-569">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-570">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e3d0c-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-572">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-573">Valeur SendListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="e3d0c-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-575">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-576">Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e3d0c-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-578">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e3d0c-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-579">Valeur RecvListenMOS minimale pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3d0c-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="e3d0c-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-581">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-581">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-582">Indique si la FEC audio a été utilisée pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3d0c-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e3d0c-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-584">légèrement</span><span class="sxs-lookup"><span data-stu-id="e3d0c-584">bit</span></span></p></td>
<td><p><span data-ttu-id="e3d0c-585">Indique la direction des informations PAI (P-Asserted-Identity) : 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e3d0c-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

