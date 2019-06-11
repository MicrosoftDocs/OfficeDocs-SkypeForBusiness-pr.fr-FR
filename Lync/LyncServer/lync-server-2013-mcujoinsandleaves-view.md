---
title: 'Affichage Lync Server 2013: McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c5dca-102">Affichage McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5dca-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5dca-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5dca-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5dca-104">Le mode McuJoinsAndLeaves stocke les informations sur les utilisateurs qui rejoignent et laissent des informations pour un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="c5dca-105">Chaque enregistrement de cette vue contient les détails de l’une des combinaisons d’un utilisateur qui rejoint ou quittent le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="c5dca-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5dca-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5dca-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="c5dca-107">Column</span></span></th>
<th><span data-ttu-id="c5dca-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="c5dca-108">Data Type</span></span></th>
<th><span data-ttu-id="c5dca-109">Détails</span><span class="sxs-lookup"><span data-stu-id="c5dca-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5dca-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dca-112">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-112">Time of conference instance.</span></span> <span data-ttu-id="c5dca-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c5dca-114">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-116">int</span><span class="sxs-lookup"><span data-stu-id="c5dca-116">int</span></span></p></td>
<td><p><span data-ttu-id="c5dca-117">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="c5dca-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c5dca-119">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5dca-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-122">URI du serveur de conférence auquel l’utilisateur s’est connecté.</span><span class="sxs-lookup"><span data-stu-id="c5dca-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5dca-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-125">URI du serveur de conférence auquel l’utilisateur s’est connecté.</span><span class="sxs-lookup"><span data-stu-id="c5dca-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="c5dca-126">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5dca-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-129">URI de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5dca-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-132">Le type d’URI de l’utilisateur dont le serveur de conférence a été capturé.</span><span class="sxs-lookup"><span data-stu-id="c5dca-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c5dca-133">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5dca-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-136">Le client de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c5dca-137">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5dca-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-140">La version du client utilisée par l’utilisateur dont les informations de jointure/de conservation du serveur de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="c5dca-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-142">int</span><span class="sxs-lookup"><span data-stu-id="c5dca-142">int</span></span></p></td>
<td><p><span data-ttu-id="c5dca-143">Le client utilisé par l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c5dca-144">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c5dca-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-147">Le nom de la catégorie du client utilisée par l’utilisateur dont les informations de jointure/conservation du serveur de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="c5dca-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-149">int</span><span class="sxs-lookup"><span data-stu-id="c5dca-149">int</span></span></p></td>
<td><p><span data-ttu-id="c5dca-150">Identifie de manière unique la combinaison utilisateur/appareil pour les utilisateurs connectés simultanément à plusieurs appareils.</span><span class="sxs-lookup"><span data-stu-id="c5dca-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-152">bit</span><span class="sxs-lookup"><span data-stu-id="c5dca-152">bit</span></span></p></td>
<td><p><span data-ttu-id="c5dca-153">Bit qui indique si l’utilisateur est ou non un utilisateur interne.</span><span class="sxs-lookup"><span data-stu-id="c5dca-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5dca-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dca-156">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="c5dca-156">Time of session request.</span></span> <span data-ttu-id="c5dca-157">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="c5dca-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c5dca-158">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-160">int</span><span class="sxs-lookup"><span data-stu-id="c5dca-160">int</span></span></p></td>
<td><p><span data-ttu-id="c5dca-161">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="c5dca-161">ID number to identify the session.</span></span> <span data-ttu-id="c5dca-162">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="c5dca-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c5dca-163">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dca-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c5dca-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c5dca-166">ID de la boîte de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="c5dca-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="c5dca-167">Le format est: boîte de dialogue; de-balise; à balise.</span><span class="sxs-lookup"><span data-stu-id="c5dca-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dca-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5dca-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dca-170">Temps pendant lequel l’utilisateur a rejoint le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dca-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dca-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dca-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c5dca-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dca-173">Temps pendant lequel l’utilisateur a quitté le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5dca-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

