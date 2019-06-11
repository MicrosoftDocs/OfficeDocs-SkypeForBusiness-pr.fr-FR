---
title: 'Affichage Lync Server 2013: FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="abaf2-102">Affichage FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abaf2-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abaf2-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="abaf2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="abaf2-104">Le mode FocusJoinsAndLeaves stocke des informations sur la participation et la conservation des informations pour une conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="abaf2-105">Chaque conférence est représentée dans cette vue par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="abaf2-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abaf2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abaf2-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="abaf2-107">Column</span></span></th>
<th><span data-ttu-id="abaf2-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="abaf2-108">Data Type</span></span></th>
<th><span data-ttu-id="abaf2-109">Détails</span><span class="sxs-lookup"><span data-stu-id="abaf2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="abaf2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="abaf2-112">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-112">Time of conference instance.</span></span> <span data-ttu-id="abaf2-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="abaf2-114">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-116">int</span><span class="sxs-lookup"><span data-stu-id="abaf2-116">int</span></span></p></td>
<td><p><span data-ttu-id="abaf2-117">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="abaf2-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="abaf2-119">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="abaf2-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-122">URI de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abaf2-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-125">Type d’URI de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="abaf2-126">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abaf2-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-129">Client de l’utilisateur qui a capturé des informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="abaf2-130">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-132">identificateur</span><span class="sxs-lookup"><span data-stu-id="abaf2-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="abaf2-133">Identificateur unique de l’utilisateur qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abaf2-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-136">Version du client utilisée par l’utilisateur et qui a capturé les informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-138">int</span><span class="sxs-lookup"><span data-stu-id="abaf2-138">int</span></span></p></td>
<td><p><span data-ttu-id="abaf2-139">Client utilisé par l’utilisateur et qui a capturé des informations de conférence jointes.</span><span class="sxs-lookup"><span data-stu-id="abaf2-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="abaf2-140">Pour plus d’informations, voir <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="abaf2-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-143">Nom de la catégorie du client utilisée par l’utilisateur et ayant capturé des informations de conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-145">int</span><span class="sxs-lookup"><span data-stu-id="abaf2-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-147">bit</span><span class="sxs-lookup"><span data-stu-id="abaf2-147">bit</span></span></p></td>
<td><p><span data-ttu-id="abaf2-148">Bit qui indique si l’utilisateur est ou non un utilisateur interne.</span><span class="sxs-lookup"><span data-stu-id="abaf2-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-150">DateHeure</span><span class="sxs-lookup"><span data-stu-id="abaf2-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="abaf2-151">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="abaf2-151">Time of session request.</span></span> <span data-ttu-id="abaf2-152">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="abaf2-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="abaf2-153">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="abaf2-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-155">int</span><span class="sxs-lookup"><span data-stu-id="abaf2-155">int</span></span></p></td>
<td><p><span data-ttu-id="abaf2-156">Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, UserInstance est utilisé pour identifier de façon unique la combinaison utilisateur/appareil.</span><span class="sxs-lookup"><span data-stu-id="abaf2-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="abaf2-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-159">ID de la boîte de dialogue SIP de la session.</span><span class="sxs-lookup"><span data-stu-id="abaf2-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="abaf2-160">Le format est: boîte de dialogue; de-balise; à balise.</span><span class="sxs-lookup"><span data-stu-id="abaf2-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-162">DateHeure</span><span class="sxs-lookup"><span data-stu-id="abaf2-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="abaf2-163">Temps pendant lequel l’utilisateur a rejoint la Conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abaf2-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-165">DateHeure</span><span class="sxs-lookup"><span data-stu-id="abaf2-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="abaf2-166">Temps pendant lequel l’utilisateur a quitté la Conférence.</span><span class="sxs-lookup"><span data-stu-id="abaf2-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abaf2-167"><strong>Rôleutilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="abaf2-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="abaf2-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="abaf2-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abaf2-169">Le rôle de l’utilisateur dans la Conférence, tel que le présentateur ou le participant.</span><span class="sxs-lookup"><span data-stu-id="abaf2-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

