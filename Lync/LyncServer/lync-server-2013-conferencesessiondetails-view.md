---
title: 'Lync Server 2013 : vue ConferenceSessionDetails'
description: 'Lync Server 2013 : vue ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566770"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="32b20-103">Vue ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32b20-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32b20-104">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="32b20-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="32b20-105">L’affichage ConferenceSessionDetails stocke les informations relatives aux sessions entre plusieurs participants.</span><span class="sxs-lookup"><span data-stu-id="32b20-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="32b20-106">Chaque enregistrement représente une session de conférence, laquelle peut être la session ayant le focus ou la session basée sur un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="32b20-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="32b20-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32b20-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32b20-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="32b20-108">Column</span></span></th>
<th><span data-ttu-id="32b20-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="32b20-109">Data Type</span></span></th>
<th><span data-ttu-id="32b20-110">Détails</span><span class="sxs-lookup"><span data-stu-id="32b20-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32b20-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="32b20-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="32b20-113">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="32b20-113">Time of session request.</span></span> <span data-ttu-id="32b20-114">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="32b20-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="32b20-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-117">int</span><span class="sxs-lookup"><span data-stu-id="32b20-117">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-118">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-118">ID number to identify the session.</span></span> <span data-ttu-id="32b20-119">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="32b20-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="32b20-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="32b20-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="32b20-p104">Heure de la première requête INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="32b20-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32b20-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32b20-128">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-131">Type de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-131">Type of conference URI.</span></span> <span data-ttu-id="32b20-132">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-134">unique</span><span class="sxs-lookup"><span data-stu-id="32b20-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="32b20-p106">Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="32b20-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32b20-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32b20-139">URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-142">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-142">Type of conferencing server URI.</span></span> <span data-ttu-id="32b20-143">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32b20-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32b20-146">URI de l’utilisateur impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-149">Type de l’URI de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="32b20-150">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-153">Client de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="32b20-154">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-156">unique</span><span class="sxs-lookup"><span data-stu-id="32b20-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="32b20-157">Identificateur unique de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-159">DateHeure</span><span class="sxs-lookup"><span data-stu-id="32b20-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="32b20-160">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-163">Version du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-165">int</span><span class="sxs-lookup"><span data-stu-id="32b20-165">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-166">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-166">Type of conference server.</span></span> <span data-ttu-id="32b20-167">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="32b20-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="32b20-170">Catégorie du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-173">Version du client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-175">int</span><span class="sxs-lookup"><span data-stu-id="32b20-175">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-176">Client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="32b20-177">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="32b20-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="32b20-180">Nom de la catégorie du client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32b20-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32b20-183">URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="32b20-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-186">Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="32b20-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="32b20-187">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-190">Client de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="32b20-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="32b20-191">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32b20-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32b20-194">URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-197">Type de l’URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="32b20-198">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-201">Client de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="32b20-202">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="32b20-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="32b20-p116">ID de dialogue SIP. Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="32b20-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="32b20-207">:d ialog ; from-tag ; to-tag</span><span class="sxs-lookup"><span data-stu-id="32b20-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-209">DateHeure</span><span class="sxs-lookup"><span data-stu-id="32b20-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="32b20-210">Numéro d’identification permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="32b20-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="32b20-211">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-213">int</span><span class="sxs-lookup"><span data-stu-id="32b20-213">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-214">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-214">ID number to identify the session.</span></span> <span data-ttu-id="32b20-215">Utilisé conjointement avec ReplacesDialogIdTime pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="32b20-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="32b20-216">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32b20-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="32b20-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="32b20-p119">ID de dialogue SIP de la session. Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="32b20-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="32b20-221">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="32b20-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-223">légèrement</span><span class="sxs-lookup"><span data-stu-id="32b20-223">bit</span></span></p></td>
<td><p><span data-ttu-id="32b20-224">Indique si la session a été démarrée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-226">légèrement</span><span class="sxs-lookup"><span data-stu-id="32b20-226">bit</span></span></p></td>
<td><p><span data-ttu-id="32b20-227">Indique si la session a été terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="32b20-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-229">légèrement</span><span class="sxs-lookup"><span data-stu-id="32b20-229">bit</span></span></p></td>
<td><p><span data-ttu-id="32b20-230">Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</span><span class="sxs-lookup"><span data-stu-id="32b20-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-232">DateHeure</span><span class="sxs-lookup"><span data-stu-id="32b20-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="32b20-p120">Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="32b20-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-237">int</span><span class="sxs-lookup"><span data-stu-id="32b20-237">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="32b20-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-242">int</span><span class="sxs-lookup"><span data-stu-id="32b20-242">int</span></span></p></td>
<td><p><span data-ttu-id="32b20-243">ID de diagnostic capturé à partir des en-têtes de session SIP.</span><span class="sxs-lookup"><span data-stu-id="32b20-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-246">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-249">Nom de domaine complet du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-252">Nom de domaine complet du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-255">Serveur de médiation dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-256"><strong>Passerelle</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-258">Passerelle dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32b20-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32b20-261">Nom de domaine complet du serveur Edge dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="32b20-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b20-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-263">type</span><span class="sxs-lookup"><span data-stu-id="32b20-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="32b20-p122">Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="32b20-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="32b20-266">0x01 - Intégré au téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="32b20-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b20-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="32b20-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="32b20-268">type</span><span class="sxs-lookup"><span data-stu-id="32b20-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="32b20-p123">Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="32b20-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="32b20-271">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="32b20-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="32b20-272">0x02 - Appel effectué par un agent pour le compte d’un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="32b20-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

