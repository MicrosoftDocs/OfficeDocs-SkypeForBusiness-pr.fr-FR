---
title: 'Lync Server 2013 : vue de session'
description: 'Lync Server 2013 : vue de session.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545010"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b36b4-103">Vue de session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36b4-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b36b4-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b36b4-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b36b4-105">L’affichage Session stocke des informations sur les sessions pour lesquelles il existe des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b36b4-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b36b4-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b36b4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b36b4-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="b36b4-107">Column</span></span></th>
<th><span data-ttu-id="b36b4-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="b36b4-108">Data Type</span></span></th>
<th><span data-ttu-id="b36b4-109">Détails</span><span class="sxs-lookup"><span data-stu-id="b36b4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b36b4-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b36b4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-112">Référencé depuis la table MediaLine.</span><span class="sxs-lookup"><span data-stu-id="b36b4-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b36b4-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b36b4-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b36b4-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-115">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="b36b4-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="b36b4-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b36b4-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b36b4-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-118">ID de corrélation de la session.</span><span class="sxs-lookup"><span data-stu-id="b36b4-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b36b4-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b36b4-120">légèrement</span><span class="sxs-lookup"><span data-stu-id="b36b4-120">bit</span></span></p></td>
<td><p><span data-ttu-id="b36b4-121">Catégorie de boîte de dialogue ; 0 est le tronçon Lync Server vers serveur de médiation ; 1 est le serveur de médiation au tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="b36b4-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b36b4-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b36b4-123">légèrement</span><span class="sxs-lookup"><span data-stu-id="b36b4-123">bit</span></span></p></td>
<td><p><span data-ttu-id="b36b4-124">Indique si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="b36b4-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b36b4-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b36b4-126">int</span><span class="sxs-lookup"><span data-stu-id="b36b4-126">int</span></span></p></td>
<td><p><span data-ttu-id="b36b4-127">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient.</span><span class="sxs-lookup"><span data-stu-id="b36b4-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b36b4-128">Pour Lync Server, une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="b36b4-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b36b4-129">0x0001 – ID de contournement inconnu pour la carte réseau par défaut</span><span class="sxs-lookup"><span data-stu-id="b36b4-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="b36b4-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b36b4-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-132">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b36b4-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="b36b4-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-134">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b36b4-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="b36b4-135">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b36b4-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b36b4-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b36b4-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-138">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="b36b4-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b36b4-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b36b4-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-141">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="b36b4-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b36b4-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b36b4-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b36b4-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-144">URI P-Asserted-Identity (PAI) de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b36b4-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b36b4-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b36b4-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-147">URI P-Asserted-Identity (PAI) de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b36b4-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b36b4-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b36b4-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-150">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b36b4-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b36b4-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-153">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b36b4-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b36b4-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-156">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b36b4-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b36b4-158">type</span><span class="sxs-lookup"><span data-stu-id="b36b4-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="b36b4-159">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-159">Type of caller’s user agent.</span></span> <span data-ttu-id="b36b4-160">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b36b4-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b36b4-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b36b4-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b36b4-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-163">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-163">Category of caller’s user agent.</span></span> <span data-ttu-id="b36b4-164">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b36b4-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b36b4-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b36b4-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b36b4-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-167">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b36b4-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b36b4-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b36b4-169">type</span><span class="sxs-lookup"><span data-stu-id="b36b4-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="b36b4-170">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b36b4-170">Type of user agent for the callee.</span></span> <span data-ttu-id="b36b4-171">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b36b4-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b36b4-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b36b4-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b36b4-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-174">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b36b4-174">User agent category for the callee.</span></span> <span data-ttu-id="b36b4-175">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b36b4-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b36b4-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b36b4-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b36b4-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-178">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b36b4-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36b4-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b36b4-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b36b4-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b36b4-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b36b4-181">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b36b4-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36b4-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="b36b4-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b36b4-183">int</span><span class="sxs-lookup"><span data-stu-id="b36b4-183">int</span></span></p></td>
<td><p><span data-ttu-id="b36b4-184">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b36b4-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

