---
title: 'Lync Server 2013 : table McuJoinsAndLeaves'
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
ms.openlocfilehash: a398c0b860cd5b4043ee766b702b1b7e8e904552
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="687f0-102">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="687f0-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="687f0-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="687f0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="687f0-104">Chaque enregistrement de cette table contient des détails sur une combinaison d’un utilisateur JOIN ou Leave et d’un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="687f0-105">Par exemple, si un utilisateur rejoint une conférence qui comprend des éléments audio/vidéo et de conférence Web, un enregistrement est créé pour la jointure de conférence Web de cet utilisateur, et un autre enregistrement est créé pour la jointure audio/vidéo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="687f0-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="687f0-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="687f0-106">Column</span></span></th>
<th><span data-ttu-id="687f0-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="687f0-107">Data Type</span></span></th>
<th><span data-ttu-id="687f0-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="687f0-108">Key/Index</span></span></th>
<th><span data-ttu-id="687f0-109">Détails</span><span class="sxs-lookup"><span data-stu-id="687f0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="687f0-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="687f0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="687f0-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="687f0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-113">Time of conference instance.</span></span> <span data-ttu-id="687f0-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="687f0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="687f0-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="687f0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-117">int</span><span class="sxs-lookup"><span data-stu-id="687f0-117">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="687f0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-119">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="687f0-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="687f0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="687f0-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="687f0-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-123">int</span><span class="sxs-lookup"><span data-stu-id="687f0-123">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-124">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="687f0-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-125">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="687f0-125">Unique number identifying this user.</span></span> <span data-ttu-id="687f0-126">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="687f0-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-128">int</span><span class="sxs-lookup"><span data-stu-id="687f0-128">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="687f0-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="687f0-130">Si un utilisateur a ouvert une session sur plusieurs ordinateurs ou périphériques à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="687f0-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="687f0-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-132">légèrement</span><span class="sxs-lookup"><span data-stu-id="687f0-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="687f0-133">Si l’utilisateur rejoint à partir d’un RTC ou non.</span><span class="sxs-lookup"><span data-stu-id="687f0-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="687f0-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-135">int</span><span class="sxs-lookup"><span data-stu-id="687f0-135">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-136">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="687f0-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-137">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="687f0-138">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mcus-table.md">table MCU de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="687f0-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-140">DateHeure</span><span class="sxs-lookup"><span data-stu-id="687f0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="687f0-141">Etranger</span><span class="sxs-lookup"><span data-stu-id="687f0-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-142">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="687f0-142">Time of session request.</span></span> <span data-ttu-id="687f0-143">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="687f0-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="687f0-144">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="687f0-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-146">int</span><span class="sxs-lookup"><span data-stu-id="687f0-146">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-147">Etranger</span><span class="sxs-lookup"><span data-stu-id="687f0-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-148">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="687f0-148">ID number to identify the session.</span></span> <span data-ttu-id="687f0-149">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="687f0-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="687f0-150">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="687f0-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-152">DateHeure</span><span class="sxs-lookup"><span data-stu-id="687f0-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="687f0-153">Heure à laquelle cet utilisateur rejoint ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="687f0-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="687f0-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="687f0-156">Heure à laquelle cet utilisateur quitte ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="687f0-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="687f0-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="687f0-158">int</span><span class="sxs-lookup"><span data-stu-id="687f0-158">int</span></span></p></td>
<td><p><span data-ttu-id="687f0-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="687f0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="687f0-160">Identificateur qui spécifie le numéro de version de l’utilisation du logiciel client dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="687f0-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="687f0-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="687f0-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="687f0-162">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="687f0-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

