---
title: 'Lync Server 2013 : table FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500831"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="8dd9f-102">Table FocusJoinsAndLeaves dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd9f-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd9f-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8dd9f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8dd9f-104">Chaque enregistrement de cette table contient des informations sur les détails des appels de la part d’un utilisateur et laisse des informations sur une conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="8dd9f-105">Chaque conférence est représentée dans ce tableau par un enregistrement pour chaque fois qu’un utilisateur rejoint et quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dd9f-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="8dd9f-106">Column</span></span></th>
<th><span data-ttu-id="8dd9f-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="8dd9f-107">Data Type</span></span></th>
<th><span data-ttu-id="8dd9f-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="8dd9f-108">Key/Index</span></span></th>
<th><span data-ttu-id="8dd9f-109">Détails</span><span class="sxs-lookup"><span data-stu-id="8dd9f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8dd9f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8dd9f-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-113">Time of conference instance.</span></span> <span data-ttu-id="8dd9f-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8dd9f-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8dd9f-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-117">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-117">int</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8dd9f-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-119">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="8dd9f-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8dd9f-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8dd9f-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8dd9f-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-124">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8dd9f-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-125">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-125">Time of session request.</span></span> <span data-ttu-id="8dd9f-126">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8dd9f-127">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8dd9f-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-129">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-129">int</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-130">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8dd9f-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-131">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-131">ID number to identify the session.</span></span> <span data-ttu-id="8dd9f-132">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8dd9f-133">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8dd9f-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-135">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-135">int</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-136">Etranger</span><span class="sxs-lookup"><span data-stu-id="8dd9f-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-137">Numéro unique identifiant cet utilisateur, référencé à partir de la <a href="lync-server-2013-users-table.md">table users dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-139">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8dd9f-140">Si un utilisateur a ouvert une session sur plusieurs ordinateurs ou appareils en même temps, <strong>colonne UserInstance</strong> est utilisé pour identifier de manière unique la combinaison utilisateur/périphérique.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-142">légèrement</span><span class="sxs-lookup"><span data-stu-id="8dd9f-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8dd9f-143">Si l’utilisateur s’est connecté en interne ou non.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-145">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8dd9f-146">Rôle de cet utilisateur dans la Conférence, tel que présentateur ou participant.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-148">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8dd9f-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8dd9f-149">Heure à laquelle cet utilisateur rejoint la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-151">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8dd9f-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8dd9f-152">Heure à laquelle cet utilisateur quitte la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd9f-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-154">int</span><span class="sxs-lookup"><span data-stu-id="8dd9f-154">int</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-155">Etranger</span><span class="sxs-lookup"><span data-stu-id="8dd9f-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd9f-156">Version du logiciel client de l’utilisateur, référencée dans la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd9f-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="8dd9f-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd9f-158">Unique</span><span class="sxs-lookup"><span data-stu-id="8dd9f-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8dd9f-159">Identificateur global unique (GUID) du point de terminaison utilisé dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="8dd9f-160">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

