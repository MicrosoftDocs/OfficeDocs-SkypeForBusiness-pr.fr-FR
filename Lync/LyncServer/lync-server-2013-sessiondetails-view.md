---
title: 'Lync Server 2013 : vue SessionDetails'
description: 'Lync Server 2013 : vue SessionDetails.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573240"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="fe8cc-103">Vue SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe8cc-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe8cc-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fe8cc-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fe8cc-105">L’affichage SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux personnes ou tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="fe8cc-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe8cc-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="fe8cc-107">Column</span></span></th>
<th><span data-ttu-id="fe8cc-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="fe8cc-108">Data Type</span></span></th>
<th><span data-ttu-id="fe8cc-109">Détails</span><span class="sxs-lookup"><span data-stu-id="fe8cc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe8cc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-112">Time of session request.</span></span> <span data-ttu-id="fe8cc-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fe8cc-114">Pour plus d’informations, reportez-vous à la table <a href="lync-server-2013-dialogs-table.md">Dialogs dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-116">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-117">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-117">ID number to identify the session.</span></span> <span data-ttu-id="fe8cc-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fe8cc-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe8cc-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-122">Heure de la première requête INVITE.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-122">Time of the first INVITE request.</span></span> <span data-ttu-id="fe8cc-123">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="fe8cc-124">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="fe8cc-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="fe8cc-125">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-125">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="fe8cc-126">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="fe8cc-126">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-129">URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-130"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-132">URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-135">Type d’URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="fe8cc-136">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-139">Type d’URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="fe8cc-140">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-143">Client de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="fe8cc-144">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-145"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-147">Le client de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="fe8cc-148">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-150">unique</span><span class="sxs-lookup"><span data-stu-id="fe8cc-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-151">Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-153">unique</span><span class="sxs-lookup"><span data-stu-id="fe8cc-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-154">Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-156">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe8cc-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-157">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-159">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-159">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-160">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-162">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-162">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-163">Nombre de messages envoyés par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-166">Version du client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-168">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-168">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-169">Client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-169">Client used by the user who started the session.</span></span> <span data-ttu-id="fe8cc-170">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-173">Nom de la catégorie du client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-176">Version du client utilisé par l’utilisateur qui a rejoint la session</span><span class="sxs-lookup"><span data-stu-id="fe8cc-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-178">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-178">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-179">Client utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="fe8cc-180">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-183">Nom de la catégorie du client utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-186">URI de l’utilisateur cible de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-189">Type d’URI de l’utilisateur cible pour la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="fe8cc-190">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-193">URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-196">Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="fe8cc-197">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-200">Client de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="fe8cc-201">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-204">URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-207">Type de l’URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="fe8cc-208">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-211">Client de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="fe8cc-212">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-215">ID de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-215">SIP dialog ID.</span></span> <span data-ttu-id="fe8cc-216">Le format est :</span><span class="sxs-lookup"><span data-stu-id="fe8cc-216">The format is:</span></span></p>
<p><span data-ttu-id="fe8cc-217">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="fe8cc-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-218"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-219">unique</span><span class="sxs-lookup"><span data-stu-id="fe8cc-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-220">GUID utilisé pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-222">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe8cc-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-223">Heure de la boîte de dialogue qui a été remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="fe8cc-224">Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de manière unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="fe8cc-225">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-227">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-227">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-228">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-228">ID number to identify the session.</span></span> <span data-ttu-id="fe8cc-229">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="fe8cc-230">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe8cc-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-233">ID de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-233">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="fe8cc-234">Le format est :</span><span class="sxs-lookup"><span data-stu-id="fe8cc-234">The format is:</span></span></p>
<p><span data-ttu-id="fe8cc-235">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="fe8cc-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-237">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe8cc-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-p120">Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="fe8cc-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-242">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-242">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="fe8cc-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-247">int</span><span class="sxs-lookup"><span data-stu-id="fe8cc-247">int</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-248">ID de diagnostic capturé à partir des en-têtes SIP.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-251">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-254">Nom de domaine complet du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-257">Nom de domaine complet du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-260">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-263">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session</span><span class="sxs-lookup"><span data-stu-id="fe8cc-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-265">légèrement</span><span class="sxs-lookup"><span data-stu-id="fe8cc-265">bit</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-266">Indique si l’utilisateur qui a démarré la session a ouvert une session depuis le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-268">légèrement</span><span class="sxs-lookup"><span data-stu-id="fe8cc-268">bit</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-269">Indique si l’utilisateur qui a rejoint la session à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-272">Priorité d’appel de la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-274">type</span><span class="sxs-lookup"><span data-stu-id="fe8cc-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-275">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-275">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="fe8cc-276">Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="fe8cc-276">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="fe8cc-277">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="fe8cc-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-279">type</span><span class="sxs-lookup"><span data-stu-id="fe8cc-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-280">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-280">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="fe8cc-281">Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="fe8cc-281">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="fe8cc-282">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="fe8cc-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe8cc-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-284">type</span><span class="sxs-lookup"><span data-stu-id="fe8cc-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-p124">Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="fe8cc-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="fe8cc-287">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="fe8cc-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="fe8cc-288">0x02-appel effectué par un agent pour le compte d’un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="fe8cc-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe8cc-289"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="fe8cc-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="fe8cc-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="fe8cc-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="fe8cc-291">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fe8cc-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

