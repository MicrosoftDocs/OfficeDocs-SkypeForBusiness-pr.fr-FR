---
title: 'Lync Server 2013 : table ErrorReport'
description: 'Lync Server 2013 : table ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572010"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="21805-103">Table ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21805-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21805-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="21805-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="21805-105">La table ErrorReport stocke des informations sur les erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="21805-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="21805-106">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-106">Each record is one error occurrence.</span></span> <span data-ttu-id="21805-107">Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.</span><span class="sxs-lookup"><span data-stu-id="21805-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21805-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="21805-108">Column</span></span></th>
<th><span data-ttu-id="21805-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="21805-109">Data Type</span></span></th>
<th><span data-ttu-id="21805-110">Clé/index</span><span class="sxs-lookup"><span data-stu-id="21805-110">Key/Index</span></span></th>
<th><span data-ttu-id="21805-111">Détails</span><span class="sxs-lookup"><span data-stu-id="21805-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21805-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="21805-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="21805-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="21805-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="21805-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="21805-115">Date et heure de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21805-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-117">int</span><span class="sxs-lookup"><span data-stu-id="21805-117">int</span></span></p></td>
<td><p><span data-ttu-id="21805-118">Primaire</span><span class="sxs-lookup"><span data-stu-id="21805-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="21805-119">Numéro d’identification permettant d’identifier le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="21805-119">ID number to identify the error report.</span></span> <span data-ttu-id="21805-120">Utilisé conjointement avec <strong>ErrorTime</strong> pour identifier un rapport d’erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="21805-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-122">int</span><span class="sxs-lookup"><span data-stu-id="21805-122">int</span></span></p></td>
<td><p><span data-ttu-id="21805-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-124">ID unique du type d’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-124">Unique ID of the error type.</span></span> <span data-ttu-id="21805-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errordef-table.md">table table errordef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-127">int</span><span class="sxs-lookup"><span data-stu-id="21805-127">int</span></span></p></td>
<td><p><span data-ttu-id="21805-128">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-129">Utilisateur à l’origine de la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="21805-130">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-132">int</span><span class="sxs-lookup"><span data-stu-id="21805-132">int</span></span></p></td>
<td><p><span data-ttu-id="21805-133">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-134">Utilisateur de destination pour la demande à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="21805-135">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-137">int</span><span class="sxs-lookup"><span data-stu-id="21805-137">int</span></span></p></td>
<td><p><span data-ttu-id="21805-138">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-139">URI de conférence lié à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-139">Conference URI related to the error.</span></span> <span data-ttu-id="21805-140">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="21805-141">En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId sera null.</span><span class="sxs-lookup"><span data-stu-id="21805-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="21805-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-143">DateHeure</span><span class="sxs-lookup"><span data-stu-id="21805-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="21805-144">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-145">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="21805-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="21805-146">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21805-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-148">int</span><span class="sxs-lookup"><span data-stu-id="21805-148">int</span></span></p></td>
<td><p><span data-ttu-id="21805-149">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-150">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="21805-150">ID number to identify the session.</span></span> <span data-ttu-id="21805-151">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="21805-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="21805-152">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-154">int</span><span class="sxs-lookup"><span data-stu-id="21805-154">int</span></span></p></td>
<td><p><span data-ttu-id="21805-155">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-156">Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="21805-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="21805-157">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="21805-158">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21805-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-160">int</span><span class="sxs-lookup"><span data-stu-id="21805-160">int</span></span></p></td>
<td><p><span data-ttu-id="21805-161">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-162">Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="21805-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="21805-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-application-table.md">table application dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="21805-164">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21805-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="21805-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-166">image</span><span class="sxs-lookup"><span data-stu-id="21805-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21805-167">Plus d’informations sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="21805-167">More information about the error.</span></span></p>
<p><span data-ttu-id="21805-168">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="21805-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-170">int</span><span class="sxs-lookup"><span data-stu-id="21805-170">int</span></span></p></td>
<td><p><span data-ttu-id="21805-171">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-172">Version client du point de terminaison qui envoie le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="21805-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="21805-173">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="21805-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="21805-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-175">légèrement</span><span class="sxs-lookup"><span data-stu-id="21805-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21805-176">Est le rapport d’erreurs capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="21805-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-177"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="21805-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-178">type</span><span class="sxs-lookup"><span data-stu-id="21805-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21805-179">Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="21805-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-181">Unique</span><span class="sxs-lookup"><span data-stu-id="21805-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21805-182">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="21805-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="21805-183">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21805-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="21805-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-185">int</span><span class="sxs-lookup"><span data-stu-id="21805-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="21805-186">Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="21805-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="21805-187">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21805-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21805-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-189">int</span><span class="sxs-lookup"><span data-stu-id="21805-189">int</span></span></p></td>
<td><p><span data-ttu-id="21805-190">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-191">Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="21805-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21805-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="21805-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="21805-193">int</span><span class="sxs-lookup"><span data-stu-id="21805-193">int</span></span></p></td>
<td><p><span data-ttu-id="21805-194">Etranger</span><span class="sxs-lookup"><span data-stu-id="21805-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21805-195">Représente le nom de domaine complet du pool où le rapport d’erreurs a été généré.</span><span class="sxs-lookup"><span data-stu-id="21805-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

