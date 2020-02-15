---
title: 'Lync Server 2013 : table ConferenceSessionDetails'
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
ms.openlocfilehash: 6c88cb167f334bc27148b16deafb0e7759105955
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="dce40-102">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce40-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dce40-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dce40-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dce40-104">Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="dce40-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dce40-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="dce40-105">Column</span></span></th>
<th><span data-ttu-id="dce40-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="dce40-106">Data Type</span></span></th>
<th><span data-ttu-id="dce40-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="dce40-107">Key/Index</span></span></th>
<th><span data-ttu-id="dce40-108">Détails</span><span class="sxs-lookup"><span data-stu-id="dce40-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dce40-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-110">Structure</span><span class="sxs-lookup"><span data-stu-id="dce40-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="dce40-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="dce40-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-112">Heure de la demande de session ; utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="dce40-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-115">int</span><span class="sxs-lookup"><span data-stu-id="dce40-115">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="dce40-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-117">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-117">ID number to identify the session.</span></span> <span data-ttu-id="dce40-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="dce40-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="dce40-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-121">int</span><span class="sxs-lookup"><span data-stu-id="dce40-121">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-123">URI de conférence Focus associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="dce40-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="dce40-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="dce40-125">Il s’agit d’une URI de conférence Focus.</span><span class="sxs-lookup"><span data-stu-id="dce40-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-127">Unique</span><span class="sxs-lookup"><span data-stu-id="dce40-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-128">Identificateur permettant de différencier les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="dce40-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="dce40-129">Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="dce40-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="dce40-130">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dce40-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-132">int</span><span class="sxs-lookup"><span data-stu-id="dce40-132">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-133">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-134">URI de conférence de serveur de conférence associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="dce40-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="dce40-135">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="dce40-136">Il s’agit de l’URI de conférence basée sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="dce40-137">Pour les sessions de conférence Focus, cette colonne sera nulle.</span><span class="sxs-lookup"><span data-stu-id="dce40-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-139">int</span><span class="sxs-lookup"><span data-stu-id="dce40-139">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-140">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-141">ID d’un utilisateur dans la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-141">ID of one user in the conference session.</span></span> <span data-ttu-id="dce40-142">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-144">unique</span><span class="sxs-lookup"><span data-stu-id="dce40-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-p107">GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="dce40-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-148">int</span><span class="sxs-lookup"><span data-stu-id="dce40-148">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-149">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-150">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="dce40-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="dce40-151">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-153">int</span><span class="sxs-lookup"><span data-stu-id="dce40-153">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-154">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-155">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="dce40-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="dce40-156">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-158">int</span><span class="sxs-lookup"><span data-stu-id="dce40-158">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-160">Version de client utilisée par l’utilisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-160">Client version used by the conference user.</span></span> <span data-ttu-id="dce40-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-163">int</span><span class="sxs-lookup"><span data-stu-id="dce40-163">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-164">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-165">Version de client utilisée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-165">Client version used by the conference server.</span></span> <span data-ttu-id="dce40-166">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-168">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dce40-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="dce40-169">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-170">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="dce40-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="dce40-171">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-173">int</span><span class="sxs-lookup"><span data-stu-id="dce40-173">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-175">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-175">ID number to identify the session.</span></span> <span data-ttu-id="dce40-176">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="dce40-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="dce40-177">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-179">légèrement</span><span class="sxs-lookup"><span data-stu-id="dce40-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-180">Indique si la session est démarrée par le serveur de conférence ?</span><span class="sxs-lookup"><span data-stu-id="dce40-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-182">légèrement</span><span class="sxs-lookup"><span data-stu-id="dce40-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-183">Indique si la session est terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="dce40-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-185">légèrement</span><span class="sxs-lookup"><span data-stu-id="dce40-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-186">Indique si l’utilisateur est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="dce40-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-188">int</span><span class="sxs-lookup"><span data-stu-id="dce40-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-189">Code de réponse SIP (Session Initiation Protocol) à l’invitation de session.</span><span class="sxs-lookup"><span data-stu-id="dce40-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="dce40-190">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dce40-191">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="dce40-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-193">int</span><span class="sxs-lookup"><span data-stu-id="dce40-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-194">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="dce40-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-196">int</span><span class="sxs-lookup"><span data-stu-id="dce40-196">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-197">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-198">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="dce40-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="dce40-199">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-201">int</span><span class="sxs-lookup"><span data-stu-id="dce40-201">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-202">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-203">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="dce40-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="dce40-204">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-206">int</span><span class="sxs-lookup"><span data-stu-id="dce40-206">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-207">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-208">Serveur de médiation utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="dce40-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="dce40-209">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-211">int</span><span class="sxs-lookup"><span data-stu-id="dce40-211">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-212">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-213">Passerelle utilisée par l’appel.</span><span class="sxs-lookup"><span data-stu-id="dce40-213">The gateway the call is using.</span></span> <span data-ttu-id="dce40-214">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-216">int</span><span class="sxs-lookup"><span data-stu-id="dce40-216">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-217">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-218">Serveur Edge utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="dce40-218">The Edge Server the call is using.</span></span> <span data-ttu-id="dce40-219">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-221">int</span><span class="sxs-lookup"><span data-stu-id="dce40-221">int</span></span></p></td>
<td><p><span data-ttu-id="dce40-222">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-223">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-223">Content type used in the session.</span></span> <span data-ttu-id="dce40-224">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dce40-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-226">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dce40-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-p121">Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="dce40-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dce40-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-232">Heure du premier message SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="dce40-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="dce40-233">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dce40-234">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="dce40-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dce40-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-237">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="dce40-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-239">entier très petit</span><span class="sxs-lookup"><span data-stu-id="dce40-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dce40-240">Etranger</span><span class="sxs-lookup"><span data-stu-id="dce40-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dce40-241">Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dce40-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="dce40-242">Ce champ sert à améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="dce40-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="dce40-243">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dce40-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dce40-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-245">type</span><span class="sxs-lookup"><span data-stu-id="dce40-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-p124">Jeu de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="dce40-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dce40-248">Intégré avec téléphone de bureau - 1</span><span class="sxs-lookup"><span data-stu-id="dce40-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dce40-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dce40-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dce40-250">type</span><span class="sxs-lookup"><span data-stu-id="dce40-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dce40-p125">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="dce40-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dce40-253">Nouvelle tentative de session - 1</span><span class="sxs-lookup"><span data-stu-id="dce40-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dce40-254">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="dce40-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="dce40-255">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="dce40-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

