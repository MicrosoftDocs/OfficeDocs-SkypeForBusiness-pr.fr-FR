---
title: 'Lync Server 2013 : table McuJoinsAndLeaves'
description: 'Lync Server 2013 : table McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556500"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="b0aaa-103">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0aaa-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0aaa-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b0aaa-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b0aaa-105">Chaque enregistrement de cette table contient des détails sur une combinaison d’un utilisateur JOIN ou Leave et d’un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="b0aaa-106">Par exemple, si un utilisateur rejoint une conférence qui comprend des éléments audio/vidéo et de conférence Web, un enregistrement est créé pour la jointure de conférence Web de cet utilisateur, et un autre enregistrement est créé pour la jointure audio/vidéo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0aaa-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="b0aaa-107">Column</span></span></th>
<th><span data-ttu-id="b0aaa-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="b0aaa-108">Data Type</span></span></th>
<th><span data-ttu-id="b0aaa-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="b0aaa-109">Key/Index</span></span></th>
<th><span data-ttu-id="b0aaa-110">Détails</span><span class="sxs-lookup"><span data-stu-id="b0aaa-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0aaa-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b0aaa-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-114">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-114">Time of conference instance.</span></span> <span data-ttu-id="b0aaa-115">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b0aaa-116">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aaa-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-118">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-118">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b0aaa-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-120">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="b0aaa-121">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b0aaa-122">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-124">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-124">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-125">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b0aaa-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-126">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-126">Unique number identifying this user.</span></span> <span data-ttu-id="b0aaa-127">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aaa-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-129">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-129">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="b0aaa-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-131">Si un utilisateur a ouvert une session sur plusieurs ordinateurs ou périphériques à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-133">légèrement</span><span class="sxs-lookup"><span data-stu-id="b0aaa-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0aaa-134">Si l’utilisateur rejoint à partir d’un RTC ou non.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aaa-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-136">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-136">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-137">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b0aaa-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-138">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="b0aaa-139">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mcus-table.md">table MCU de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-141">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0aaa-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-142">Etranger</span><span class="sxs-lookup"><span data-stu-id="b0aaa-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-143">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-143">Time of session request.</span></span> <span data-ttu-id="b0aaa-144">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b0aaa-145">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aaa-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-147">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-147">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-148">Etranger</span><span class="sxs-lookup"><span data-stu-id="b0aaa-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-149">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-149">ID number to identify the session.</span></span> <span data-ttu-id="b0aaa-150">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b0aaa-151">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-153">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0aaa-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0aaa-154">Heure à laquelle cet utilisateur rejoint ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aaa-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-156">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0aaa-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0aaa-157">Heure à laquelle cet utilisateur quitte ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aaa-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="b0aaa-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0aaa-159">int</span><span class="sxs-lookup"><span data-stu-id="b0aaa-159">int</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-160">Etranger</span><span class="sxs-lookup"><span data-stu-id="b0aaa-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0aaa-161">Identificateur qui spécifie le numéro de version de l’utilisation du logiciel client dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="b0aaa-162">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b0aaa-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b0aaa-163">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0aaa-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

