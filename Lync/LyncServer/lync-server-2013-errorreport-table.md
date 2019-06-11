---
title: 'Lync Server 2013 : Table ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="025a5-102">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="025a5-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="025a5-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="025a5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="025a5-104">La table ErrorReport stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="025a5-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="025a5-105">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-105">Each record is one error occurrence.</span></span> <span data-ttu-id="025a5-106">Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client.</span><span class="sxs-lookup"><span data-stu-id="025a5-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="025a5-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="025a5-107">Column</span></span></th>
<th><span data-ttu-id="025a5-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="025a5-108">Data Type</span></span></th>
<th><span data-ttu-id="025a5-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="025a5-109">Key/Index</span></span></th>
<th><span data-ttu-id="025a5-110">Détails</span><span class="sxs-lookup"><span data-stu-id="025a5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="025a5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="025a5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="025a5-113">Principal</span><span class="sxs-lookup"><span data-stu-id="025a5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="025a5-114">Date et heure auxquelles l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="025a5-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-116">int</span><span class="sxs-lookup"><span data-stu-id="025a5-116">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-117">Principal</span><span class="sxs-lookup"><span data-stu-id="025a5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="025a5-118">Numéro d’identification pour identifier le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-118">ID number to identify the error report.</span></span> <span data-ttu-id="025a5-119">Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier de manière unique un rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-121">int</span><span class="sxs-lookup"><span data-stu-id="025a5-121">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-122">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-123">ID unique du type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-123">Unique ID of the error type.</span></span> <span data-ttu-id="025a5-124">Pour plus d’informations, voir la <a href="lync-server-2013-errordef-table.md">table ErrorDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-126">int</span><span class="sxs-lookup"><span data-stu-id="025a5-126">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-127">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-128">Utilisateur à l’origine de la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="025a5-129">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-131">int</span><span class="sxs-lookup"><span data-stu-id="025a5-131">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-132">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-133">Utilisateur de destination pour la requête à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="025a5-134">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-136">int</span><span class="sxs-lookup"><span data-stu-id="025a5-136">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-137">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-138">URI de la conférence liée à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-138">Conference URI related to the error.</span></span> <span data-ttu-id="025a5-139">Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="025a5-140">En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId seront NULL.</span><span class="sxs-lookup"><span data-stu-id="025a5-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-142">DateHeure</span><span class="sxs-lookup"><span data-stu-id="025a5-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="025a5-143">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-144">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="025a5-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="025a5-145">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-147">int</span><span class="sxs-lookup"><span data-stu-id="025a5-147">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-148">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-149">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="025a5-149">ID number to identify the session.</span></span> <span data-ttu-id="025a5-150">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="025a5-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="025a5-151">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-153">int</span><span class="sxs-lookup"><span data-stu-id="025a5-153">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-154">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-155">Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="025a5-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="025a5-156">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="025a5-157">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a5-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-159">int</span><span class="sxs-lookup"><span data-stu-id="025a5-159">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-160">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-161">Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="025a5-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="025a5-162">Pour plus d’informations, consultez le <a href="lync-server-2013-application-table.md">tableau de l’application dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="025a5-163">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a5-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-165">image</span><span class="sxs-lookup"><span data-stu-id="025a5-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="025a5-166">Plus d’informations sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-166">More information about the error.</span></span></p>
<p><span data-ttu-id="025a5-167">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="025a5-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-169">int</span><span class="sxs-lookup"><span data-stu-id="025a5-169">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-170">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-171">Version du client de point de terminaison qui envoie le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="025a5-172">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="025a5-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-174">bit</span><span class="sxs-lookup"><span data-stu-id="025a5-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="025a5-175">Est le rapport d’erreur capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="025a5-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-176"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-177">type</span><span class="sxs-lookup"><span data-stu-id="025a5-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="025a5-178">Réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="025a5-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-180">Identificateur</span><span class="sxs-lookup"><span data-stu-id="025a5-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="025a5-181">Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</span><span class="sxs-lookup"><span data-stu-id="025a5-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="025a5-182">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a5-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-184">int</span><span class="sxs-lookup"><span data-stu-id="025a5-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="025a5-185">Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="025a5-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="025a5-186">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a5-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="025a5-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-188">int</span><span class="sxs-lookup"><span data-stu-id="025a5-188">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-189">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-190">Représente le nom de domaine complet du serveur qui a généré le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="025a5-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="025a5-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="025a5-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="025a5-192">int</span><span class="sxs-lookup"><span data-stu-id="025a5-192">int</span></span></p></td>
<td><p><span data-ttu-id="025a5-193">Externes</span><span class="sxs-lookup"><span data-stu-id="025a5-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="025a5-194">Représente le nom de domaine complet du pool dans lequel le rapport d’erreur a été généré.</span><span class="sxs-lookup"><span data-stu-id="025a5-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

