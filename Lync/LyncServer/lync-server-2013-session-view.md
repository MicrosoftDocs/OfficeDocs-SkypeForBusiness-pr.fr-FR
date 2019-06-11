---
title: 'Lync Server 2013: vue de session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="81759-102">Affichage de session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81759-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81759-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="81759-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="81759-104">Le mode session stocke les informations sur les sessions contenant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="81759-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="81759-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81759-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81759-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="81759-106">Column</span></span></th>
<th><span data-ttu-id="81759-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="81759-107">Data Type</span></span></th>
<th><span data-ttu-id="81759-108">Détails</span><span class="sxs-lookup"><span data-stu-id="81759-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81759-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="81759-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="81759-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="81759-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="81759-111">Fait référence à partir de la table MediaLine.</span><span class="sxs-lookup"><span data-stu-id="81759-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="81759-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="81759-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="81759-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="81759-114">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="81759-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-115">Correspondance</span><span class="sxs-lookup"><span data-stu-id="81759-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="81759-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="81759-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="81759-117">ID de corrélation de la session.</span><span class="sxs-lookup"><span data-stu-id="81759-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="81759-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="81759-119">bit</span><span class="sxs-lookup"><span data-stu-id="81759-119">bit</span></span></p></td>
<td><p><span data-ttu-id="81759-120">Catégorie de boîte de dialogue. 0 est Lync Server to Mediation Server leg; 1 est un serveur de médiation en tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="81759-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="81759-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="81759-122">bit</span><span class="sxs-lookup"><span data-stu-id="81759-122">bit</span></span></p></td>
<td><p><span data-ttu-id="81759-123">Indique si l’appel a été ignoré.</span><span class="sxs-lookup"><span data-stu-id="81759-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="81759-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="81759-125">int</span><span class="sxs-lookup"><span data-stu-id="81759-125">int</span></span></p></td>
<td><p><span data-ttu-id="81759-126">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent.</span><span class="sxs-lookup"><span data-stu-id="81759-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="81759-127">Pour Lync Server, une seule valeur est définie:</span><span class="sxs-lookup"><span data-stu-id="81759-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="81759-128">0x0001-ID de contournement inconnu pour la carte réseau par défaut</span><span class="sxs-lookup"><span data-stu-id="81759-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="81759-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="81759-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="81759-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="81759-131">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="81759-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="81759-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="81759-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="81759-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="81759-134">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="81759-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="81759-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="81759-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-137">Nom de domaine complet du pool d’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="81759-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="81759-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-140">Nom de domaine complet (FQDN) du pool d’appel.</span><span class="sxs-lookup"><span data-stu-id="81759-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="81759-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="81759-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="81759-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="81759-143">URI d’identité ayant une assertion p d’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="81759-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="81759-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="81759-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="81759-146">URI d’identité affirmée de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="81759-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="81759-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-149">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="81759-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="81759-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-152">Nom du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="81759-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="81759-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-155">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="81759-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="81759-157">type</span><span class="sxs-lookup"><span data-stu-id="81759-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="81759-158">Type de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-158">Type of caller’s user agent.</span></span> <span data-ttu-id="81759-159">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81759-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="81759-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="81759-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="81759-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="81759-162">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-162">Category of caller’s user agent.</span></span> <span data-ttu-id="81759-163">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81759-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="81759-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="81759-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81759-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="81759-166">Chaîne de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="81759-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="81759-168">type</span><span class="sxs-lookup"><span data-stu-id="81759-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="81759-169">Type d’agent utilisateur pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-169">Type of user agent for the callee.</span></span> <span data-ttu-id="81759-170">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81759-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="81759-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="81759-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="81759-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="81759-173">Catégorie de l’agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-173">User agent category for the callee.</span></span> <span data-ttu-id="81759-174">Pour plus d’informations, reportez-vous <a href="lync-server-2013-useragentdef-table-qoe.md">à la table UserAgentDef (QoE) dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81759-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="81759-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="81759-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="81759-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="81759-177">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81759-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="81759-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="81759-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="81759-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="81759-180">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81759-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81759-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="81759-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="81759-182">int</span><span class="sxs-lookup"><span data-stu-id="81759-182">int</span></span></p></td>
<td><p><span data-ttu-id="81759-183">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="81759-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

