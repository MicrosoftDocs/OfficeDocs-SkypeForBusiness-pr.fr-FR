---
title: 'Affichage Lync Server 2013 : McuJoinsAndLeaves'
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="8b912-102">Affichage McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b912-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b912-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8b912-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8b912-104">Le mode McuJoinsAndLeaves stocke les informations sur les utilisateurs qui rejoignent et laissent des informations pour un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="8b912-105">Chaque enregistrement de cette vue contient les détails de l’une des combinaisons d’un utilisateur qui rejoint ou quittent le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="8b912-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b912-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b912-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="8b912-107">Column</span></span></th>
<th><span data-ttu-id="8b912-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="8b912-108">Data Type</span></span></th>
<th><span data-ttu-id="8b912-109">Détails</span><span class="sxs-lookup"><span data-stu-id="8b912-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b912-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8b912-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b912-112">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-112">Time of conference instance.</span></span> <span data-ttu-id="8b912-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="8b912-114">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-116">int</span><span class="sxs-lookup"><span data-stu-id="8b912-116">int</span></span></p></td>
<td><p><span data-ttu-id="8b912-117">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="8b912-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="8b912-119">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b912-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8b912-122">URI du serveur de conférence auquel l’utilisateur s’est connecté.</span><span class="sxs-lookup"><span data-stu-id="8b912-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b912-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8b912-125">URI du serveur de conférence auquel l’utilisateur s’est connecté.</span><span class="sxs-lookup"><span data-stu-id="8b912-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="8b912-126">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8b912-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8b912-129">URI de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b912-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8b912-132">Le type d’URI de l’utilisateur dont le serveur de conférence a été capturé.</span><span class="sxs-lookup"><span data-stu-id="8b912-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="8b912-133">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b912-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8b912-136">Le client de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="8b912-137">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b912-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8b912-140">La version du client utilisée par l’utilisateur dont les informations de jointure/de conservation du serveur de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8b912-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-142">int</span><span class="sxs-lookup"><span data-stu-id="8b912-142">int</span></span></p></td>
<td><p><span data-ttu-id="8b912-143">Le client utilisé par l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="8b912-144">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8b912-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8b912-147">Le nom de la catégorie du client utilisée par l’utilisateur dont les informations de jointure/conservation du serveur de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8b912-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-149">int</span><span class="sxs-lookup"><span data-stu-id="8b912-149">int</span></span></p></td>
<td><p><span data-ttu-id="8b912-150">Identifie de manière unique la combinaison utilisateur/appareil pour les utilisateurs connectés simultanément à plusieurs appareils.</span><span class="sxs-lookup"><span data-stu-id="8b912-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-152">bit</span><span class="sxs-lookup"><span data-stu-id="8b912-152">bit</span></span></p></td>
<td><p><span data-ttu-id="8b912-153">Bit qui indique si l’utilisateur est ou non un utilisateur interne.</span><span class="sxs-lookup"><span data-stu-id="8b912-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8b912-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b912-156">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="8b912-156">Time of session request.</span></span> <span data-ttu-id="8b912-157">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="8b912-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="8b912-158">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-160">int</span><span class="sxs-lookup"><span data-stu-id="8b912-160">int</span></span></p></td>
<td><p><span data-ttu-id="8b912-161">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="8b912-161">ID number to identify the session.</span></span> <span data-ttu-id="8b912-162">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="8b912-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="8b912-163">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b912-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="8b912-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="8b912-166">ID de la boîte de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="8b912-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="8b912-167">Le format est : boîte de dialogue ; de-balise ; à balise.</span><span class="sxs-lookup"><span data-stu-id="8b912-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b912-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8b912-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b912-170">Temps pendant lequel l’utilisateur a rejoint le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b912-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="8b912-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8b912-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8b912-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b912-173">Temps pendant lequel l’utilisateur a quitté le serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b912-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

