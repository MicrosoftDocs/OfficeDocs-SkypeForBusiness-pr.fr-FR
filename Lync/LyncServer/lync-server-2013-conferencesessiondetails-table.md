---
title: 'Lync Server 2013 : table ConferenceSessionDetails'
description: 'Lync Server 2013 : table ConferenceSessionDetails.'
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
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566780"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="3f6ca-103">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f6ca-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f6ca-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f6ca-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f6ca-105">Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f6ca-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3f6ca-106">Column</span></span></th>
<th><span data-ttu-id="3f6ca-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="3f6ca-107">Data Type</span></span></th>
<th><span data-ttu-id="3f6ca-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="3f6ca-108">Key/Index</span></span></th>
<th><span data-ttu-id="3f6ca-109">Détails</span><span class="sxs-lookup"><span data-stu-id="3f6ca-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-111">Structure</span><span class="sxs-lookup"><span data-stu-id="3f6ca-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="3f6ca-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-113">Heure de la demande de session ; utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="3f6ca-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-116">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-116">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="3f6ca-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-118">ID number to identify the session.</span></span> <span data-ttu-id="3f6ca-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="3f6ca-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-122">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-122">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-124">URI de conférence Focus associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="3f6ca-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="3f6ca-126">Il s’agit d’une URI de conférence Focus.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-128">Unique</span><span class="sxs-lookup"><span data-stu-id="3f6ca-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-129">Identificateur permettant de différencier les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="3f6ca-130">Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="3f6ca-131">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-133">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-133">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-134">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-135">URI de conférence de serveur de conférence associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="3f6ca-136">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="3f6ca-137">Il s’agit de l’URI de conférence basée sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="3f6ca-138">Pour les sessions de conférence Focus, cette colonne sera nulle.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-140">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-140">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-141">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-142">ID d’un utilisateur dans la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-142">ID of one user in the conference session.</span></span> <span data-ttu-id="3f6ca-143">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-145">unique</span><span class="sxs-lookup"><span data-stu-id="3f6ca-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-p107">GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-149">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-149">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-150">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-151">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="3f6ca-152">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-154">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-154">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-155">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-156">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="3f6ca-157">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-159">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-159">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-160">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-161">Version de client utilisée par l’utilisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-161">Client version used by the conference user.</span></span> <span data-ttu-id="3f6ca-162">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-164">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-164">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-165">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-166">Version de client utilisée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-166">Client version used by the conference server.</span></span> <span data-ttu-id="3f6ca-167">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3f6ca-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-170">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-171">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="3f6ca-172">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-174">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-174">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-175">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-176">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-176">ID number to identify the session.</span></span> <span data-ttu-id="3f6ca-177">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="3f6ca-178">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-180">légèrement</span><span class="sxs-lookup"><span data-stu-id="3f6ca-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-181">Indique si la session est démarrée par le serveur de conférence ?</span><span class="sxs-lookup"><span data-stu-id="3f6ca-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-183">légèrement</span><span class="sxs-lookup"><span data-stu-id="3f6ca-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-184">Indique si la session est terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-186">légèrement</span><span class="sxs-lookup"><span data-stu-id="3f6ca-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-187">Indique si l’utilisateur est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-189">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-190">Code de réponse SIP (Session Initiation Protocol) à l’invitation de session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="3f6ca-191">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3f6ca-192">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="3f6ca-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-194">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-195">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-197">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-197">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-198">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-199">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="3f6ca-200">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-202">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-202">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-203">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-204">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="3f6ca-205">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-207">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-207">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-208">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-209">Serveur de médiation utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="3f6ca-210">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-212">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-212">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-213">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-214">Passerelle utilisée par l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-214">The gateway the call is using.</span></span> <span data-ttu-id="3f6ca-215">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-217">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-217">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-218">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-219">Serveur Edge utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-219">The Edge Server the call is using.</span></span> <span data-ttu-id="3f6ca-220">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-222">int</span><span class="sxs-lookup"><span data-stu-id="3f6ca-222">int</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-223">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-224">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-224">Content type used in the session.</span></span> <span data-ttu-id="3f6ca-225">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3f6ca-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-227">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3f6ca-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-p121">Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="3f6ca-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-232">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3f6ca-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-233">Heure du premier message SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="3f6ca-234">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3f6ca-235">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="3f6ca-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-237">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3f6ca-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-238">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-240">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3f6ca-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-241">Etranger</span><span class="sxs-lookup"><span data-stu-id="3f6ca-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f6ca-242">Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3f6ca-243">Ce champ sert à améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="3f6ca-244">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ca-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-246">type</span><span class="sxs-lookup"><span data-stu-id="3f6ca-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-p124">Jeu de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="3f6ca-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f6ca-249">Intégré avec téléphone de bureau - 1</span><span class="sxs-lookup"><span data-stu-id="3f6ca-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ca-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3f6ca-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3f6ca-251">type</span><span class="sxs-lookup"><span data-stu-id="3f6ca-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f6ca-p125">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="3f6ca-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f6ca-254">Nouvelle tentative de session - 1</span><span class="sxs-lookup"><span data-stu-id="3f6ca-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f6ca-255">\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="3f6ca-256">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

