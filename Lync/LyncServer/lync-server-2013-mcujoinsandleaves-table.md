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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524731"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="28803-102">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28803-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28803-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="28803-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="28803-104">Chaque enregistrement de cette table contient des détails sur une combinaison d’un utilisateur JOIN ou Leave et d’un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="28803-105">Par exemple, si un utilisateur rejoint une conférence qui comprend des éléments audio/vidéo et de conférence Web, un enregistrement est créé pour la jointure de conférence Web de cet utilisateur, et un autre enregistrement est créé pour la jointure audio/vidéo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28803-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28803-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="28803-106">Column</span></span></th>
<th><span data-ttu-id="28803-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="28803-107">Data Type</span></span></th>
<th><span data-ttu-id="28803-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="28803-108">Key/Index</span></span></th>
<th><span data-ttu-id="28803-109">Détails</span><span class="sxs-lookup"><span data-stu-id="28803-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28803-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="28803-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28803-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="28803-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="28803-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-113">Time of conference instance.</span></span> <span data-ttu-id="28803-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="28803-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="28803-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28803-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="28803-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-117">int</span><span class="sxs-lookup"><span data-stu-id="28803-117">int</span></span></p></td>
<td><p><span data-ttu-id="28803-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="28803-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-119">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="28803-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="28803-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="28803-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28803-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="28803-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-123">int</span><span class="sxs-lookup"><span data-stu-id="28803-123">int</span></span></p></td>
<td><p><span data-ttu-id="28803-124">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="28803-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-125">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28803-125">Unique number identifying this user.</span></span> <span data-ttu-id="28803-126">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28803-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="28803-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-128">int</span><span class="sxs-lookup"><span data-stu-id="28803-128">int</span></span></p></td>
<td><p><span data-ttu-id="28803-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="28803-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="28803-130">Si un utilisateur a ouvert une session sur plusieurs ordinateurs ou périphériques à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="28803-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28803-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="28803-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-132">légèrement</span><span class="sxs-lookup"><span data-stu-id="28803-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28803-133">Si l’utilisateur rejoint à partir d’un RTC ou non.</span><span class="sxs-lookup"><span data-stu-id="28803-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28803-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="28803-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-135">int</span><span class="sxs-lookup"><span data-stu-id="28803-135">int</span></span></p></td>
<td><p><span data-ttu-id="28803-136">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="28803-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-137">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="28803-138">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mcus-table.md">table MCU de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28803-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="28803-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-140">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28803-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="28803-141">Etranger</span><span class="sxs-lookup"><span data-stu-id="28803-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-142">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="28803-142">Time of session request.</span></span> <span data-ttu-id="28803-143">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="28803-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="28803-144">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28803-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="28803-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-146">int</span><span class="sxs-lookup"><span data-stu-id="28803-146">int</span></span></p></td>
<td><p><span data-ttu-id="28803-147">Etranger</span><span class="sxs-lookup"><span data-stu-id="28803-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-148">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="28803-148">ID number to identify the session.</span></span> <span data-ttu-id="28803-149">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="28803-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="28803-150">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28803-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="28803-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-152">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28803-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28803-153">Heure à laquelle cet utilisateur rejoint ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28803-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="28803-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28803-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="28803-156">Heure à laquelle cet utilisateur quitte ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28803-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="28803-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="28803-158">int</span><span class="sxs-lookup"><span data-stu-id="28803-158">int</span></span></p></td>
<td><p><span data-ttu-id="28803-159">Etranger</span><span class="sxs-lookup"><span data-stu-id="28803-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="28803-160">Identificateur qui spécifie le numéro de version de l’utilisation du logiciel client dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="28803-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="28803-161">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="28803-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="28803-162">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28803-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

