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
ms.openlocfilehash: 3e991f6240d9c21815299a3ef169c5824cf5ef3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="188c8-102">Table ConferenceSessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="188c8-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="188c8-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="188c8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="188c8-104">Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.</span><span class="sxs-lookup"><span data-stu-id="188c8-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="188c8-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="188c8-105">Column</span></span></th>
<th><span data-ttu-id="188c8-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="188c8-106">Data Type</span></span></th>
<th><span data-ttu-id="188c8-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="188c8-107">Key/Index</span></span></th>
<th><span data-ttu-id="188c8-108">Détails</span><span class="sxs-lookup"><span data-stu-id="188c8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="188c8-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-110">Structure</span><span class="sxs-lookup"><span data-stu-id="188c8-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="188c8-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="188c8-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-112">Heure de la demande de session ; utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="188c8-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-115">int</span><span class="sxs-lookup"><span data-stu-id="188c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="188c8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-117">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-117">ID number to identify the session.</span></span> <span data-ttu-id="188c8-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="188c8-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="188c8-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-121">int</span><span class="sxs-lookup"><span data-stu-id="188c8-121">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-123">URI de conférence Focus associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="188c8-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="188c8-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="188c8-125">Il s’agit d’une URI de conférence Focus.</span><span class="sxs-lookup"><span data-stu-id="188c8-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-127">Unique</span><span class="sxs-lookup"><span data-stu-id="188c8-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-128">Identificateur permettant de différencier les instances des conférences périodiques.</span><span class="sxs-lookup"><span data-stu-id="188c8-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="188c8-129">Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="188c8-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="188c8-130">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="188c8-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-132">int</span><span class="sxs-lookup"><span data-stu-id="188c8-132">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-133">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-134">URI de conférence de serveur de conférence associée à cette session.</span><span class="sxs-lookup"><span data-stu-id="188c8-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="188c8-135">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="188c8-136">Il s’agit de l’URI de conférence basée sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="188c8-137">Pour les sessions de conférence Focus, cette colonne sera nulle.</span><span class="sxs-lookup"><span data-stu-id="188c8-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-139">int</span><span class="sxs-lookup"><span data-stu-id="188c8-139">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-140">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-141">ID d’un utilisateur dans la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-141">ID of one user in the conference session.</span></span> <span data-ttu-id="188c8-142">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-144">unique</span><span class="sxs-lookup"><span data-stu-id="188c8-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-p107">GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="188c8-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-148">int</span><span class="sxs-lookup"><span data-stu-id="188c8-148">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-149">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-150">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="188c8-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="188c8-151">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-153">int</span><span class="sxs-lookup"><span data-stu-id="188c8-153">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-154">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-155">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="188c8-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="188c8-156">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-158">int</span><span class="sxs-lookup"><span data-stu-id="188c8-158">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-160">Version de client utilisée par l’utilisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-160">Client version used by the conference user.</span></span> <span data-ttu-id="188c8-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-163">int</span><span class="sxs-lookup"><span data-stu-id="188c8-163">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-164">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-165">Version de client utilisée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-165">Client version used by the conference server.</span></span> <span data-ttu-id="188c8-166">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-168">DateHeure</span><span class="sxs-lookup"><span data-stu-id="188c8-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="188c8-169">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-170">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="188c8-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="188c8-171">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-173">int</span><span class="sxs-lookup"><span data-stu-id="188c8-173">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-175">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-175">ID number to identify the session.</span></span> <span data-ttu-id="188c8-176">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="188c8-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="188c8-177">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-179">légèrement</span><span class="sxs-lookup"><span data-stu-id="188c8-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-180">Indique si la session est démarrée par le serveur de conférence ?</span><span class="sxs-lookup"><span data-stu-id="188c8-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-182">légèrement</span><span class="sxs-lookup"><span data-stu-id="188c8-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-183">Indique si la session est terminée par le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="188c8-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-185">légèrement</span><span class="sxs-lookup"><span data-stu-id="188c8-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-186">Indique si l’utilisateur est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="188c8-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-188">int</span><span class="sxs-lookup"><span data-stu-id="188c8-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-189">Code de réponse SIP (Session Initiation Protocol) à l’invitation de session.</span><span class="sxs-lookup"><span data-stu-id="188c8-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="188c8-190">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="188c8-191">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="188c8-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-193">int</span><span class="sxs-lookup"><span data-stu-id="188c8-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-194">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="188c8-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-196">int</span><span class="sxs-lookup"><span data-stu-id="188c8-196">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-197">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-198">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="188c8-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="188c8-199">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-201">int</span><span class="sxs-lookup"><span data-stu-id="188c8-201">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-202">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-203">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="188c8-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="188c8-204">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-206">int</span><span class="sxs-lookup"><span data-stu-id="188c8-206">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-207">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-208">Serveur de médiation utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="188c8-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="188c8-209">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-211">int</span><span class="sxs-lookup"><span data-stu-id="188c8-211">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-212">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-213">Passerelle utilisée par l’appel.</span><span class="sxs-lookup"><span data-stu-id="188c8-213">The gateway the call is using.</span></span> <span data-ttu-id="188c8-214">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-216">int</span><span class="sxs-lookup"><span data-stu-id="188c8-216">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-217">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-218">Serveur Edge utilisé par l’appel.</span><span class="sxs-lookup"><span data-stu-id="188c8-218">The Edge Server the call is using.</span></span> <span data-ttu-id="188c8-219">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-221">int</span><span class="sxs-lookup"><span data-stu-id="188c8-221">int</span></span></p></td>
<td><p><span data-ttu-id="188c8-222">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-223">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-223">Content type used in the session.</span></span> <span data-ttu-id="188c8-224">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="188c8-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-226">DateHeure</span><span class="sxs-lookup"><span data-stu-id="188c8-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-p121">Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="188c8-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-231">DateHeure</span><span class="sxs-lookup"><span data-stu-id="188c8-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-232">Heure du premier message SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="188c8-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="188c8-233">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="188c8-234">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="188c8-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-236">DateHeure</span><span class="sxs-lookup"><span data-stu-id="188c8-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-237">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="188c8-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-239">entier très petit</span><span class="sxs-lookup"><span data-stu-id="188c8-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="188c8-240">Etranger</span><span class="sxs-lookup"><span data-stu-id="188c8-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="188c8-241">Contient la valeur du type d’URI MCU de la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="188c8-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="188c8-242">Ce champ sert à améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="188c8-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="188c8-243">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="188c8-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="188c8-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-245">type</span><span class="sxs-lookup"><span data-stu-id="188c8-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-p124">Jeu de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="188c8-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="188c8-248">Intégré avec téléphone de bureau - 1</span><span class="sxs-lookup"><span data-stu-id="188c8-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="188c8-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="188c8-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="188c8-250">type</span><span class="sxs-lookup"><span data-stu-id="188c8-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="188c8-p125">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="188c8-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="188c8-253">Nouvelle tentative de session - 1</span><span class="sxs-lookup"><span data-stu-id="188c8-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="188c8-254">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="188c8-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="188c8-255">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="188c8-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

