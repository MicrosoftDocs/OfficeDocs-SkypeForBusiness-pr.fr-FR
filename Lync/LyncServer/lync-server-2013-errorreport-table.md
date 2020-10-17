---
title: 'Lync Server 2013 : table ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 321a975e9461e39de882d9620cdded9d2554e8ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533137"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="86c9a-102">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86c9a-102">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86c9a-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="86c9a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="86c9a-104">La table ErrorReport stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="86c9a-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="86c9a-105">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-105">Each record is one error occurrence.</span></span> <span data-ttu-id="86c9a-106">Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.</span><span class="sxs-lookup"><span data-stu-id="86c9a-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86c9a-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="86c9a-107">Column</span></span></th>
<th><span data-ttu-id="86c9a-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="86c9a-108">Data Type</span></span></th>
<th><span data-ttu-id="86c9a-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="86c9a-109">Key/Index</span></span></th>
<th><span data-ttu-id="86c9a-110">Détails</span><span class="sxs-lookup"><span data-stu-id="86c9a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="86c9a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="86c9a-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="86c9a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="86c9a-114">Date et heure de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-116">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-116">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="86c9a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="86c9a-118">Numéro d’identification permettant d’identifier le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="86c9a-118">ID number to identify the error report.</span></span> <span data-ttu-id="86c9a-119">Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier un rapport d’erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="86c9a-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-121">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-121">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-123">ID unique du type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-123">Unique ID of the error type.</span></span> <span data-ttu-id="86c9a-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errordef-table.md">table table errordef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-126">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-126">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-128">Utilisateur à l’origine de la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="86c9a-129">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-131">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-131">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-132">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-133">Utilisateur de destination pour la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="86c9a-134">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-136">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-136">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-137">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-138">URI de conférence lié à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-138">Conference URI related to the error.</span></span> <span data-ttu-id="86c9a-139">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="86c9a-140">En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId sera null.</span><span class="sxs-lookup"><span data-stu-id="86c9a-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-142">DateHeure</span><span class="sxs-lookup"><span data-stu-id="86c9a-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="86c9a-143">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-144">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="86c9a-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="86c9a-145">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-147">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-147">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-148">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-149">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="86c9a-149">ID number to identify the session.</span></span> <span data-ttu-id="86c9a-150">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="86c9a-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="86c9a-151">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-153">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-153">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-154">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-155">Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="86c9a-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="86c9a-156">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="86c9a-157">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86c9a-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-159">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-159">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-160">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-161">Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="86c9a-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="86c9a-162">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-application-table.md">table application dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="86c9a-163">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86c9a-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-165">image</span><span class="sxs-lookup"><span data-stu-id="86c9a-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86c9a-166">Plus d’informations sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-166">More information about the error.</span></span></p>
<p><span data-ttu-id="86c9a-167">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="86c9a-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-169">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-169">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-170">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-171">Version client du point de terminaison qui envoie le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="86c9a-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="86c9a-172">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86c9a-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-174">légèrement</span><span class="sxs-lookup"><span data-stu-id="86c9a-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86c9a-175">Est le rapport d’erreurs capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="86c9a-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-176"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-177">type</span><span class="sxs-lookup"><span data-stu-id="86c9a-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86c9a-178">Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="86c9a-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-180">Unique</span><span class="sxs-lookup"><span data-stu-id="86c9a-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86c9a-181">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="86c9a-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="86c9a-182">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86c9a-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-184">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86c9a-185">Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="86c9a-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="86c9a-186">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86c9a-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c9a-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-188">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-188">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-189">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-190">Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="86c9a-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c9a-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="86c9a-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="86c9a-192">int</span><span class="sxs-lookup"><span data-stu-id="86c9a-192">int</span></span></p></td>
<td><p><span data-ttu-id="86c9a-193">Etranger</span><span class="sxs-lookup"><span data-stu-id="86c9a-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86c9a-194">Représente le nom de domaine complet du pool où le rapport d’erreurs a été généré.</span><span class="sxs-lookup"><span data-stu-id="86c9a-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

