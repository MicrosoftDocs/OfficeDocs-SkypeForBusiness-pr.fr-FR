---
title: 'Affichage Lync Server 2013 : FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="33a4d-102">Affichage FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33a4d-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a4d-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="33a4d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="33a4d-104">Le mode FocusJoinsAndLeaves stocke des informations sur la participation et la conservation des informations pour une conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="33a4d-105">Chaque conférence est représentée dans cette vue par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="33a4d-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33a4d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33a4d-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="33a4d-107">Column</span></span></th>
<th><span data-ttu-id="33a4d-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="33a4d-108">Data Type</span></span></th>
<th><span data-ttu-id="33a4d-109">Détails</span><span class="sxs-lookup"><span data-stu-id="33a4d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="33a4d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="33a4d-112">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-112">Time of conference instance.</span></span> <span data-ttu-id="33a4d-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="33a4d-114">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-116">int</span><span class="sxs-lookup"><span data-stu-id="33a4d-116">int</span></span></p></td>
<td><p><span data-ttu-id="33a4d-117">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="33a4d-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="33a4d-119">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="33a4d-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-122">URI de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33a4d-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-125">Type d’URI de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="33a4d-126">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33a4d-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-129">Client de l’utilisateur qui a capturé des informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="33a4d-130">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-132">identificateur</span><span class="sxs-lookup"><span data-stu-id="33a4d-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="33a4d-133">Identificateur unique de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33a4d-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-136">Version du client utilisée par l’utilisateur et qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-138">int</span><span class="sxs-lookup"><span data-stu-id="33a4d-138">int</span></span></p></td>
<td><p><span data-ttu-id="33a4d-139">Client utilisé par l’utilisateur et qui a capturé des informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="33a4d-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="33a4d-140">Pour plus d’informations, voir <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="33a4d-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-143">Nom de la catégorie du client utilisée par l’utilisateur et ayant capturé des informations de conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-145">int</span><span class="sxs-lookup"><span data-stu-id="33a4d-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-147">bit</span><span class="sxs-lookup"><span data-stu-id="33a4d-147">bit</span></span></p></td>
<td><p><span data-ttu-id="33a4d-148">Bit qui indique si l’utilisateur est ou non un utilisateur interne.</span><span class="sxs-lookup"><span data-stu-id="33a4d-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-150">DateHeure</span><span class="sxs-lookup"><span data-stu-id="33a4d-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="33a4d-151">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="33a4d-151">Time of session request.</span></span> <span data-ttu-id="33a4d-152">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="33a4d-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="33a4d-153">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33a4d-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-155">int</span><span class="sxs-lookup"><span data-stu-id="33a4d-155">int</span></span></p></td>
<td><p><span data-ttu-id="33a4d-156">Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, UserInstance est utilisé pour identifier de façon unique la combinaison utilisateur/appareil.</span><span class="sxs-lookup"><span data-stu-id="33a4d-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="33a4d-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-159">ID de la boîte de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="33a4d-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="33a4d-160">Le format est : boîte de dialogue ; de-balise ; à balise.</span><span class="sxs-lookup"><span data-stu-id="33a4d-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-162">DateHeure</span><span class="sxs-lookup"><span data-stu-id="33a4d-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="33a4d-163">Temps pendant lequel l’utilisateur a rejoint la Conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a4d-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-165">DateHeure</span><span class="sxs-lookup"><span data-stu-id="33a4d-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="33a4d-166">Temps pendant lequel l’utilisateur a quitté la Conférence.</span><span class="sxs-lookup"><span data-stu-id="33a4d-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a4d-167"><strong>Rôleutilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="33a4d-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="33a4d-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33a4d-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="33a4d-169">Le rôle de l’utilisateur dans la Conférence, tel que le présentateur ou le participant.</span><span class="sxs-lookup"><span data-stu-id="33a4d-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

