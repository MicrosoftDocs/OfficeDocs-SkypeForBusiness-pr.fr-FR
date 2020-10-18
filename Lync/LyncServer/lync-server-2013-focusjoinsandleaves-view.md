---
title: 'Lync Server 2013 : vue FocusJoinsAndLeaves'
description: 'Lync Server 2013 : vue FocusJoinsAndLeaves.'
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
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577450"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="36757-103">Vue FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36757-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36757-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="36757-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="36757-105">La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon.</span><span class="sxs-lookup"><span data-stu-id="36757-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="36757-106">Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="36757-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36757-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36757-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="36757-108">Column</span></span></th>
<th><span data-ttu-id="36757-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="36757-109">Data Type</span></span></th>
<th><span data-ttu-id="36757-110">Détails</span><span class="sxs-lookup"><span data-stu-id="36757-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36757-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="36757-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="36757-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="36757-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-113">Time of conference instance.</span></span> <span data-ttu-id="36757-114">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="36757-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="36757-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-117">int</span><span class="sxs-lookup"><span data-stu-id="36757-117">int</span></span></p></td>
<td><p><span data-ttu-id="36757-118">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="36757-119">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="36757-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="36757-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="36757-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="36757-123">URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="36757-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36757-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36757-126">Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="36757-127">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="36757-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36757-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36757-130">Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="36757-131">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="36757-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-133">unique</span><span class="sxs-lookup"><span data-stu-id="36757-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="36757-134">Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="36757-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36757-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36757-137">Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="36757-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-139">int</span><span class="sxs-lookup"><span data-stu-id="36757-139">int</span></span></p></td>
<td><p><span data-ttu-id="36757-140">Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="36757-141">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="36757-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="36757-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="36757-144">Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="36757-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="36757-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-146">int</span><span class="sxs-lookup"><span data-stu-id="36757-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="36757-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-148">légèrement</span><span class="sxs-lookup"><span data-stu-id="36757-148">bit</span></span></p></td>
<td><p><span data-ttu-id="36757-149">Bit qui indique si l’utilisateur est un utilisateur interne ou non.</span><span class="sxs-lookup"><span data-stu-id="36757-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="36757-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-151">DateHeure</span><span class="sxs-lookup"><span data-stu-id="36757-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="36757-152">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="36757-152">Time of session request.</span></span> <span data-ttu-id="36757-153">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="36757-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="36757-154">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36757-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="36757-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-156">int</span><span class="sxs-lookup"><span data-stu-id="36757-156">int</span></span></p></td>
<td><p><span data-ttu-id="36757-157">Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="36757-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="36757-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="36757-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="36757-p108">ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.</span><span class="sxs-lookup"><span data-stu-id="36757-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="36757-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-163">DateHeure</span><span class="sxs-lookup"><span data-stu-id="36757-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="36757-164">Heure à laquelle cet utilisateur a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36757-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="36757-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-166">DateHeure</span><span class="sxs-lookup"><span data-stu-id="36757-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="36757-167">Heure à laquelle cet utilisateur a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="36757-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36757-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="36757-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="36757-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36757-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36757-170">Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.</span><span class="sxs-lookup"><span data-stu-id="36757-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

