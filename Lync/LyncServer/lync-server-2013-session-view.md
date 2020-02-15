---
title: 'Lync Server 2013 : vue de session'
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
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b1554-102">Vue de session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1554-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1554-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b1554-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b1554-104">L’affichage Session stocke des informations sur les sessions pour lesquelles il existe des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b1554-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b1554-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1554-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1554-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b1554-106">Column</span></span></th>
<th><span data-ttu-id="b1554-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="b1554-107">Data Type</span></span></th>
<th><span data-ttu-id="b1554-108">Détails</span><span class="sxs-lookup"><span data-stu-id="b1554-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1554-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b1554-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b1554-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b1554-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b1554-111">Référencé depuis la table MediaLine.</span><span class="sxs-lookup"><span data-stu-id="b1554-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b1554-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b1554-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b1554-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b1554-114">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="b1554-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="b1554-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b1554-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b1554-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b1554-117">ID de corrélation de la session.</span><span class="sxs-lookup"><span data-stu-id="b1554-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b1554-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b1554-119">légèrement</span><span class="sxs-lookup"><span data-stu-id="b1554-119">bit</span></span></p></td>
<td><p><span data-ttu-id="b1554-120">Catégorie de boîte de dialogue ; 0 est le tronçon Lync Server vers serveur de médiation ; 1 est le serveur de médiation au tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="b1554-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b1554-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b1554-122">légèrement</span><span class="sxs-lookup"><span data-stu-id="b1554-122">bit</span></span></p></td>
<td><p><span data-ttu-id="b1554-123">Indique si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="b1554-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b1554-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b1554-125">int</span><span class="sxs-lookup"><span data-stu-id="b1554-125">int</span></span></p></td>
<td><p><span data-ttu-id="b1554-126">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient.</span><span class="sxs-lookup"><span data-stu-id="b1554-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b1554-127">Pour Lync Server, une seule valeur est définie :</span><span class="sxs-lookup"><span data-stu-id="b1554-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b1554-128">0x0001 – ID de contournement inconnu pour la carte réseau par défaut</span><span class="sxs-lookup"><span data-stu-id="b1554-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="b1554-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b1554-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b1554-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b1554-131">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b1554-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="b1554-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b1554-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b1554-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="b1554-134">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b1554-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b1554-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b1554-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-137">Nom de domaine complet du pool des appelants.</span><span class="sxs-lookup"><span data-stu-id="b1554-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b1554-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b1554-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-140">Nom de domaine complet du pool des appelés.</span><span class="sxs-lookup"><span data-stu-id="b1554-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b1554-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b1554-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b1554-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b1554-143">URI P-Asserted-Identity (PAI) de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b1554-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b1554-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b1554-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b1554-146">URI P-Asserted-Identity (PAI) de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b1554-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b1554-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b1554-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-149">Nom du système d’extrémité de l’appelant de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b1554-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b1554-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-152">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b1554-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b1554-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-155">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b1554-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b1554-157">type</span><span class="sxs-lookup"><span data-stu-id="b1554-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b1554-158">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-158">Type of caller’s user agent.</span></span> <span data-ttu-id="b1554-159">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b1554-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b1554-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b1554-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b1554-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b1554-162">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-162">Category of caller’s user agent.</span></span> <span data-ttu-id="b1554-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b1554-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b1554-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b1554-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b1554-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b1554-166">Chaîne de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b1554-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b1554-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b1554-168">type</span><span class="sxs-lookup"><span data-stu-id="b1554-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="b1554-169">Type de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b1554-169">Type of user agent for the callee.</span></span> <span data-ttu-id="b1554-170">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b1554-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b1554-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b1554-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b1554-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b1554-173">Catégorie de l’agent utilisateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b1554-173">User agent category for the callee.</span></span> <span data-ttu-id="b1554-174">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table-qoe.md">table table useragentdef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b1554-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b1554-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b1554-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b1554-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b1554-177">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1554-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1554-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b1554-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b1554-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b1554-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b1554-180">URI de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b1554-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1554-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="b1554-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b1554-182">int</span><span class="sxs-lookup"><span data-stu-id="b1554-182">int</span></span></p></td>
<td><p><span data-ttu-id="b1554-183">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b1554-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

