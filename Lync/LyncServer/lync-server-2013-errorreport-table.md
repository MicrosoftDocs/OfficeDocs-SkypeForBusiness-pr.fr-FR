---
title: 'Lync Server 2013 : Table ErrorReport'
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
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="afda9-102">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afda9-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afda9-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="afda9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="afda9-104">La table ErrorReport stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="afda9-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="afda9-105">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-105">Each record is one error occurrence.</span></span> <span data-ttu-id="afda9-106">Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client.</span><span class="sxs-lookup"><span data-stu-id="afda9-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afda9-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="afda9-107">Column</span></span></th>
<th><span data-ttu-id="afda9-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="afda9-108">Data Type</span></span></th>
<th><span data-ttu-id="afda9-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="afda9-109">Key/Index</span></span></th>
<th><span data-ttu-id="afda9-110">Détails</span><span class="sxs-lookup"><span data-stu-id="afda9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afda9-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="afda9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="afda9-113">Principal</span><span class="sxs-lookup"><span data-stu-id="afda9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="afda9-114">Date et heure auxquelles l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="afda9-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-116">int</span><span class="sxs-lookup"><span data-stu-id="afda9-116">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-117">Principal</span><span class="sxs-lookup"><span data-stu-id="afda9-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="afda9-118">Numéro d’identification pour identifier le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-118">ID number to identify the error report.</span></span> <span data-ttu-id="afda9-119">Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier de manière unique un rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-121">int</span><span class="sxs-lookup"><span data-stu-id="afda9-121">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-122">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-123">ID unique du type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-123">Unique ID of the error type.</span></span> <span data-ttu-id="afda9-124">Pour plus d’informations, voir la <a href="lync-server-2013-errordef-table.md">table ErrorDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-126">int</span><span class="sxs-lookup"><span data-stu-id="afda9-126">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-127">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-128">Utilisateur à l’origine de la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="afda9-129">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-131">int</span><span class="sxs-lookup"><span data-stu-id="afda9-131">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-132">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-133">Utilisateur de destination pour la requête à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="afda9-134">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-136">int</span><span class="sxs-lookup"><span data-stu-id="afda9-136">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-137">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-138">URI de la conférence liée à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-138">Conference URI related to the error.</span></span> <span data-ttu-id="afda9-139">Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="afda9-140">En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId seront NULL.</span><span class="sxs-lookup"><span data-stu-id="afda9-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-142">DateHeure</span><span class="sxs-lookup"><span data-stu-id="afda9-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="afda9-143">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-144">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="afda9-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="afda9-145">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-147">int</span><span class="sxs-lookup"><span data-stu-id="afda9-147">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-148">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-149">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="afda9-149">ID number to identify the session.</span></span> <span data-ttu-id="afda9-150">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="afda9-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="afda9-151">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-153">int</span><span class="sxs-lookup"><span data-stu-id="afda9-153">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-154">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-155">Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="afda9-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="afda9-156">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="afda9-157">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afda9-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-159">int</span><span class="sxs-lookup"><span data-stu-id="afda9-159">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-160">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-161">Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="afda9-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="afda9-162">Pour plus d’informations, consultez le <a href="lync-server-2013-application-table.md">tableau de l’application dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="afda9-163">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afda9-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-165">image</span><span class="sxs-lookup"><span data-stu-id="afda9-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afda9-166">Plus d’informations sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-166">More information about the error.</span></span></p>
<p><span data-ttu-id="afda9-167">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="afda9-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-169">int</span><span class="sxs-lookup"><span data-stu-id="afda9-169">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-170">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-171">Version du client de point de terminaison qui envoie le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="afda9-172">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="afda9-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-174">bit</span><span class="sxs-lookup"><span data-stu-id="afda9-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afda9-175">Est le rapport d’erreur capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="afda9-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-176"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-177">type</span><span class="sxs-lookup"><span data-stu-id="afda9-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afda9-178">Réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="afda9-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-180">Identificateur</span><span class="sxs-lookup"><span data-stu-id="afda9-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afda9-181">Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</span><span class="sxs-lookup"><span data-stu-id="afda9-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="afda9-182">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afda9-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-184">int</span><span class="sxs-lookup"><span data-stu-id="afda9-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afda9-185">Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="afda9-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="afda9-186">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afda9-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afda9-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-188">int</span><span class="sxs-lookup"><span data-stu-id="afda9-188">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-189">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-190">Représente le nom de domaine complet du serveur qui a généré le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="afda9-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afda9-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="afda9-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="afda9-192">int</span><span class="sxs-lookup"><span data-stu-id="afda9-192">int</span></span></p></td>
<td><p><span data-ttu-id="afda9-193">Externes</span><span class="sxs-lookup"><span data-stu-id="afda9-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afda9-194">Représente le nom de domaine complet du pool dans lequel le rapport d’erreur a été généré.</span><span class="sxs-lookup"><span data-stu-id="afda9-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

