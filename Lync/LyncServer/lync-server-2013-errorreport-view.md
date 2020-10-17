---
title: 'Lync Server 2013 : vue ErrorReport'
description: 'Lync Server 2013 : vue ErrorReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572040"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="10660-103">Vue ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10660-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10660-104">_**Dernière modification de la rubrique :** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="10660-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="10660-105">La vue ErrorReport stocke les informations sur les erreurs signalées.</span><span class="sxs-lookup"><span data-stu-id="10660-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="10660-106">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-106">Each record is one error occurrence.</span></span> <span data-ttu-id="10660-107">Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.</span><span class="sxs-lookup"><span data-stu-id="10660-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="10660-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10660-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10660-109">Colonne</span><span class="sxs-lookup"><span data-stu-id="10660-109">Column</span></span></th>
<th><span data-ttu-id="10660-110">Type de données</span><span class="sxs-lookup"><span data-stu-id="10660-110">Data Type</span></span></th>
<th><span data-ttu-id="10660-111">Détails</span><span class="sxs-lookup"><span data-stu-id="10660-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10660-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="10660-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="10660-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="10660-p102">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="10660-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="10660-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-117">int</span><span class="sxs-lookup"><span data-stu-id="10660-117">int</span></span></p></td>
<td><p><span data-ttu-id="10660-p103">Numéro d’ID identifiant l’erreur. Utilisé conjointement à ErrorTime pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="10660-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="10660-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-121">int</span><span class="sxs-lookup"><span data-stu-id="10660-121">int</span></span></p></td>
<td><p><span data-ttu-id="10660-122">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="10660-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="10660-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="10660-125">URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-128">Type d’URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="10660-129">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="10660-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-132">Client de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="10660-133">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-134"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="10660-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="10660-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="10660-136">URI de l’utilisateur cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-p106">Type d’URI de l’utilisateur cible du rapport d’erreurs. Voir la table UriTypes pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="10660-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-141"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="10660-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-143">Client de l’utilisateur cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="10660-144">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="10660-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="10660-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="10660-147">URI de la conférence cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-150">Type d’URI de la conférence cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="10660-151">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="10660-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-153">DateHeure</span><span class="sxs-lookup"><span data-stu-id="10660-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="10660-154">Heure de la demande de session à l’origine du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="10660-155">Utilisé conjointement à SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="10660-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="10660-156">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="10660-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-158">int</span><span class="sxs-lookup"><span data-stu-id="10660-158">int</span></span></p></td>
<td><p><span data-ttu-id="10660-159">Numéro d’ID identifiant la demande de session à l’origine du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="10660-160">Utilisé conjointement à SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="10660-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="10660-161">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="10660-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="10660-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="10660-p111">ID de dialogue SIP de la session à l’origine de l’erreur. Le format est :</span><span class="sxs-lookup"><span data-stu-id="10660-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="10660-166">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="10660-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="10660-167">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="10660-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="10660-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="10660-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="10660-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-171">Version du client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-173">int</span><span class="sxs-lookup"><span data-stu-id="10660-173">int</span></span></p></td>
<td><p><span data-ttu-id="10660-174">Client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="10660-175">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="10660-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="10660-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="10660-178">Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="10660-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-181">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="10660-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-182"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="10660-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-184">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="10660-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="10660-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-186">int</span><span class="sxs-lookup"><span data-stu-id="10660-186">int</span></span></p></td>
<td><p><span data-ttu-id="10660-187">Code de réponse SIP à la session du message SIP contenant le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="10660-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="10660-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="10660-190">Type de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="10660-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="10660-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="10660-193">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="10660-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="10660-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10660-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="10660-196">Type de session.</span><span class="sxs-lookup"><span data-stu-id="10660-196">Type of session.</span></span> <span data-ttu-id="10660-197">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="10660-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="10660-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-199">unique</span><span class="sxs-lookup"><span data-stu-id="10660-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="10660-200">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="10660-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-201"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="10660-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-202">int</span><span class="sxs-lookup"><span data-stu-id="10660-202">int</span></span></p></td>
<td><p><span data-ttu-id="10660-203">Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="10660-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="10660-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-205">légèrement</span><span class="sxs-lookup"><span data-stu-id="10660-205">bit</span></span></p></td>
<td><p><span data-ttu-id="10660-206">Indique si le rapport d’erreurs a été capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="10660-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-207"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="10660-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-208">type</span><span class="sxs-lookup"><span data-stu-id="10660-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="10660-209">Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="10660-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="10660-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="10660-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="10660-212">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="10660-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10660-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="10660-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="10660-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="10660-215">Nom de domaine complet du serveur frontal qui a envoyé le rapport.</span><span class="sxs-lookup"><span data-stu-id="10660-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10660-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="10660-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="10660-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="10660-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="10660-218">Nom de domaine complet du pool contenant le serveur frontal qui a envoyé le rapport.</span><span class="sxs-lookup"><span data-stu-id="10660-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

