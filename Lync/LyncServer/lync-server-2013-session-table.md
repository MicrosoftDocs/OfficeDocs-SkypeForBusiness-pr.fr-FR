---
title: 'Lync Server 2013 : table de sessions'
description: 'Lync Server 2013 : table de sessions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576450"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="d5ab1-103">Table session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5ab1-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5ab1-104">_**Dernière modification de la rubrique :** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="d5ab1-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="d5ab1-105">Chaque enregistrement représente une session qui implique l’audio, l’audio et la vidéo.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="d5ab1-106">Il contient des informations générales sur la session.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-106">It contains overall information about the session.</span></span> <span data-ttu-id="d5ab1-107">Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5ab1-108"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d5ab1-109"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d5ab1-110"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d5ab1-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d5ab1-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="d5ab1-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-115">Référencé à partir de la <a href="lync-server-2013-dialog-table.md">table Dialog dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-117">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-117">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-118">Primaire</span><span class="sxs-lookup"><span data-stu-id="d5ab1-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-119">Référencé à partir de la <a href="lync-server-2013-dialog-table.md">table Dialog dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-121">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-121">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-123">Clé de conférence.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-123">Conference key.</span></span> <span data-ttu-id="d5ab1-124">Référencé à partir de la <a href="lync-server-2013-conference-table.md">table Conference dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-126">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-126">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-128">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-128">Correlation key.</span></span> <span data-ttu-id="d5ab1-129">Référencé à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table table sessioncorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-131">légèrement</span><span class="sxs-lookup"><span data-stu-id="d5ab1-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d5ab1-132">Catégorie de boîte de dialogue ; 0 est le tronçon Lync Server vers serveur de médiation ; 1 est le serveur de médiation au tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-134">légèrement</span><span class="sxs-lookup"><span data-stu-id="d5ab1-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d5ab1-135">Indicateur signalant si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-137">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d5ab1-138">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d5ab1-139">Pour Lync Server, une seule valeur est définie.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="d5ab1-140">0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-142">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d5ab1-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d5ab1-143">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-145">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d5ab1-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d5ab1-146">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-148">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-148">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-149">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-150">Pool de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-150">The pool of the caller.</span></span> <span data-ttu-id="d5ab1-151">Référencé à partir de la <a href="lync-server-2013-pool-table.md">table pool dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-153">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-153">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-154">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-155">Pool du récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-155">The pool of the call receiver.</span></span> <span data-ttu-id="d5ab1-156">Référencé à partir de la <a href="lync-server-2013-pool-table.md">table pool dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-158">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-158">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-160">URI SIP dans l’identité SIP p-asserted (PAI) du point de terminaison de réception.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="d5ab1-161">Référencé à partir de la <a href="lync-server-2013-user-table.md">table user dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-163">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-163">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-164">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-165">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-165">Caller’s URI.</span></span> <span data-ttu-id="d5ab1-166">Référencé à partir de la <a href="lync-server-2013-user-table.md">table user dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-168">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-168">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-169">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-170">Point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-170">Caller’s endpoint.</span></span> <span data-ttu-id="d5ab1-171">Référencé à partir de la <a href="lync-server-2013-endpoint-table.md">table de points de terminaison dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-173">légèrement</span><span class="sxs-lookup"><span data-stu-id="d5ab1-173">bit</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-175">Agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-175">Caller’s user agent.</span></span> <span data-ttu-id="d5ab1-176">Référencé à partir de la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-178">type</span><span class="sxs-lookup"><span data-stu-id="d5ab1-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d5ab1-179">Priorité de cet appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-181">légèrement</span><span class="sxs-lookup"><span data-stu-id="d5ab1-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d5ab1-182">Cette colonne a été déconseillée et n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d5ab1-183">Au lieu de cela, ces informations sont reportées sur des bases de lignes par support.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="d5ab1-184">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d5ab1-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-186">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-186">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-187">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-188">P-asserted-identité de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="d5ab1-189">L’identité P-asserted-Identity (PAI) est utilisée pour indiquer la véritable identité de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-191">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-191">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-192">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-193">Point de terminaison qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5ab1-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-195">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-195">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-196">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-197">Agent utilisateur employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="d5ab1-198">Les agents utilisateur représentent l’appareil de point de terminaison client.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5ab1-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="d5ab1-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d5ab1-200">int</span><span class="sxs-lookup"><span data-stu-id="d5ab1-200">int</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-201">Etranger</span><span class="sxs-lookup"><span data-stu-id="d5ab1-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d5ab1-202">URI SIP de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="d5ab1-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

