---
title: 'Affichage Lync Server 2013 : SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="dae44-102">Affichage SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dae44-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dae44-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dae44-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dae44-104">La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou un autre type de session.</span><span class="sxs-lookup"><span data-stu-id="dae44-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="dae44-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dae44-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dae44-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="dae44-106">Column</span></span></th>
<th><span data-ttu-id="dae44-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="dae44-107">Data Type</span></span></th>
<th><span data-ttu-id="dae44-108">Détails</span><span class="sxs-lookup"><span data-stu-id="dae44-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dae44-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dae44-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="dae44-111">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="dae44-111">Time of session request.</span></span> <span data-ttu-id="dae44-112">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="dae44-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="dae44-113">Pour plus d’informations, consultez le <a href="lync-server-2013-dialogs-table.md">tableau de boîte de dialogue dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-115">int</span><span class="sxs-lookup"><span data-stu-id="dae44-115">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-116">ID number to identify the session.</span></span> <span data-ttu-id="dae44-117">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="dae44-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="dae44-118">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dae44-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="dae44-121">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="dae44-121">Time of the first INVITE request.</span></span> <span data-ttu-id="dae44-122">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dae44-123">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="dae44-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="dae44-124">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dae44-125">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="dae44-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-128">URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-129"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-131">URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-134">Type d’URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="dae44-135">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-138">Type d’URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="dae44-139">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-142">Client de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="dae44-143">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-146">Le client de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="dae44-147">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-149">identificateur</span><span class="sxs-lookup"><span data-stu-id="dae44-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dae44-150">Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-152">identificateur</span><span class="sxs-lookup"><span data-stu-id="dae44-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dae44-153">Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dae44-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="dae44-156">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-158">int</span><span class="sxs-lookup"><span data-stu-id="dae44-158">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-159">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-161">int</span><span class="sxs-lookup"><span data-stu-id="dae44-161">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-162">Nombre de messages envoyés par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-165">Version du client utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-167">int</span><span class="sxs-lookup"><span data-stu-id="dae44-167">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-168">Client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-168">Client used by the user who started the session.</span></span> <span data-ttu-id="dae44-169">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dae44-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dae44-172">Nom de la catégorie du client utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-175">Version du client utilisée par l’utilisateur ayant rejoint la session</span><span class="sxs-lookup"><span data-stu-id="dae44-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-177">int</span><span class="sxs-lookup"><span data-stu-id="dae44-177">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-178">Client utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="dae44-179">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dae44-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dae44-182">Nom de la catégorie du client utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-185">URI de l’utilisateur cible de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-188">Type d’URI de l’utilisateur cible pour la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="dae44-189">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-192">URI de l’utilisateur au nom duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="dae44-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-195">Type d’URI de l’utilisateur au nom duquel la session a démarré.</span><span class="sxs-lookup"><span data-stu-id="dae44-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="dae44-196">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-199">Client de l’utilisateur dont le nom est démarré.</span><span class="sxs-lookup"><span data-stu-id="dae44-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="dae44-200">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dae44-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dae44-203">URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-206">Type d’URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="dae44-207">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-210">Client de l’utilisateur qui a fait appel à la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="dae44-211">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="dae44-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="dae44-214">ID de boîte de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="dae44-214">SIP dialog ID.</span></span> <span data-ttu-id="dae44-215">Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="dae44-215">The format is:</span></span></p>
<p><span data-ttu-id="dae44-216">boîte de dialogue ; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="dae44-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-217"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-218">identificateur</span><span class="sxs-lookup"><span data-stu-id="dae44-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dae44-219">GUID utilisé pour mettre en corrélation plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="dae44-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-221">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dae44-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="dae44-222">Heure de la boîte de dialogue qui a été remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="dae44-223">Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de façon unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="dae44-224">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-226">int</span><span class="sxs-lookup"><span data-stu-id="dae44-226">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-227">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-227">ID number to identify the session.</span></span> <span data-ttu-id="dae44-228">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de façon unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="dae44-229">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dae44-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="dae44-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="dae44-232">ID de boîte de dialogue SIP le remplacement de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="dae44-233">Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="dae44-233">The format is:</span></span></p>
<p><span data-ttu-id="dae44-234">boîte de dialogue ; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="dae44-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dae44-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="dae44-237">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="dae44-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="dae44-238">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dae44-239">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="dae44-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-241">int</span><span class="sxs-lookup"><span data-stu-id="dae44-241">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-242">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="dae44-243">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dae44-244">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="dae44-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-246">int</span><span class="sxs-lookup"><span data-stu-id="dae44-246">int</span></span></p></td>
<td><p><span data-ttu-id="dae44-247">ID de diagnostic capturé à partir d’en-têtes SIP.</span><span class="sxs-lookup"><span data-stu-id="dae44-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-248"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-250">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-253">Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-256">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-259">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-262">Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-264">bit</span><span class="sxs-lookup"><span data-stu-id="dae44-264">bit</span></span></p></td>
<td><p><span data-ttu-id="dae44-265">Indique si l’utilisateur qui a démarré la session s’est connecté à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="dae44-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-267">bit</span><span class="sxs-lookup"><span data-stu-id="dae44-267">bit</span></span></p></td>
<td><p><span data-ttu-id="dae44-268">Indique si l’utilisateur ayant rejoint la session à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="dae44-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dae44-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dae44-271">Priorité de la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-273">type</span><span class="sxs-lookup"><span data-stu-id="dae44-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="dae44-274">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="dae44-275">Les définitions d’attribut suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="dae44-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="dae44-276">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="dae44-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-278">type</span><span class="sxs-lookup"><span data-stu-id="dae44-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="dae44-279">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="dae44-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="dae44-280">Les définitions d’attribut suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="dae44-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="dae44-281">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="dae44-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae44-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-283">type</span><span class="sxs-lookup"><span data-stu-id="dae44-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="dae44-284">Indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="dae44-284">Indicates the call attributes.</span></span> <span data-ttu-id="dae44-285">Les définitions d’attribut suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="dae44-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="dae44-286">0x01-nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="dae44-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="dae44-287">0x02-appel émis par l’agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="dae44-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae44-288"><strong>Emplacement</strong></span><span class="sxs-lookup"><span data-stu-id="dae44-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="dae44-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="dae44-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="dae44-290">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dae44-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

