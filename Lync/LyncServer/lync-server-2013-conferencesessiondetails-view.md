---
title: 'Affichage Lync Server 2013 : ConferenceSessionDetails'
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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="db20e-102">Affichage ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db20e-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db20e-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="db20e-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="db20e-104">Le mode ConferenceSessionDetails stocke les informations sur les sessions multiparties.</span><span class="sxs-lookup"><span data-stu-id="db20e-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="db20e-105">Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.</span><span class="sxs-lookup"><span data-stu-id="db20e-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="db20e-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db20e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db20e-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="db20e-107">Column</span></span></th>
<th><span data-ttu-id="db20e-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="db20e-108">Data Type</span></span></th>
<th><span data-ttu-id="db20e-109">Détails</span><span class="sxs-lookup"><span data-stu-id="db20e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db20e-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db20e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="db20e-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="db20e-112">Time of session request.</span></span> <span data-ttu-id="db20e-113">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="db20e-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="db20e-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-116">int</span><span class="sxs-lookup"><span data-stu-id="db20e-116">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-117">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-117">ID number to identify the session.</span></span> <span data-ttu-id="db20e-118">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="db20e-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="db20e-119">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db20e-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="db20e-122">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="db20e-122">Time of the first INVITE request.</span></span> <span data-ttu-id="db20e-123">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="db20e-124">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="db20e-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="db20e-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db20e-127">URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-130">URI du type de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-130">Type of conference URI.</span></span> <span data-ttu-id="db20e-131">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-133">identificateur</span><span class="sxs-lookup"><span data-stu-id="db20e-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="db20e-134">Identificateur qui différencie les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="db20e-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="db20e-135">Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="db20e-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="db20e-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db20e-138">URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-141">Type d’URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-141">Type of conferencing server URI.</span></span> <span data-ttu-id="db20e-142">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="db20e-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db20e-145">URI de l’utilisateur impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-148">Type d’URI de l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="db20e-149">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-152">Client de l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="db20e-153">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-155">identificateur</span><span class="sxs-lookup"><span data-stu-id="db20e-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="db20e-156">Identificateur unique de l’utilisateur dont vous participez à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-158">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db20e-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="db20e-159">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-162">Version du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-164">int</span><span class="sxs-lookup"><span data-stu-id="db20e-164">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-165">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-165">Type of conference server.</span></span> <span data-ttu-id="db20e-166">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="db20e-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="db20e-169">Catégorie de serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-172">Version du client utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-174">int</span><span class="sxs-lookup"><span data-stu-id="db20e-174">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-175">Client utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="db20e-176">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="db20e-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="db20e-179">Nom de la catégorie du client utilisée par l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="db20e-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db20e-182">URI de l’utilisateur au nom duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="db20e-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-185">Type d’URI de l’utilisateur au nom duquel la session a démarré.</span><span class="sxs-lookup"><span data-stu-id="db20e-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="db20e-186">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-189">Client de l’utilisateur dont le nom est démarré.</span><span class="sxs-lookup"><span data-stu-id="db20e-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="db20e-190">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="db20e-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db20e-193">URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-196">Type d’URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="db20e-197">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-200">Client de l’utilisateur qui a fait appel à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="db20e-201">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-203">varstring (LGA775)</span><span class="sxs-lookup"><span data-stu-id="db20e-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="db20e-204">ID de boîte de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="db20e-204">SIP dialog ID.</span></span> <span data-ttu-id="db20e-205">Le format est</span><span class="sxs-lookup"><span data-stu-id="db20e-205">The format is</span></span></p>
<p><span data-ttu-id="db20e-206">:d ialog ; from-tag ; to-tag</span><span class="sxs-lookup"><span data-stu-id="db20e-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-208">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db20e-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="db20e-209">Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="db20e-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="db20e-210">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-212">int</span><span class="sxs-lookup"><span data-stu-id="db20e-212">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-213">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-213">ID number to identify the session.</span></span> <span data-ttu-id="db20e-214">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une session qui est remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="db20e-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="db20e-215">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="db20e-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="db20e-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="db20e-218">ID de boîte de dialogue SIP le remplacement de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="db20e-219">Le format de :</span><span class="sxs-lookup"><span data-stu-id="db20e-219">The format of the is:</span></span></p>
<p><span data-ttu-id="db20e-220">boîte de dialogue ; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="db20e-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-222">bit</span><span class="sxs-lookup"><span data-stu-id="db20e-222">bit</span></span></p></td>
<td><p><span data-ttu-id="db20e-223">Indique si la session a été démarrée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-225">bit</span><span class="sxs-lookup"><span data-stu-id="db20e-225">bit</span></span></p></td>
<td><p><span data-ttu-id="db20e-226">Indique si la session a été terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db20e-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-228">bit</span><span class="sxs-lookup"><span data-stu-id="db20e-228">bit</span></span></p></td>
<td><p><span data-ttu-id="db20e-229">Indique si l’utilisateur s’est connecté à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="db20e-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db20e-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="db20e-232">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="db20e-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="db20e-233">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="db20e-234">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="db20e-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-236">int</span><span class="sxs-lookup"><span data-stu-id="db20e-236">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-237">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="db20e-238">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="db20e-239">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="db20e-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-241">int</span><span class="sxs-lookup"><span data-stu-id="db20e-241">int</span></span></p></td>
<td><p><span data-ttu-id="db20e-242">ID de diagnostic capturé à partir d’en-têtes SIP de session.</span><span class="sxs-lookup"><span data-stu-id="db20e-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-243"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-245">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-248">Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-251">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-254">Serveur de médiation utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-255"><strong>Passerelle</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-257">Passerelle utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db20e-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db20e-260">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db20e-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-262">type</span><span class="sxs-lookup"><span data-stu-id="db20e-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="db20e-263">Indique les attributs de l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="db20e-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="db20e-264">Les définitions d’attribut suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="db20e-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="db20e-265">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="db20e-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db20e-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="db20e-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="db20e-267">type</span><span class="sxs-lookup"><span data-stu-id="db20e-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="db20e-268">Indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="db20e-268">Indicates the call attributes.</span></span> <span data-ttu-id="db20e-269">Les définitions d’attribut suivantes sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="db20e-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="db20e-270">0x01-nouvelle tentative de Session0</span><span class="sxs-lookup"><span data-stu-id="db20e-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="db20e-271">x02 : appel passé par l’agent pour le compte d’un Response Group</span><span class="sxs-lookup"><span data-stu-id="db20e-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

