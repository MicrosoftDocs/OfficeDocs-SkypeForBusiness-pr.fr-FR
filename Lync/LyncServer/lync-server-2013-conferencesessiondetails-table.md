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
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="5ae04-102">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ae04-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ae04-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5ae04-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5ae04-104">Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ae04-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ae04-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="5ae04-105">Column</span></span></th>
<th><span data-ttu-id="5ae04-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="5ae04-106">Data Type</span></span></th>
<th><span data-ttu-id="5ae04-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="5ae04-107">Key/Index</span></span></th>
<th><span data-ttu-id="5ae04-108">Détails</span><span class="sxs-lookup"><span data-stu-id="5ae04-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-110">Structure</span><span class="sxs-lookup"><span data-stu-id="5ae04-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="5ae04-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="5ae04-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-112">Heure de la demande de session ; utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5ae04-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-115">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-115">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="5ae04-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-117">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-117">ID number to identify the session.</span></span> <span data-ttu-id="5ae04-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="5ae04-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5ae04-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-121">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-121">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-123">URI de conférence Focus associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="5ae04-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5ae04-125">Il s’agit d’une URI de conférence Focus.</span><span class="sxs-lookup"><span data-stu-id="5ae04-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-127">Unique</span><span class="sxs-lookup"><span data-stu-id="5ae04-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-128">Identificateur permettant de différencier les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="5ae04-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="5ae04-129">Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="5ae04-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="5ae04-130">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ae04-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-132">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-132">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-133">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-134">URI de conférence de serveur de conférence associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="5ae04-135">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5ae04-136">Il s’agit de l’URI de conférence basée sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="5ae04-137">Pour les sessions de conférence Focus, cette colonne sera nulle.</span><span class="sxs-lookup"><span data-stu-id="5ae04-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-139">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-139">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-140">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-141">ID d’un utilisateur dans la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-141">ID of one user in the conference session.</span></span> <span data-ttu-id="5ae04-142">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-144">unique</span><span class="sxs-lookup"><span data-stu-id="5ae04-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-p107">GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="5ae04-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-148">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-148">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-149">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-150">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="5ae04-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="5ae04-151">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-153">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-153">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-154">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-155">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="5ae04-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="5ae04-156">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-158">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-158">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-160">Version de client utilisée par l’utilisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-160">Client version used by the conference user.</span></span> <span data-ttu-id="5ae04-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-163">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-163">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-164">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-165">Version de client utilisée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-165">Client version used by the conference server.</span></span> <span data-ttu-id="5ae04-166">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-168">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5ae04-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ae04-169">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-170">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="5ae04-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5ae04-171">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-173">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-173">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-175">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-175">ID number to identify the session.</span></span> <span data-ttu-id="5ae04-176">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5ae04-177">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-179">légèrement</span><span class="sxs-lookup"><span data-stu-id="5ae04-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-180">Indique si la session est démarrée par le serveur de conférence ?</span><span class="sxs-lookup"><span data-stu-id="5ae04-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-182">légèrement</span><span class="sxs-lookup"><span data-stu-id="5ae04-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-183">Indique si la session est terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="5ae04-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-185">légèrement</span><span class="sxs-lookup"><span data-stu-id="5ae04-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-186">Indique si l’utilisateur est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="5ae04-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-188">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-189">Code de réponse SIP (Session Initiation Protocol) à l’invitation de session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="5ae04-190">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5ae04-191">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="5ae04-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-193">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-194">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="5ae04-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-196">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-196">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-197">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-198">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="5ae04-199">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-201">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-201">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-202">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-203">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="5ae04-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="5ae04-204">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-206">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-206">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-207">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-208">Serveur de médiation utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="5ae04-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="5ae04-209">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-211">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-211">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-212">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-213">Passerelle utilisée par l’appel.</span><span class="sxs-lookup"><span data-stu-id="5ae04-213">The gateway the call is using.</span></span> <span data-ttu-id="5ae04-214">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-216">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-216">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-217">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-218">Serveur Edge utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="5ae04-218">The Edge Server the call is using.</span></span> <span data-ttu-id="5ae04-219">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-221">int</span><span class="sxs-lookup"><span data-stu-id="5ae04-221">int</span></span></p></td>
<td><p><span data-ttu-id="5ae04-222">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-223">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-223">Content type used in the session.</span></span> <span data-ttu-id="5ae04-224">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ae04-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-226">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5ae04-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-p121">Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="5ae04-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5ae04-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-232">Heure du premier message SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="5ae04-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="5ae04-233">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5ae04-234">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="5ae04-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5ae04-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-237">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="5ae04-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-239">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5ae04-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5ae04-240">Etranger</span><span class="sxs-lookup"><span data-stu-id="5ae04-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ae04-241">Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ae04-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="5ae04-242">Ce champ sert à améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="5ae04-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="5ae04-243">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ae04-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ae04-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-245">type</span><span class="sxs-lookup"><span data-stu-id="5ae04-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-p124">Jeu de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="5ae04-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ae04-248">Intégré avec téléphone de bureau - 1</span><span class="sxs-lookup"><span data-stu-id="5ae04-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ae04-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5ae04-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5ae04-250">type</span><span class="sxs-lookup"><span data-stu-id="5ae04-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ae04-p125">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="5ae04-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ae04-253">Nouvelle tentative de session - 1</span><span class="sxs-lookup"><span data-stu-id="5ae04-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5ae04-254">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="5ae04-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="5ae04-255">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="5ae04-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

