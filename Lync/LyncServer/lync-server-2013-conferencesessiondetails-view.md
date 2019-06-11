---
title: 'Affichage Lync Server 2013: ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="7da8d-102">Affichage ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7da8d-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7da8d-103">_**Dernière modification de la rubrique:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="7da8d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="7da8d-104">Le mode ConferenceSessionDetails stocke les informations sur les sessions multiparties.</span><span class="sxs-lookup"><span data-stu-id="7da8d-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="7da8d-105">Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.</span><span class="sxs-lookup"><span data-stu-id="7da8d-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="7da8d-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7da8d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7da8d-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="7da8d-107">Column</span></span></th>
<th><span data-ttu-id="7da8d-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="7da8d-108">Data Type</span></span></th>
<th><span data-ttu-id="7da8d-109">Détails</span><span class="sxs-lookup"><span data-stu-id="7da8d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7da8d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da8d-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-112">Time of session request.</span></span> <span data-ttu-id="7da8d-113">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="7da8d-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7da8d-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-116">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-116">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-117">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-117">ID number to identify the session.</span></span> <span data-ttu-id="7da8d-118">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="7da8d-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7da8d-119">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7da8d-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da8d-122">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="7da8d-122">Time of the first INVITE request.</span></span> <span data-ttu-id="7da8d-123">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7da8d-124">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="7da8d-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7da8d-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-127">URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-130">URI du type de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-130">Type of conference URI.</span></span> <span data-ttu-id="7da8d-131">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-133">identificateur</span><span class="sxs-lookup"><span data-stu-id="7da8d-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7da8d-134">Identificateur qui différencie les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="7da8d-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="7da8d-135">Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="7da8d-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7da8d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-138">URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-141">Type d’URI du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-141">Type of conferencing server URI.</span></span> <span data-ttu-id="7da8d-142">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7da8d-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-145">URI de l’utilisateur impliqué dans la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-148">Type d’URI de l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="7da8d-149">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-152">Client de l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="7da8d-153">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-155">identificateur</span><span class="sxs-lookup"><span data-stu-id="7da8d-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7da8d-156">Identificateur unique de l’utilisateur dont vous participez à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-158">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7da8d-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da8d-159">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-162">Version du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-164">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-164">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-165">Type du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-165">Type of conference server.</span></span> <span data-ttu-id="7da8d-166">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7da8d-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-169">Catégorie de serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-172">Version du client utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-174">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-174">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-175">Client utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="7da8d-176">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7da8d-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-179">Nom de la catégorie du client utilisée par l’utilisateur qui faisait partie de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7da8d-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-182">URI de l’utilisateur au nom duquel la session a été démarrée.</span><span class="sxs-lookup"><span data-stu-id="7da8d-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-185">Type d’URI de l’utilisateur au nom duquel la session a démarré.</span><span class="sxs-lookup"><span data-stu-id="7da8d-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="7da8d-186">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-189">Client de l’utilisateur dont le nom est démarré.</span><span class="sxs-lookup"><span data-stu-id="7da8d-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="7da8d-190">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7da8d-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-193">URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-196">Type d’URI de l’utilisateur qui a expertisé la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="7da8d-197">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-200">Client de l’utilisateur qui a fait appel à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="7da8d-201">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-203">varstring (LGA775)</span><span class="sxs-lookup"><span data-stu-id="7da8d-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-204">ID de boîte de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="7da8d-204">SIP dialog ID.</span></span> <span data-ttu-id="7da8d-205">Le format est</span><span class="sxs-lookup"><span data-stu-id="7da8d-205">The format is</span></span></p>
<p><span data-ttu-id="7da8d-206">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="7da8d-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-208">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7da8d-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da8d-209">Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="7da8d-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="7da8d-210">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-212">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-212">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-213">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-213">ID number to identify the session.</span></span> <span data-ttu-id="7da8d-214">Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une session qui est remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="7da8d-215">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7da8d-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="7da8d-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-218">ID de boîte de dialogue SIP le remplacement de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="7da8d-219">Le format de:</span><span class="sxs-lookup"><span data-stu-id="7da8d-219">The format of the is:</span></span></p>
<p><span data-ttu-id="7da8d-220">boîte de dialogue; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="7da8d-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-222">bit</span><span class="sxs-lookup"><span data-stu-id="7da8d-222">bit</span></span></p></td>
<td><p><span data-ttu-id="7da8d-223">Indique si la session a été démarrée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-225">bit</span><span class="sxs-lookup"><span data-stu-id="7da8d-225">bit</span></span></p></td>
<td><p><span data-ttu-id="7da8d-226">Indique si la session a été terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="7da8d-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-228">bit</span><span class="sxs-lookup"><span data-stu-id="7da8d-228">bit</span></span></p></td>
<td><p><span data-ttu-id="7da8d-229">Indique si l’utilisateur s’est connecté à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="7da8d-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="7da8d-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da8d-232">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="7da8d-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="7da8d-233">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7da8d-234">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="7da8d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-236">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-236">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-237">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="7da8d-238">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7da8d-239">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="7da8d-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-241">int</span><span class="sxs-lookup"><span data-stu-id="7da8d-241">int</span></span></p></td>
<td><p><span data-ttu-id="7da8d-242">ID de diagnostic capturé à partir d’en-têtes SIP de session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-243"><strong>Indiquez</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-245">Type de contenu de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-248">Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-251">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-254">Serveur de médiation utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-255"><strong>Passerelle</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-257">Passerelle utilisée par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7da8d-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7da8d-260">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da8d-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-262">type</span><span class="sxs-lookup"><span data-stu-id="7da8d-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="7da8d-263">Indique les attributs de l’utilisateur ayant participé à la session.</span><span class="sxs-lookup"><span data-stu-id="7da8d-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="7da8d-264">Les définitions d’attribut suivantes sont autorisées:</span><span class="sxs-lookup"><span data-stu-id="7da8d-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="7da8d-265">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="7da8d-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da8d-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7da8d-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7da8d-267">type</span><span class="sxs-lookup"><span data-stu-id="7da8d-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="7da8d-268">Indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="7da8d-268">Indicates the call attributes.</span></span> <span data-ttu-id="7da8d-269">Les définitions d’attribut suivantes sont autorisées:</span><span class="sxs-lookup"><span data-stu-id="7da8d-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="7da8d-270">0x01-nouvelle tentative de Session0</span><span class="sxs-lookup"><span data-stu-id="7da8d-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="7da8d-271">x02: appel passé par l’agent pour le compte d’un Response Group</span><span class="sxs-lookup"><span data-stu-id="7da8d-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

