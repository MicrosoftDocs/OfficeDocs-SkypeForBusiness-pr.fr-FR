---
title: 'Lync Server 2013 : vue FocusJoinsAndLeaves'
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
ms.openlocfilehash: 85e13c744ed92dcbcb70b2da851b915e8c6f8104
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="8cd3e-102">Vue FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cd3e-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd3e-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8cd3e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8cd3e-104">La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="8cd3e-105">Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="8cd3e-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cd3e-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="8cd3e-107">Column</span></span></th>
<th><span data-ttu-id="8cd3e-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="8cd3e-108">Data Type</span></span></th>
<th><span data-ttu-id="8cd3e-109">Détails</span><span class="sxs-lookup"><span data-stu-id="8cd3e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8cd3e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-112">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-112">Time of conference instance.</span></span> <span data-ttu-id="8cd3e-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="8cd3e-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-116">int</span><span class="sxs-lookup"><span data-stu-id="8cd3e-116">int</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-117">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="8cd3e-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="8cd3e-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-122">URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-125">Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="8cd3e-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-129">Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="8cd3e-130">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-132">unique</span><span class="sxs-lookup"><span data-stu-id="8cd3e-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-133">Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-136">Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-138">int</span><span class="sxs-lookup"><span data-stu-id="8cd3e-138">int</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-139">Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="8cd3e-140">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-143">Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-145">int</span><span class="sxs-lookup"><span data-stu-id="8cd3e-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-147">légèrement</span><span class="sxs-lookup"><span data-stu-id="8cd3e-147">bit</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-148">Bit qui indique si l’utilisateur est un utilisateur interne ou non.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-150">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8cd3e-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-151">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-151">Time of session request.</span></span> <span data-ttu-id="8cd3e-152">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="8cd3e-153">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8cd3e-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-155">int</span><span class="sxs-lookup"><span data-stu-id="8cd3e-155">int</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-156">Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-p108">ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-162">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8cd3e-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-163">Heure à laquelle cet utilisateur a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd3e-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-165">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8cd3e-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-166">Heure à laquelle cet utilisateur a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd3e-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="8cd3e-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd3e-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cd3e-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8cd3e-169">Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.</span><span class="sxs-lookup"><span data-stu-id="8cd3e-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

