---
title: 'Lync Server 2013 : vue ConferenceSessionDetails'
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
ms.openlocfilehash: cf8023408990b7f0243aaf0e937e2d1095dff0c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529181"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="aab17-102">Vue ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aab17-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aab17-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="aab17-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="aab17-104">L’affichage ConferenceSessionDetails stocke les informations relatives aux sessions entre plusieurs participants.</span><span class="sxs-lookup"><span data-stu-id="aab17-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="aab17-105">Chaque enregistrement représente une session de conférence, laquelle peut être la session ayant le focus ou la session basée sur un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="aab17-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="aab17-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aab17-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aab17-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="aab17-107">Column</span></span></th>
<th><span data-ttu-id="aab17-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="aab17-108">Data Type</span></span></th>
<th><span data-ttu-id="aab17-109">Détails</span><span class="sxs-lookup"><span data-stu-id="aab17-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aab17-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aab17-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="aab17-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="aab17-112">Time of session request.</span></span> <span data-ttu-id="aab17-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="aab17-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="aab17-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-116">int</span><span class="sxs-lookup"><span data-stu-id="aab17-116">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-117">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-117">ID number to identify the session.</span></span> <span data-ttu-id="aab17-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="aab17-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="aab17-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aab17-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="aab17-p104">Heure de la première requête INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="aab17-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aab17-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aab17-127">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-130">Type de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-130">Type of conference URI.</span></span> <span data-ttu-id="aab17-131">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-133">unique</span><span class="sxs-lookup"><span data-stu-id="aab17-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="aab17-p106">Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="aab17-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aab17-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aab17-138">URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-141">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-141">Type of conferencing server URI.</span></span> <span data-ttu-id="aab17-142">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aab17-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aab17-145">URI de l’utilisateur impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-148">Type de l’URI de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="aab17-149">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-152">Client de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="aab17-153">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-155">unique</span><span class="sxs-lookup"><span data-stu-id="aab17-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="aab17-156">Identificateur unique de l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-158">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aab17-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="aab17-159">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-162">Version du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-164">int</span><span class="sxs-lookup"><span data-stu-id="aab17-164">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-165">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-165">Type of conference server.</span></span> <span data-ttu-id="aab17-166">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aab17-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aab17-169">Catégorie du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-172">Version du client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-174">int</span><span class="sxs-lookup"><span data-stu-id="aab17-174">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-175">Client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="aab17-176">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aab17-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aab17-179">Nom de la catégorie du client dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aab17-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aab17-182">URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="aab17-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-185">Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="aab17-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="aab17-186">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-189">Client de l’utilisateur pour le compte duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="aab17-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="aab17-190">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aab17-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aab17-193">URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-196">Type de l’URI de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="aab17-197">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-200">Client de l’utilisateur qui a référencé la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="aab17-201">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="aab17-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="aab17-p116">ID de dialogue SIP. Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="aab17-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="aab17-206">:d ialog ; from-tag ; to-tag</span><span class="sxs-lookup"><span data-stu-id="aab17-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-208">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aab17-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="aab17-209">Numéro d’identification permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="aab17-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="aab17-210">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-212">int</span><span class="sxs-lookup"><span data-stu-id="aab17-212">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-213">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-213">ID number to identify the session.</span></span> <span data-ttu-id="aab17-214">Utilisé conjointement avec ReplacesDialogIdTime pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="aab17-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="aab17-215">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aab17-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="aab17-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="aab17-p119">ID de dialogue SIP de la session. Le format est le suivant :</span><span class="sxs-lookup"><span data-stu-id="aab17-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="aab17-220">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="aab17-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-222">légèrement</span><span class="sxs-lookup"><span data-stu-id="aab17-222">bit</span></span></p></td>
<td><p><span data-ttu-id="aab17-223">Indique si la session a été démarrée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-225">légèrement</span><span class="sxs-lookup"><span data-stu-id="aab17-225">bit</span></span></p></td>
<td><p><span data-ttu-id="aab17-226">Indique si la session a été terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="aab17-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-228">légèrement</span><span class="sxs-lookup"><span data-stu-id="aab17-228">bit</span></span></p></td>
<td><p><span data-ttu-id="aab17-229">Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</span><span class="sxs-lookup"><span data-stu-id="aab17-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="aab17-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="aab17-p120">Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="aab17-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-236">int</span><span class="sxs-lookup"><span data-stu-id="aab17-236">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="aab17-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-241">int</span><span class="sxs-lookup"><span data-stu-id="aab17-241">int</span></span></p></td>
<td><p><span data-ttu-id="aab17-242">ID de diagnostic capturé à partir des en-têtes de session SIP.</span><span class="sxs-lookup"><span data-stu-id="aab17-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-245">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-248">Nom de domaine complet du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-251">Nom de domaine complet du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-254">Serveur de médiation dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-255"><strong>Passerelle</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-257">Passerelle dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aab17-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aab17-260">Nom de domaine complet du serveur Edge dont s’est servi l’utilisateur qui a participé à la session.</span><span class="sxs-lookup"><span data-stu-id="aab17-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aab17-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-262">type</span><span class="sxs-lookup"><span data-stu-id="aab17-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="aab17-p122">Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="aab17-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="aab17-265">0x01 - Intégré au téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="aab17-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aab17-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="aab17-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="aab17-267">type</span><span class="sxs-lookup"><span data-stu-id="aab17-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="aab17-p123">Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="aab17-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="aab17-270">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="aab17-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="aab17-271">0x02 - Appel effectué par un agent pour le compte d’un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="aab17-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

