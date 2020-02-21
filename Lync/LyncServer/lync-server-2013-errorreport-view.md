---
title: 'Lync Server 2013 : vue ErrorReport'
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
ms.openlocfilehash: e635cd289f0224a7f8d4106cecc3d8b047e9bb92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="63706-102">Vue ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63706-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63706-103">_**Dernière modification de la rubrique :** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="63706-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="63706-104">La vue ErrorReport stocke les informations sur les erreurs signalées.</span><span class="sxs-lookup"><span data-stu-id="63706-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="63706-105">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-105">Each record is one error occurrence.</span></span> <span data-ttu-id="63706-106">Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.</span><span class="sxs-lookup"><span data-stu-id="63706-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="63706-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63706-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63706-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="63706-108">Column</span></span></th>
<th><span data-ttu-id="63706-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="63706-109">Data Type</span></span></th>
<th><span data-ttu-id="63706-110">Détails</span><span class="sxs-lookup"><span data-stu-id="63706-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63706-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="63706-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="63706-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="63706-p102">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="63706-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63706-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-116">int</span><span class="sxs-lookup"><span data-stu-id="63706-116">int</span></span></p></td>
<td><p><span data-ttu-id="63706-p103">Numéro d’ID identifiant l’erreur. Utilisé conjointement à ErrorTime pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="63706-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="63706-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-120">int</span><span class="sxs-lookup"><span data-stu-id="63706-120">int</span></span></p></td>
<td><p><span data-ttu-id="63706-121">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="63706-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63706-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63706-124">URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-127">Type d’URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="63706-128">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63706-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-131">Client de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="63706-132">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-133"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="63706-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63706-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63706-135">URI de l’utilisateur cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-p106">Type d’URI de l’utilisateur cible du rapport d’erreurs. Voir la table UriTypes pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="63706-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63706-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-142">Client de l’utilisateur cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="63706-143">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="63706-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="63706-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63706-146">URI de la conférence cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-149">Type d’URI de la conférence cible du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="63706-150">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="63706-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-152">DateHeure</span><span class="sxs-lookup"><span data-stu-id="63706-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="63706-153">Heure de la demande de session à l’origine du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="63706-154">Utilisé conjointement à SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="63706-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="63706-155">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63706-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-157">int</span><span class="sxs-lookup"><span data-stu-id="63706-157">int</span></span></p></td>
<td><p><span data-ttu-id="63706-158">Numéro d’ID identifiant la demande de session à l’origine du rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="63706-159">Utilisé conjointement à SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="63706-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="63706-160">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="63706-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="63706-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="63706-p111">ID de dialogue SIP de la session à l’origine de l’erreur. Le format est :</span><span class="sxs-lookup"><span data-stu-id="63706-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="63706-165">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="63706-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="63706-166">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="63706-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="63706-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="63706-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="63706-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-170">Version du client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-172">int</span><span class="sxs-lookup"><span data-stu-id="63706-172">int</span></span></p></td>
<td><p><span data-ttu-id="63706-173">Client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="63706-174">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="63706-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="63706-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="63706-177">Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="63706-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-180">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="63706-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="63706-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-183">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="63706-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="63706-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-185">int</span><span class="sxs-lookup"><span data-stu-id="63706-185">int</span></span></p></td>
<td><p><span data-ttu-id="63706-186">Code de réponse SIP à la session du message SIP contenant le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="63706-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="63706-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63706-189">Type de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="63706-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="63706-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63706-192">Type de contenu de la demande ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="63706-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="63706-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="63706-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63706-195">Type de session.</span><span class="sxs-lookup"><span data-stu-id="63706-195">Type of session.</span></span> <span data-ttu-id="63706-196">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="63706-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="63706-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-198">unique</span><span class="sxs-lookup"><span data-stu-id="63706-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="63706-199">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="63706-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="63706-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-201">int</span><span class="sxs-lookup"><span data-stu-id="63706-201">int</span></span></p></td>
<td><p><span data-ttu-id="63706-202">Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="63706-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="63706-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-204">légèrement</span><span class="sxs-lookup"><span data-stu-id="63706-204">bit</span></span></p></td>
<td><p><span data-ttu-id="63706-205">Indique si le rapport d’erreurs a été capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="63706-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-206"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="63706-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-207">type</span><span class="sxs-lookup"><span data-stu-id="63706-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="63706-208">Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="63706-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="63706-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="63706-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63706-211">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="63706-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63706-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="63706-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="63706-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="63706-214">Nom de domaine complet du serveur frontal qui a envoyé le rapport.</span><span class="sxs-lookup"><span data-stu-id="63706-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63706-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="63706-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="63706-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="63706-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="63706-217">Nom de domaine complet du pool contenant le serveur frontal qui a envoyé le rapport.</span><span class="sxs-lookup"><span data-stu-id="63706-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

