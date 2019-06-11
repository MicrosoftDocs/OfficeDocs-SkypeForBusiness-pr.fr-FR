---
title: 'Lync Server 2013 : Table Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="719a9-102">Table Session dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719a9-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719a9-103">_**Dernière modification de la rubrique:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="719a9-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="719a9-104">Chaque enregistrement représente une session qui implique du son, de l’audio et de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="719a9-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="719a9-105">Il contient des informations générales sur la session.</span><span class="sxs-lookup"><span data-stu-id="719a9-105">It contains overall information about the session.</span></span> <span data-ttu-id="719a9-106">Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="719a9-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="719a9-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="719a9-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="719a9-109"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="719a9-110"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="719a9-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="719a9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="719a9-113">Principal</span><span class="sxs-lookup"><span data-stu-id="719a9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="719a9-114">Fait référence à partir de la <a href="lync-server-2013-dialog-table.md">table boîte de dialogue dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-116">int</span><span class="sxs-lookup"><span data-stu-id="719a9-116">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-117">Principal</span><span class="sxs-lookup"><span data-stu-id="719a9-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="719a9-118">Fait référence à partir de la <a href="lync-server-2013-dialog-table.md">table boîte de dialogue dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-120">int</span><span class="sxs-lookup"><span data-stu-id="719a9-120">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-121">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-122">Clé de conférence.</span><span class="sxs-lookup"><span data-stu-id="719a9-122">Conference key.</span></span> <span data-ttu-id="719a9-123">Référence à partir de la <a href="lync-server-2013-conference-table.md">table Conference dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-125">int</span><span class="sxs-lookup"><span data-stu-id="719a9-125">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-126">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-127">Clé de corrélation.</span><span class="sxs-lookup"><span data-stu-id="719a9-127">Correlation key.</span></span> <span data-ttu-id="719a9-128">Fait référence à partir de la <a href="lync-server-2013-sessioncorrelation-table.md">table SessionCorrelation dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-130">bit</span><span class="sxs-lookup"><span data-stu-id="719a9-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="719a9-131">Catégorie de boîte de dialogue. 0 est Lync Server to Mediation Server leg; 1 est un serveur de médiation en tronçon de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="719a9-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-133">bit</span><span class="sxs-lookup"><span data-stu-id="719a9-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="719a9-134">Indicateur indiquant si l’appel a été ignoré ou non.</span><span class="sxs-lookup"><span data-stu-id="719a9-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-136">int</span><span class="sxs-lookup"><span data-stu-id="719a9-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="719a9-137">Ce champ, s’il est présent, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent.</span><span class="sxs-lookup"><span data-stu-id="719a9-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="719a9-138">Pour Lync Server, une seule valeur est définie.</span><span class="sxs-lookup"><span data-stu-id="719a9-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="719a9-139">0x0001-ID de contournement inconnu pour la carte réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="719a9-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-141">DateHeure</span><span class="sxs-lookup"><span data-stu-id="719a9-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="719a9-142">Heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-144">DateHeure</span><span class="sxs-lookup"><span data-stu-id="719a9-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="719a9-145">Heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-147">int</span><span class="sxs-lookup"><span data-stu-id="719a9-147">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-148">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-149">Le pool de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="719a9-149">The pool of the caller.</span></span> <span data-ttu-id="719a9-150">Fait référence à partir de la <a href="lync-server-2013-pool-table.md">table de réserve dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-152">int</span><span class="sxs-lookup"><span data-stu-id="719a9-152">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-153">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-154">Le regroupement du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-154">The pool of the call receiver.</span></span> <span data-ttu-id="719a9-155">Fait référence à partir de la <a href="lync-server-2013-pool-table.md">table de réserve dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-157">int</span><span class="sxs-lookup"><span data-stu-id="719a9-157">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-158">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-159">URI SIP dans l’identité SIP p-assertion (PAI) du point de terminaison de réception.</span><span class="sxs-lookup"><span data-stu-id="719a9-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="719a9-160">Référence à partir de la <a href="lync-server-2013-user-table.md">table utilisateur dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-162">int</span><span class="sxs-lookup"><span data-stu-id="719a9-162">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-163">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-164">URI de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="719a9-164">Caller’s URI.</span></span> <span data-ttu-id="719a9-165">Référence à partir de la <a href="lync-server-2013-user-table.md">table utilisateur dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-167">int</span><span class="sxs-lookup"><span data-stu-id="719a9-167">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-168">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-169">Point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="719a9-169">Caller’s endpoint.</span></span> <span data-ttu-id="719a9-170">Référence à partir de la <a href="lync-server-2013-endpoint-table.md">table de points de terminaison dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-172">bit</span><span class="sxs-lookup"><span data-stu-id="719a9-172">bit</span></span></p></td>
<td><p><span data-ttu-id="719a9-173">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-174">Agent utilisateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="719a9-174">Caller’s user agent.</span></span> <span data-ttu-id="719a9-175">Référence à partir de la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="719a9-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-177">type</span><span class="sxs-lookup"><span data-stu-id="719a9-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="719a9-178">Priorité de cet appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-180">bit</span><span class="sxs-lookup"><span data-stu-id="719a9-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="719a9-181">Cette colonne a été déconseillée et n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="719a9-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="719a9-182">À la place, ces informations sont communiquées sur une base de lignes par média.</span><span class="sxs-lookup"><span data-stu-id="719a9-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="719a9-183">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="719a9-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-185">int</span><span class="sxs-lookup"><span data-stu-id="719a9-185">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-186">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-187">P-assertion-identité de l’utilisateur qui a placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="719a9-188">Le P-assertion-Identity (PAI) est utilisé pour transmettre la véritable identité de l’utilisateur qui a placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-190">int</span><span class="sxs-lookup"><span data-stu-id="719a9-190">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-191">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-192">Point de terminaison ayant reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719a9-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-194">int</span><span class="sxs-lookup"><span data-stu-id="719a9-194">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-195">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-196">Agent utilisateur utilisé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="719a9-197">Les agents utilisateurs représentent l’appareil de point de terminaison client.</span><span class="sxs-lookup"><span data-stu-id="719a9-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719a9-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="719a9-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="719a9-199">int</span><span class="sxs-lookup"><span data-stu-id="719a9-199">int</span></span></p></td>
<td><p><span data-ttu-id="719a9-200">Externes</span><span class="sxs-lookup"><span data-stu-id="719a9-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="719a9-201">URI SIP de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="719a9-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

