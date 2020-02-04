---
title: 'Affichage Lync Server 2013 : ErrorReport'
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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="51e5a-102">Affichage ErrorReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e5a-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e5a-103">_**Dernière modification de la rubrique :** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="51e5a-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="51e5a-104">Le mode ErrorReport stocke les informations sur les erreurs signalées.</span><span class="sxs-lookup"><span data-stu-id="51e5a-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="51e5a-105">Chaque enregistrement correspond à une occurrence d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-105">Each record is one error occurrence.</span></span> <span data-ttu-id="51e5a-106">Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client.</span><span class="sxs-lookup"><span data-stu-id="51e5a-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="51e5a-107">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51e5a-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51e5a-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="51e5a-108">Column</span></span></th>
<th><span data-ttu-id="51e5a-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="51e5a-109">Data Type</span></span></th>
<th><span data-ttu-id="51e5a-110">Détails</span><span class="sxs-lookup"><span data-stu-id="51e5a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="51e5a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="51e5a-113">L’heure de l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="51e5a-113">Time of error occurred.</span></span> <span data-ttu-id="51e5a-114">Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-116">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-116">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-117">Numéro d’identification pour identifier l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-117">ID number to identify the error.</span></span> <span data-ttu-id="51e5a-118">Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-120">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-120">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-121">ID de diagnostic du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51e5a-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-124">URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-127">Type d’URI de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="51e5a-128">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-131">Client de l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="51e5a-132">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-133"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51e5a-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-135">URI de l’utilisateur qui a été la cible du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-138">Type d’URI de l’utilisateur qui a ciblé le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="51e5a-139">Pour plus d’informations, voir la table UriTypes.</span><span class="sxs-lookup"><span data-stu-id="51e5a-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-142">Client de l’utilisateur qui cible le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="51e5a-143">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51e5a-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-146">URI de la Conférence qui était la cible du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-149">Type d’URI de la Conférence qui était la cible du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="51e5a-150">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-152">DateHeure</span><span class="sxs-lookup"><span data-stu-id="51e5a-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="51e5a-153">Durée de la demande de session à l’origine du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="51e5a-154">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="51e5a-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="51e5a-155">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-157">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-157">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-158">Numéro d’identification identifiant la demande de session à l’origine du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="51e5a-159">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="51e5a-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="51e5a-160">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-162">varstring (LGA775)</span><span class="sxs-lookup"><span data-stu-id="51e5a-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-163">ID de boîte de dialogue SIP de session à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="51e5a-164">Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="51e5a-164">The format is:</span></span></p>
<p><span data-ttu-id="51e5a-165">boîte de dialogue ; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="51e5a-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="51e5a-166">Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="51e5a-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="51e5a-167">Cast (Cast (ExternalId) en tant que varchar (max))</span><span class="sxs-lookup"><span data-stu-id="51e5a-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-170">Version du client utilisée par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-171"><strong>TypeClient</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-172">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-172">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-173">Client utilisé par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="51e5a-174">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="51e5a-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-177">Nom de la catégorie du client utilisée par l’utilisateur à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-180">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="51e5a-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-183">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="51e5a-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-185">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-185">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-186">Code de réponse SIP à la session du message SIP contenant le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="51e5a-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-189">Type de requête ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="51e5a-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-190"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="51e5a-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-192">Type de contenu de la requête qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="51e5a-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e5a-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-195">Type de session.</span><span class="sxs-lookup"><span data-stu-id="51e5a-195">Type of session.</span></span> <span data-ttu-id="51e5a-196">Pour plus d’informations, voir la <a href="lync-server-2013-calltype-table.md">table CallType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51e5a-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-198">identificateur</span><span class="sxs-lookup"><span data-stu-id="51e5a-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="51e5a-199">Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</span><span class="sxs-lookup"><span data-stu-id="51e5a-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-201">int</span><span class="sxs-lookup"><span data-stu-id="51e5a-201">int</span></span></p></td>
<td><p><span data-ttu-id="51e5a-202">Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="51e5a-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-204">bit</span><span class="sxs-lookup"><span data-stu-id="51e5a-204">bit</span></span></p></td>
<td><p><span data-ttu-id="51e5a-205">Indique si le rapport d’erreur a été capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.</span><span class="sxs-lookup"><span data-stu-id="51e5a-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-206"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-207">type</span><span class="sxs-lookup"><span data-stu-id="51e5a-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="51e5a-208">Réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="51e5a-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="51e5a-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e5a-211">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51e5a-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e5a-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="51e5a-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="51e5a-214">Nom de domaine complet du serveur frontal qui a soumis le rapport.</span><span class="sxs-lookup"><span data-stu-id="51e5a-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e5a-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="51e5a-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="51e5a-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="51e5a-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="51e5a-217">Nom de domaine complet du pool contenant le serveur frontal qui a soumis le rapport.</span><span class="sxs-lookup"><span data-stu-id="51e5a-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

