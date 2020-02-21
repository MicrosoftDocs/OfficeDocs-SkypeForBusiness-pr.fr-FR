---
title: 'Lync Server 2013 : table de sessions'
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
ms.openlocfilehash: f927957f21c67a8cfca6b169b99f7de9275740fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="e0365-102">Table session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0365-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0365-103">_**Dernière modification de la rubrique :** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="e0365-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="e0365-104">Chaque enregistrement représente une session qui implique l’audio, l’audio et la vidéo.</span><span class="sxs-lookup"><span data-stu-id="e0365-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="e0365-105">Il contient des informations générales sur la session.</span><span class="sxs-lookup"><span data-stu-id="e0365-105">It contains overall information about the session.</span></span> <span data-ttu-id="e0365-106">Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e0365-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0365-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e0365-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e0365-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e0365-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0365-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e0365-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0365-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="e0365-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e0365-114">Référencé à partir de la <a href="lync-server-2013-dialog-table.md">table Dialog dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-116">int</span><span class="sxs-lookup"><span data-stu-id="e0365-116">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="e0365-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e0365-118">Référencé à partir de la <a href="lync-server-2013-dialog-table.md">table Dialog dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-120">int</span><span class="sxs-lookup"><span data-stu-id="e0365-120">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-122">Clé de conférence.</span><span class="sxs-lookup"><span data-stu-id="e0365-122">Conference key.</span></span> <span data-ttu-id="e0365-123">Référencé à partir de la <a href="lync-server-2013-conference-table.md">table Conference dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-125">int</span><span class="sxs-lookup"><span data-stu-id="e0365-125">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-126">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-127">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="e0365-127">Correlation key.</span></span> <span data-ttu-id="e0365-128">Référencé à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table table sessioncorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-130">légèrement</span><span class="sxs-lookup"><span data-stu-id="e0365-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0365-131">Catégorie de boîte de dialogue ; 0 est le tronçon Lync Server vers serveur de médiation ; 1 est le serveur de médiation au tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="e0365-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-133">légèrement</span><span class="sxs-lookup"><span data-stu-id="e0365-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0365-134">Indicateur signalant si l’appel a été contourné ou non.</span><span class="sxs-lookup"><span data-stu-id="e0365-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-136">int</span><span class="sxs-lookup"><span data-stu-id="e0365-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0365-137">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient.</span><span class="sxs-lookup"><span data-stu-id="e0365-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e0365-138">Pour Lync Server, une seule valeur est définie.</span><span class="sxs-lookup"><span data-stu-id="e0365-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="e0365-139">0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="e0365-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-141">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e0365-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0365-142">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-144">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e0365-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0365-145">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-147">int</span><span class="sxs-lookup"><span data-stu-id="e0365-147">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-148">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-149">Pool de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e0365-149">The pool of the caller.</span></span> <span data-ttu-id="e0365-150">Référencé à partir de la <a href="lync-server-2013-pool-table.md">table pool dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-152">int</span><span class="sxs-lookup"><span data-stu-id="e0365-152">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-153">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-154">Pool du récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="e0365-154">The pool of the call receiver.</span></span> <span data-ttu-id="e0365-155">Référencé à partir de la <a href="lync-server-2013-pool-table.md">table pool dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-157">int</span><span class="sxs-lookup"><span data-stu-id="e0365-157">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-158">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-159">URI SIP dans l’identité SIP p-asserted (PAI) du point de terminaison de réception.</span><span class="sxs-lookup"><span data-stu-id="e0365-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="e0365-160">Référencé à partir de la <a href="lync-server-2013-user-table.md">table user dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-162">int</span><span class="sxs-lookup"><span data-stu-id="e0365-162">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-163">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-164">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e0365-164">Caller’s URI.</span></span> <span data-ttu-id="e0365-165">Référencé à partir de la <a href="lync-server-2013-user-table.md">table user dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-167">int</span><span class="sxs-lookup"><span data-stu-id="e0365-167">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-168">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-169">Point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e0365-169">Caller’s endpoint.</span></span> <span data-ttu-id="e0365-170">Référencé à partir de la <a href="lync-server-2013-endpoint-table.md">table de points de terminaison dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-172">légèrement</span><span class="sxs-lookup"><span data-stu-id="e0365-172">bit</span></span></p></td>
<td><p><span data-ttu-id="e0365-173">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-174">Agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e0365-174">Caller’s user agent.</span></span> <span data-ttu-id="e0365-175">Référencé à partir de la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0365-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-177">type</span><span class="sxs-lookup"><span data-stu-id="e0365-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0365-178">Priorité de cet appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-180">légèrement</span><span class="sxs-lookup"><span data-stu-id="e0365-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0365-181">Cette colonne a été déconseillée et n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0365-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e0365-182">Au lieu de cela, ces informations sont reportées sur des bases de lignes par support.</span><span class="sxs-lookup"><span data-stu-id="e0365-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="e0365-183">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0365-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-185">int</span><span class="sxs-lookup"><span data-stu-id="e0365-185">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-186">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-187">P-asserted-identité de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="e0365-188">L’identité P-asserted-Identity (PAI) est utilisée pour indiquer la véritable identité de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-190">int</span><span class="sxs-lookup"><span data-stu-id="e0365-190">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-191">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-192">Point de terminaison qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0365-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-194">int</span><span class="sxs-lookup"><span data-stu-id="e0365-194">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-195">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-196">Agent utilisateur employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="e0365-197">Les agents utilisateur représentent l’appareil de point de terminaison client.</span><span class="sxs-lookup"><span data-stu-id="e0365-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0365-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="e0365-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e0365-199">int</span><span class="sxs-lookup"><span data-stu-id="e0365-199">int</span></span></p></td>
<td><p><span data-ttu-id="e0365-200">Etranger</span><span class="sxs-lookup"><span data-stu-id="e0365-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0365-201">URI SIP de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="e0365-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

