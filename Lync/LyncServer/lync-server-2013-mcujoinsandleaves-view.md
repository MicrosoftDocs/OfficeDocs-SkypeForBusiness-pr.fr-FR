---
title: 'Lync Server 2013 : vue McuJoinsAndLeaves'
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
ms.openlocfilehash: 329396549a02a354939b166c8785b875faee2f78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524721"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="82331-102">Vue McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82331-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82331-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="82331-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="82331-104">La vue McuJoinsAndLeaves stocke des informations sur la participation ou l’arrêt de la participation des utilisateurs pour un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="82331-105">Chaque enregistrement de cette vue contient les détails des appels sur la participation ou l’arrêt de la participation d’un utilisateur à une conférence, ainsi que sur le serveur de conférence concerné.</span><span class="sxs-lookup"><span data-stu-id="82331-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="82331-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82331-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82331-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="82331-107">Column</span></span></th>
<th><span data-ttu-id="82331-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="82331-108">Data Type</span></span></th>
<th><span data-ttu-id="82331-109">Détails</span><span class="sxs-lookup"><span data-stu-id="82331-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82331-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="82331-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="82331-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="82331-112">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-112">Time of conference instance.</span></span> <span data-ttu-id="82331-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="82331-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="82331-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-116">int</span><span class="sxs-lookup"><span data-stu-id="82331-116">int</span></span></p></td>
<td><p><span data-ttu-id="82331-117">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="82331-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="82331-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="82331-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82331-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82331-122">URI du serveur de conférence auquel s’est connecté l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82331-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="82331-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82331-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82331-125">URI du serveur de conférence auquel s’est connecté l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82331-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="82331-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="82331-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82331-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82331-129">URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="82331-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82331-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82331-132">Type d’URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="82331-133">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="82331-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82331-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82331-136">Client de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="82331-137">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="82331-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82331-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82331-140">Version du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="82331-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-142">int</span><span class="sxs-lookup"><span data-stu-id="82331-142">int</span></span></p></td>
<td><p><span data-ttu-id="82331-143">Client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="82331-144">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="82331-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="82331-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="82331-147">Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="82331-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-149">int</span><span class="sxs-lookup"><span data-stu-id="82331-149">int</span></span></p></td>
<td><p><span data-ttu-id="82331-150">Identifie de manière unique la combinaison utilisateur/périphérique pour les utilisateurs connectés simultanément à plusieurs périphériques.</span><span class="sxs-lookup"><span data-stu-id="82331-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="82331-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-152">légèrement</span><span class="sxs-lookup"><span data-stu-id="82331-152">bit</span></span></p></td>
<td><p><span data-ttu-id="82331-153">Bit qui indique si l’utilisateur est un utilisateur interne ou non.</span><span class="sxs-lookup"><span data-stu-id="82331-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="82331-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="82331-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="82331-156">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="82331-156">Time of session request.</span></span> <span data-ttu-id="82331-157">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="82331-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="82331-158">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="82331-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-160">int</span><span class="sxs-lookup"><span data-stu-id="82331-160">int</span></span></p></td>
<td><p><span data-ttu-id="82331-161">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="82331-161">ID number to identify the session.</span></span> <span data-ttu-id="82331-162">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="82331-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="82331-163">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82331-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="82331-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="82331-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="82331-p110">ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.</span><span class="sxs-lookup"><span data-stu-id="82331-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82331-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="82331-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="82331-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="82331-170">Heure à laquelle l’utilisateur a joint le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82331-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="82331-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82331-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="82331-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="82331-173">Heure à laquelle l’utilisateur a quitté le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="82331-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

