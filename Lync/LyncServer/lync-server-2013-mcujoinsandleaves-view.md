---
title: 'Lync Server 2013 : vue McuJoinsAndLeaves'
description: 'Lync Server 2013 : vue McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556490"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c4426-103">Vue McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4426-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4426-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c4426-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c4426-105">La vue McuJoinsAndLeaves stocke des informations sur la participation ou l’arrêt de la participation des utilisateurs pour un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="c4426-106">Chaque enregistrement de cette vue contient les détails des appels sur la participation ou l’arrêt de la participation d’un utilisateur à une conférence, ainsi que sur le serveur de conférence concerné.</span><span class="sxs-lookup"><span data-stu-id="c4426-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="c4426-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4426-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4426-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="c4426-108">Column</span></span></th>
<th><span data-ttu-id="c4426-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="c4426-109">Data Type</span></span></th>
<th><span data-ttu-id="c4426-110">Détails</span><span class="sxs-lookup"><span data-stu-id="c4426-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4426-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c4426-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4426-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-113">Time of conference instance.</span></span> <span data-ttu-id="c4426-114">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c4426-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-117">int</span><span class="sxs-lookup"><span data-stu-id="c4426-117">int</span></span></p></td>
<td><p><span data-ttu-id="c4426-118">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="c4426-119">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c4426-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4426-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4426-123">URI du serveur de conférence auquel s’est connecté l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c4426-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4426-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4426-126">URI du serveur de conférence auquel s’est connecté l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c4426-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="c4426-127">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c4426-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c4426-130">URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4426-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4426-133">Type d’URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4426-134">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4426-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4426-137">Client de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4426-138">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4426-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4426-141">Version du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-143">int</span><span class="sxs-lookup"><span data-stu-id="c4426-143">int</span></span></p></td>
<td><p><span data-ttu-id="c4426-144">Client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c4426-145">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c4426-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c4426-148">Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-150">int</span><span class="sxs-lookup"><span data-stu-id="c4426-150">int</span></span></p></td>
<td><p><span data-ttu-id="c4426-151">Identifie de manière unique la combinaison utilisateur/périphérique pour les utilisateurs connectés simultanément à plusieurs périphériques.</span><span class="sxs-lookup"><span data-stu-id="c4426-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-153">légèrement</span><span class="sxs-lookup"><span data-stu-id="c4426-153">bit</span></span></p></td>
<td><p><span data-ttu-id="c4426-154">Bit qui indique si l’utilisateur est un utilisateur interne ou non.</span><span class="sxs-lookup"><span data-stu-id="c4426-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-156">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c4426-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4426-157">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="c4426-157">Time of session request.</span></span> <span data-ttu-id="c4426-158">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="c4426-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c4426-159">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-161">int</span><span class="sxs-lookup"><span data-stu-id="c4426-161">int</span></span></p></td>
<td><p><span data-ttu-id="c4426-162">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="c4426-162">ID number to identify the session.</span></span> <span data-ttu-id="c4426-163">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="c4426-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c4426-164">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c4426-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c4426-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c4426-p110">ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.</span><span class="sxs-lookup"><span data-stu-id="c4426-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4426-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-170">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c4426-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4426-171">Heure à laquelle l’utilisateur a joint le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4426-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="c4426-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c4426-173">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c4426-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="c4426-174">Heure à laquelle l’utilisateur a quitté le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4426-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

