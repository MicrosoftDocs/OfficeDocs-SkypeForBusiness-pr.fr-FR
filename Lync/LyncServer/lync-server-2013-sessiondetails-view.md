---
title: 'Affichage Lync Server 2013: SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="f178a-102">Affichage SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f178a-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f178a-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f178a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f178a-104">La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou un autre type de session.</span><span class="sxs-lookup"><span data-stu-id="f178a-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="f178a-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f178a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f178a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f178a-106">Column</span></span></th>
<th><span data-ttu-id="f178a-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="f178a-107">Data Type</span></span></th>
<th><span data-ttu-id="f178a-108">Détails</span><span class="sxs-lookup"><span data-stu-id="f178a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f178a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f178a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f178a-111">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="f178a-111">Time of session request.</span></span> <span data-ttu-id="f178a-112">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="f178a-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f178a-113">Pour plus d’informations, consultez le <a href="lync-server-2013-dialogs-table.md">tableau de boîte de dialogue dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-115">int</span><span class="sxs-lookup"><span data-stu-id="f178a-115">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-116">ID number to identify the session.</span></span> <span data-ttu-id="f178a-117">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="f178a-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f178a-118">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f178a-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="f178a-121">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="f178a-121">Time of the first INVITE request.</span></span> <span data-ttu-id="f178a-122">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f178a-123">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="f178a-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="f178a-124">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f178a-125">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="f178a-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-128">URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-129"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-131">URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-134">Type d’URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="f178a-135">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-138">Type d’URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="f178a-139">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-142">Client de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="f178a-143">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-146">Le client de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="f178a-147">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-149">identificateur</span><span class="sxs-lookup"><span data-stu-id="f178a-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f178a-150">Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-152">identificateur</span><span class="sxs-lookup"><span data-stu-id="f178a-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f178a-153">Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f178a-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="f178a-156">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-158">int</span><span class="sxs-lookup"><span data-stu-id="f178a-158">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-159">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-161">int</span><span class="sxs-lookup"><span data-stu-id="f178a-161">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-162">Nombre de messages envoyés par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-165">Version du client utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-167">int</span><span class="sxs-lookup"><span data-stu-id="f178a-167">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-168">Client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-168">Client used by the user who started the session.</span></span> <span data-ttu-id="f178a-169">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f178a-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f178a-172">Nom de la catégorie du client utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-175">Version du client utilisée par l’utilisateur ayant rejoint la session</span><span class="sxs-lookup"><span data-stu-id="f178a-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-177">int</span><span class="sxs-lookup"><span data-stu-id="f178a-177">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-178">Client utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="f178a-179">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f178a-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f178a-182">Nom de la catégorie du client utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-185">URI de l’utilisateur cible de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-188">Type d’URI de l’utilisateur cible pour la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="f178a-189">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-192">URI de l’utilisateur au nom duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="f178a-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-195">Type d’URI de l’utilisateur au nom duquel la session a démarré.</span><span class="sxs-lookup"><span data-stu-id="f178a-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="f178a-196">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-199">Client de l’utilisateur dont le nom est démarré.</span><span class="sxs-lookup"><span data-stu-id="f178a-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="f178a-200">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f178a-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f178a-203">URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-206">Type d’URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="f178a-207">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-210">Client de l’utilisateur qui a fait appel à la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="f178a-211">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="f178a-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="f178a-214">ID de boîte de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="f178a-214">SIP dialog ID.</span></span> <span data-ttu-id="f178a-215">Le format est le suivant:</span><span class="sxs-lookup"><span data-stu-id="f178a-215">The format is:</span></span></p>
<p><span data-ttu-id="f178a-216">boîte de dialogue; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="f178a-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-217"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-218">identificateur</span><span class="sxs-lookup"><span data-stu-id="f178a-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f178a-219">GUID utilisé pour mettre en corrélation plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="f178a-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-221">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f178a-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="f178a-222">Heure de la boîte de dialogue qui a été remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="f178a-223">Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de façon unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="f178a-224">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-226">int</span><span class="sxs-lookup"><span data-stu-id="f178a-226">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-227">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-227">ID number to identify the session.</span></span> <span data-ttu-id="f178a-228">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de façon unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="f178a-229">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f178a-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="f178a-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="f178a-232">ID de boîte de dialogue SIP le remplacement de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="f178a-233">Le format est le suivant:</span><span class="sxs-lookup"><span data-stu-id="f178a-233">The format is:</span></span></p>
<p><span data-ttu-id="f178a-234">boîte de dialogue; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="f178a-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f178a-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="f178a-237">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="f178a-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="f178a-238">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f178a-239">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="f178a-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-241">int</span><span class="sxs-lookup"><span data-stu-id="f178a-241">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-242">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="f178a-243">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f178a-244">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="f178a-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-246">int</span><span class="sxs-lookup"><span data-stu-id="f178a-246">int</span></span></p></td>
<td><p><span data-ttu-id="f178a-247">ID de diagnostic capturé à partir d’en-têtes SIP.</span><span class="sxs-lookup"><span data-stu-id="f178a-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-248"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-250">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-253">Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-256">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-259">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-262">Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-264">bit</span><span class="sxs-lookup"><span data-stu-id="f178a-264">bit</span></span></p></td>
<td><p><span data-ttu-id="f178a-265">Indique si l’utilisateur qui a démarré la session s’est connecté à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f178a-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-267">bit</span><span class="sxs-lookup"><span data-stu-id="f178a-267">bit</span></span></p></td>
<td><p><span data-ttu-id="f178a-268">Indique si l’utilisateur ayant rejoint la session à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f178a-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f178a-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f178a-271">Priorité de la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-273">type</span><span class="sxs-lookup"><span data-stu-id="f178a-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="f178a-274">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="f178a-275">Les définitions d’attribut suivantes sont autorisées:</span><span class="sxs-lookup"><span data-stu-id="f178a-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="f178a-276">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="f178a-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-278">type</span><span class="sxs-lookup"><span data-stu-id="f178a-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="f178a-279">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f178a-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="f178a-280">Les définitions d’attribut suivantes sont autorisées:</span><span class="sxs-lookup"><span data-stu-id="f178a-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="f178a-281">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="f178a-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f178a-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-283">type</span><span class="sxs-lookup"><span data-stu-id="f178a-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="f178a-284">Indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="f178a-284">Indicates the call attributes.</span></span> <span data-ttu-id="f178a-285">Les définitions d’attribut suivantes sont autorisées:</span><span class="sxs-lookup"><span data-stu-id="f178a-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="f178a-286">0x01-nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="f178a-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="f178a-287">0x02-appel émis par l’agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="f178a-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f178a-288"><strong>Emplacement</strong></span><span class="sxs-lookup"><span data-stu-id="f178a-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="f178a-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f178a-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f178a-290">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f178a-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

