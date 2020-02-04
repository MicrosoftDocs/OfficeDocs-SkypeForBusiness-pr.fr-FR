---
title: 'Lync Server 2013 : Table ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="57d9e-102">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57d9e-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57d9e-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="57d9e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="57d9e-104">Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.</span><span class="sxs-lookup"><span data-stu-id="57d9e-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57d9e-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="57d9e-105">Column</span></span></th>
<th><span data-ttu-id="57d9e-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="57d9e-106">Data Type</span></span></th>
<th><span data-ttu-id="57d9e-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="57d9e-107">Key/Index</span></span></th>
<th><span data-ttu-id="57d9e-108">Détails</span><span class="sxs-lookup"><span data-stu-id="57d9e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-110">Valeur</span><span class="sxs-lookup"><span data-stu-id="57d9e-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="57d9e-111">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="57d9e-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-112">Durée de la demande de session ; utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="57d9e-113">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-115">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-115">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-116">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="57d9e-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-117">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-117">ID number to identify the session.</span></span> <span data-ttu-id="57d9e-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="57d9e-119">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-121">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-121">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-122">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-123">URI de conférence Focus liée à cette session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="57d9e-124">Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="57d9e-125">Cet URI est un URI de conférence en fonction du focus.</span><span class="sxs-lookup"><span data-stu-id="57d9e-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-127">Identificateur</span><span class="sxs-lookup"><span data-stu-id="57d9e-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-128">Identificateur qui différencie les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="57d9e-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="57d9e-129">Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="57d9e-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="57d9e-130">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57d9e-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-132">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-132">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-133">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-134">URI de la Conférence Server Conferencing liée à cette session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="57d9e-135">Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="57d9e-136">Cet URI est l’URI de conférence basée sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="57d9e-137">Pour les sessions de conférence au focus, cette colonne a la valeur null.</span><span class="sxs-lookup"><span data-stu-id="57d9e-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-139">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-139">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-140">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-141">ID d’un utilisateur dans la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-141">ID of one user in the conference session.</span></span> <span data-ttu-id="57d9e-142">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-144">identificateur</span><span class="sxs-lookup"><span data-stu-id="57d9e-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-145">GUID permettant d’identifier l’instance de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="57d9e-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="57d9e-146">Par exemple, si un utilisateur ouvre une session sur d’autres ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="57d9e-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-148">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-148">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-149">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-150">Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom.</span><span class="sxs-lookup"><span data-stu-id="57d9e-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="57d9e-151">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-153">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-153">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-154">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-155">ID de l’utilisateur avec lequel l’appel est soumis.</span><span class="sxs-lookup"><span data-stu-id="57d9e-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="57d9e-156">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-158">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-158">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-159">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-160">Version du client utilisée par l’utilisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-160">Client version used by the conference user.</span></span> <span data-ttu-id="57d9e-161">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-163">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-163">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-164">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-165">Version du client utilisée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-165">Client version used by the conference server.</span></span> <span data-ttu-id="57d9e-166">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-168">DateHeure</span><span class="sxs-lookup"><span data-stu-id="57d9e-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="57d9e-169">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-170">Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="57d9e-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="57d9e-171">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-173">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-173">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-174">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-175">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-175">ID number to identify the session.</span></span> <span data-ttu-id="57d9e-176">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session qui est remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="57d9e-177">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-179">bit</span><span class="sxs-lookup"><span data-stu-id="57d9e-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-180">Indique si la session a démarré par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-182">bit</span><span class="sxs-lookup"><span data-stu-id="57d9e-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-183">Indique si la session a été terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="57d9e-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-185">bit</span><span class="sxs-lookup"><span data-stu-id="57d9e-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-186">Si l’utilisateur est connecté à partir d’un emplacement interne ou non.</span><span class="sxs-lookup"><span data-stu-id="57d9e-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-188">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-189">Code de réponse SIP (Session Initiation Protocol) à l’invitation à la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="57d9e-190">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="57d9e-191">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="57d9e-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-193">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-194">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="57d9e-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-196">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-196">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-197">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-198">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="57d9e-199">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-201">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-201">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-202">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-203">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="57d9e-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="57d9e-204">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-206">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-206">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-207">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-208">Serveur de médiation utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="57d9e-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="57d9e-209">Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-211">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-211">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-212">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-213">Passerelle utilisée par l’appel.</span><span class="sxs-lookup"><span data-stu-id="57d9e-213">The gateway the call is using.</span></span> <span data-ttu-id="57d9e-214">Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-216">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-216">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-217">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-218">Serveur Edge utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="57d9e-218">The Edge Server the call is using.</span></span> <span data-ttu-id="57d9e-219">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-221">int</span><span class="sxs-lookup"><span data-stu-id="57d9e-221">int</span></span></p></td>
<td><p><span data-ttu-id="57d9e-222">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-223">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-223">Content type used in the session.</span></span> <span data-ttu-id="57d9e-224">Pour plus d’informations, voir la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57d9e-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-226">DateHeure</span><span class="sxs-lookup"><span data-stu-id="57d9e-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-227">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="57d9e-227">The time of the first INVITE request.</span></span> <span data-ttu-id="57d9e-228">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="57d9e-229">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="57d9e-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="57d9e-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-232">Heure de la première réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="57d9e-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="57d9e-233">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="57d9e-234">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="57d9e-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="57d9e-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-237">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="57d9e-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="57d9e-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="57d9e-240">Externes</span><span class="sxs-lookup"><span data-stu-id="57d9e-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57d9e-241">Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="57d9e-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="57d9e-242">Ce champ permet d’améliorer les performances de requête.</span><span class="sxs-lookup"><span data-stu-id="57d9e-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="57d9e-243">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57d9e-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d9e-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-245">type</span><span class="sxs-lookup"><span data-stu-id="57d9e-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-246">Un ensemble de bits indiquant les attributs de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="57d9e-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="57d9e-247">Les définitions d’attribut suivantes apparaissent :</span><span class="sxs-lookup"><span data-stu-id="57d9e-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="57d9e-248">Intégré au téléphone de bureau-1</span><span class="sxs-lookup"><span data-stu-id="57d9e-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d9e-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="57d9e-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="57d9e-250">type</span><span class="sxs-lookup"><span data-stu-id="57d9e-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="57d9e-251">Un ensemble de bits qui indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="57d9e-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="57d9e-252">Les définitions d’attribut suivantes apparaissent :</span><span class="sxs-lookup"><span data-stu-id="57d9e-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="57d9e-253">Nouvelle tentative de session-1</span><span class="sxs-lookup"><span data-stu-id="57d9e-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57d9e-254">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="57d9e-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="57d9e-255">S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="57d9e-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

