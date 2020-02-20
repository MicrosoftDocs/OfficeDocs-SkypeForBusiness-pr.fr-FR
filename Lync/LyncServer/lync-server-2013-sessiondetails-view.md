---
title: 'Lync Server 2013 : vue SessionDetails'
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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b5d6d-102">Vue SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5d6d-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5d6d-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b5d6d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b5d6d-104">L’affichage SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux personnes ou tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="b5d6d-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5d6d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b5d6d-106">Column</span></span></th>
<th><span data-ttu-id="b5d6d-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="b5d6d-107">Data Type</span></span></th>
<th><span data-ttu-id="b5d6d-108">Détails</span><span class="sxs-lookup"><span data-stu-id="b5d6d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b5d6d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-111">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-111">Time of session request.</span></span> <span data-ttu-id="b5d6d-112">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b5d6d-113">Pour plus d’informations, reportez-vous à la table <a href="lync-server-2013-dialogs-table.md">Dialogs dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-115">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-115">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-116">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-116">ID number to identify the session.</span></span> <span data-ttu-id="b5d6d-117">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b5d6d-118">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b5d6d-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-121">Heure de la première requête INVITE.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-121">Time of the first INVITE request.</span></span> <span data-ttu-id="b5d6d-122">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b5d6d-123">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d6d-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="b5d6d-124">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b5d6d-125">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d6d-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-128">URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-129"><strong>Visite guidée</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-131">URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-134">Type d’URI de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="b5d6d-135">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-138">Type d’URI de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="b5d6d-139">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-142">Client de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="b5d6d-143">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-146">Le client de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="b5d6d-147">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-149">unique</span><span class="sxs-lookup"><span data-stu-id="b5d6d-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-150">Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-152">unique</span><span class="sxs-lookup"><span data-stu-id="b5d6d-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-153">Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b5d6d-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-156">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-158">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-158">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-159">Nombre de messages envoyés par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-161">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-161">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-162">Nombre de messages envoyés par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-165">Version du client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-167">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-167">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-168">Client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-168">Client used by the user who started the session.</span></span> <span data-ttu-id="b5d6d-169">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-172">Nom de la catégorie du client utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-175">Version du client utilisé par l’utilisateur qui a rejoint la session</span><span class="sxs-lookup"><span data-stu-id="b5d6d-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-177">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-177">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-178">Client utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="b5d6d-179">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-182">Nom de la catégorie du client utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-185">URI de l’utilisateur cible de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-188">Type d’URI de l’utilisateur cible pour la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="b5d6d-189">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-192">URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-195">Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b5d6d-196">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-199">Client de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b5d6d-200">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-203">URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-206">Type de l’URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b5d6d-207">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-210">Client de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b5d6d-211">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-214">ID de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-214">SIP dialog ID.</span></span> <span data-ttu-id="b5d6d-215">Le format est :</span><span class="sxs-lookup"><span data-stu-id="b5d6d-215">The format is:</span></span></p>
<p><span data-ttu-id="b5d6d-216">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="b5d6d-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-217"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-218">unique</span><span class="sxs-lookup"><span data-stu-id="b5d6d-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-219">GUID utilisé pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-221">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b5d6d-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-222">Heure de la boîte de dialogue qui a été remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="b5d6d-223">Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de manière unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b5d6d-224">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-226">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-226">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-227">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-227">ID number to identify the session.</span></span> <span data-ttu-id="b5d6d-228">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une boîte de dialogue qui est remplacée par la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b5d6d-229">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5d6d-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-232">ID de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="b5d6d-233">Le format est :</span><span class="sxs-lookup"><span data-stu-id="b5d6d-233">The format is:</span></span></p>
<p><span data-ttu-id="b5d6d-234">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="b5d6d-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b5d6d-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-p120">Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d6d-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-241">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-241">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d6d-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-246">int</span><span class="sxs-lookup"><span data-stu-id="b5d6d-246">int</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-247">ID de diagnostic capturé à partir des en-têtes SIP.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-250">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-253">Nom de domaine complet du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-256">Nom de domaine complet du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-259">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-262">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session</span><span class="sxs-lookup"><span data-stu-id="b5d6d-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-264">légèrement</span><span class="sxs-lookup"><span data-stu-id="b5d6d-264">bit</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-265">Indique si l’utilisateur qui a démarré la session a ouvert une session depuis le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-267">légèrement</span><span class="sxs-lookup"><span data-stu-id="b5d6d-267">bit</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-268">Indique si l’utilisateur qui a rejoint la session à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-271">Priorité d’appel de la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-273">type</span><span class="sxs-lookup"><span data-stu-id="b5d6d-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-274">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="b5d6d-275">Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="b5d6d-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b5d6d-276">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="b5d6d-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-278">type</span><span class="sxs-lookup"><span data-stu-id="b5d6d-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-279">Indique les attributs de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="b5d6d-280">Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="b5d6d-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b5d6d-281">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="b5d6d-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d6d-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-283">type</span><span class="sxs-lookup"><span data-stu-id="b5d6d-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-p124">Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="b5d6d-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b5d6d-286">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="b5d6d-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="b5d6d-287">0x02-appel effectué par un agent pour le compte d’un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="b5d6d-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d6d-288"><strong>Emplacement</strong></span><span class="sxs-lookup"><span data-stu-id="b5d6d-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d6d-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b5d6d-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b5d6d-290">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b5d6d-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

