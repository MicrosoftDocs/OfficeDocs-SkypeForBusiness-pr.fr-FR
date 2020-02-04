---
title: 'Lync Server 2013 : Table McuJoinsAndLeaves'
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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="b70d7-102">Table McuJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b70d7-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b70d7-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b70d7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b70d7-104">Chaque enregistrement de cette table contient les détails de l’appel d’une combinaison d’une jointure utilisateur ou d’un serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="b70d7-105">Par exemple, si un utilisateur rejoint une conférence incluant des conférences Web et des éléments audio ou vidéo, un enregistrement sera créé pour la participation à la conférence Web de cet utilisateur et un autre enregistrement serait créé pour la participation de l’utilisateur à la conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="b70d7-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b70d7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b70d7-106">Column</span></span></th>
<th><span data-ttu-id="b70d7-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="b70d7-107">Data Type</span></span></th>
<th><span data-ttu-id="b70d7-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="b70d7-108">Key/Index</span></span></th>
<th><span data-ttu-id="b70d7-109">Détails</span><span class="sxs-lookup"><span data-stu-id="b70d7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b70d7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b70d7-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-113">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-113">Time of conference instance.</span></span> <span data-ttu-id="b70d7-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b70d7-115">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-117">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-117">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-118">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b70d7-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-119">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="b70d7-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b70d7-121">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-123">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-123">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-124">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b70d7-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-125">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b70d7-125">Unique number identifying this user.</span></span> <span data-ttu-id="b70d7-126">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-128">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-128">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-129">Principal</span><span class="sxs-lookup"><span data-stu-id="b70d7-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="b70d7-130">Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, McuUserInstance identifie de façon unique la combinaison utilisateur/appareil.</span><span class="sxs-lookup"><span data-stu-id="b70d7-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-132">bit</span><span class="sxs-lookup"><span data-stu-id="b70d7-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b70d7-133">Le fait que l’utilisateur se connecte à partir d’un réseau PSTN ou non.</span><span class="sxs-lookup"><span data-stu-id="b70d7-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-135">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-135">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-136">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b70d7-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-137">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="b70d7-138">Pour plus d’informations, reportez-vous <a href="lync-server-2013-mcus-table.md">à la table MCU dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-140">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b70d7-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-141">Externes</span><span class="sxs-lookup"><span data-stu-id="b70d7-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-142">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="b70d7-142">Time of session request.</span></span> <span data-ttu-id="b70d7-143">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b70d7-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b70d7-144">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-146">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-146">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-147">Externes</span><span class="sxs-lookup"><span data-stu-id="b70d7-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-148">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="b70d7-148">ID number to identify the session.</span></span> <span data-ttu-id="b70d7-149">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b70d7-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b70d7-150">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-152">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b70d7-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b70d7-153">Heure à laquelle l’utilisateur rejoint ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-155">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b70d7-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b70d7-156">Heure à laquelle l’utilisateur quitte ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-158">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-158">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-159">Externes</span><span class="sxs-lookup"><span data-stu-id="b70d7-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b70d7-160">Identificateur spécifiant le numéro de version de l’utilisation du logiciel client dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="b70d7-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="b70d7-161">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b70d7-162">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b70d7-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

