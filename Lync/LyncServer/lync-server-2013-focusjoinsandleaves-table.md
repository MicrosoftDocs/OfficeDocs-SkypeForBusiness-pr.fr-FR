---
title: 'Lync Server 2013 : Table FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e8bd6-102">Table FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8bd6-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8bd6-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e8bd6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e8bd6-104">Chaque enregistrement de cette table contient les informations CDR relatives à la jointure d’un utilisateur et laisse des informations pour une seule conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="e8bd6-105">Chaque conférence est représentée dans ce tableau par un seul enregistrement pour chaque fois qu’un utilisateur rejoint et quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8bd6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e8bd6-106">Column</span></span></th>
<th><span data-ttu-id="e8bd6-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="e8bd6-107">Data Type</span></span></th>
<th><span data-ttu-id="e8bd6-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="e8bd6-108">Key/Index</span></span></th>
<th><span data-ttu-id="e8bd6-109">Détails</span><span class="sxs-lookup"><span data-stu-id="e8bd6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e8bd6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e8bd6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-113">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-113">Time of conference instance.</span></span> <span data-ttu-id="e8bd6-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e8bd6-115">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8bd6-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-117">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-117">int</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-118">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e8bd6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-119">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="e8bd6-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e8bd6-121">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8bd6-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e8bd6-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-124">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e8bd6-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-125">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-125">Time of session request.</span></span> <span data-ttu-id="e8bd6-126">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e8bd6-127">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8bd6-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-129">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-129">int</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-130">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="e8bd6-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-131">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-131">ID number to identify the session.</span></span> <span data-ttu-id="e8bd6-132">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e8bd6-133">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e8bd6-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-135">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-135">int</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-136">Externes</span><span class="sxs-lookup"><span data-stu-id="e8bd6-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-137">Numéro unique identifiant cet utilisateur, référencé dans la <a href="lync-server-2013-users-table.md">table utilisateurs de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-139">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8bd6-140">Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, <strong>UserInstance</strong> est utilisé pour identifier de façon unique la combinaison utilisateur/appareil.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-142">bit</span><span class="sxs-lookup"><span data-stu-id="e8bd6-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8bd6-143">Si l’utilisateur s’est connecté à partir d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-144"><strong>Rôleutilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-145">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8bd6-146">Le rôle de cet utilisateur dans la Conférence, comme le présentateur ou le participant.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-148">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e8bd6-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8bd6-149">Heure à laquelle l’utilisateur rejoint la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-151">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e8bd6-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8bd6-152">Heure à laquelle l’utilisateur quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8bd6-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-154">int</span><span class="sxs-lookup"><span data-stu-id="e8bd6-154">int</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-155">Externes</span><span class="sxs-lookup"><span data-stu-id="e8bd6-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e8bd6-156">Version du logiciel client de l’utilisateur, référencée dans la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8bd6-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e8bd6-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8bd6-158">Identificateur</span><span class="sxs-lookup"><span data-stu-id="e8bd6-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8bd6-159">Identifiant unique global (GUID) du point de terminaison utilisé dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="e8bd6-160">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8bd6-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

