---
title: 'Lync Server 2013 : modifications apportées par la préparation du domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="22489-102">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22489-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22489-103">_**Dernière modification de la rubrique :** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="22489-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="22489-p101">Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="22489-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="22489-106">Entrées de contrôle d’accès ajoutées à la racine de domaine</span><span class="sxs-lookup"><span data-stu-id="22489-106">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22489-107">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="22489-107">ACE</span></span></th>
<th><span data-ttu-id="22489-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="22489-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="22489-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="22489-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="22489-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="22489-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="22489-111">RTCHSUniversal-services</span><span class="sxs-lookup"><span data-stu-id="22489-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="22489-112">Utilisateurs authentifiés</span><span class="sxs-lookup"><span data-stu-id="22489-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22489-113">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="22489-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="22489-114"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-116">Non</span><span class="sxs-lookup"><span data-stu-id="22489-116">No</span></span></p></td>
<td><p><span data-ttu-id="22489-117">Non</span><span class="sxs-lookup"><span data-stu-id="22489-117">No</span></span></p></td>
<td><p><span data-ttu-id="22489-118">Non</span><span class="sxs-lookup"><span data-stu-id="22489-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22489-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="22489-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="22489-120"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-121">Non</span><span class="sxs-lookup"><span data-stu-id="22489-121">No</span></span></p></td>
<td><p><span data-ttu-id="22489-122">Non</span><span class="sxs-lookup"><span data-stu-id="22489-122">No</span></span></p></td>
<td><p><span data-ttu-id="22489-123">Non</span><span class="sxs-lookup"><span data-stu-id="22489-123">No</span></span></p></td>
<td><p><span data-ttu-id="22489-124">Non</span><span class="sxs-lookup"><span data-stu-id="22489-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22489-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="22489-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="22489-126"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-127">Non</span><span class="sxs-lookup"><span data-stu-id="22489-127">No</span></span></p></td>
<td><p><span data-ttu-id="22489-128">Non</span><span class="sxs-lookup"><span data-stu-id="22489-128">No</span></span></p></td>
<td><p><span data-ttu-id="22489-129">Non</span><span class="sxs-lookup"><span data-stu-id="22489-129">No</span></span></p></td>
<td><p><span data-ttu-id="22489-130">Non</span><span class="sxs-lookup"><span data-stu-id="22489-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22489-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="22489-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="22489-132"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-133">Non</span><span class="sxs-lookup"><span data-stu-id="22489-133">No</span></span></p></td>
<td><p><span data-ttu-id="22489-134">Non</span><span class="sxs-lookup"><span data-stu-id="22489-134">No</span></span></p></td>
<td><p><span data-ttu-id="22489-135">Non</span><span class="sxs-lookup"><span data-stu-id="22489-135">No</span></span></p></td>
<td><p><span data-ttu-id="22489-136">Non</span><span class="sxs-lookup"><span data-stu-id="22489-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22489-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="22489-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="22489-138"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-139">Non</span><span class="sxs-lookup"><span data-stu-id="22489-139">No</span></span></p></td>
<td><p><span data-ttu-id="22489-140">Non</span><span class="sxs-lookup"><span data-stu-id="22489-140">No</span></span></p></td>
<td><p><span data-ttu-id="22489-141">Non</span><span class="sxs-lookup"><span data-stu-id="22489-141">No</span></span></p></td>
<td><p><span data-ttu-id="22489-142">Non</span><span class="sxs-lookup"><span data-stu-id="22489-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22489-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="22489-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="22489-144"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-145">Non</span><span class="sxs-lookup"><span data-stu-id="22489-145">No</span></span></p></td>
<td><p><span data-ttu-id="22489-146">Non</span><span class="sxs-lookup"><span data-stu-id="22489-146">No</span></span></p></td>
<td><p><span data-ttu-id="22489-147">Non</span><span class="sxs-lookup"><span data-stu-id="22489-147">No</span></span></p></td>
<td><p><span data-ttu-id="22489-148"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22489-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="22489-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="22489-150"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-151">Non</span><span class="sxs-lookup"><span data-stu-id="22489-151">No</span></span></p></td>
<td><p><span data-ttu-id="22489-152">Non</span><span class="sxs-lookup"><span data-stu-id="22489-152">No</span></span></p></td>
<td><p><span data-ttu-id="22489-153">Non</span><span class="sxs-lookup"><span data-stu-id="22489-153">No</span></span></p></td>
<td><p><span data-ttu-id="22489-154">Non</span><span class="sxs-lookup"><span data-stu-id="22489-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22489-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="22489-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="22489-156">Non</span><span class="sxs-lookup"><span data-stu-id="22489-156">No</span></span></p></td>
<td><p><span data-ttu-id="22489-157">Non</span><span class="sxs-lookup"><span data-stu-id="22489-157">No</span></span></p></td>
<td><p><span data-ttu-id="22489-158"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-159">Non</span><span class="sxs-lookup"><span data-stu-id="22489-159">No</span></span></p></td>
<td><p><span data-ttu-id="22489-160">Non</span><span class="sxs-lookup"><span data-stu-id="22489-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22489-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="22489-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="22489-162">Non</span><span class="sxs-lookup"><span data-stu-id="22489-162">No</span></span></p></td>
<td><p><span data-ttu-id="22489-163">Non</span><span class="sxs-lookup"><span data-stu-id="22489-163">No</span></span></p></td>
<td><p><span data-ttu-id="22489-164"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-165">Non</span><span class="sxs-lookup"><span data-stu-id="22489-165">No</span></span></p></td>
<td><p><span data-ttu-id="22489-166">Non</span><span class="sxs-lookup"><span data-stu-id="22489-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22489-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="22489-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="22489-168">Non</span><span class="sxs-lookup"><span data-stu-id="22489-168">No</span></span></p></td>
<td><p><span data-ttu-id="22489-169">Non</span><span class="sxs-lookup"><span data-stu-id="22489-169">No</span></span></p></td>
<td><p><span data-ttu-id="22489-170"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-171">Non</span><span class="sxs-lookup"><span data-stu-id="22489-171">No</span></span></p></td>
<td><p><span data-ttu-id="22489-172">Non</span><span class="sxs-lookup"><span data-stu-id="22489-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22489-173">Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="22489-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="22489-174">Non</span><span class="sxs-lookup"><span data-stu-id="22489-174">No</span></span></p></td>
<td><p><span data-ttu-id="22489-175">Non</span><span class="sxs-lookup"><span data-stu-id="22489-175">No</span></span></p></td>
<td><p><span data-ttu-id="22489-176">Non</span><span class="sxs-lookup"><span data-stu-id="22489-176">No</span></span></p></td>
<td><p><span data-ttu-id="22489-177"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-178">Non</span><span class="sxs-lookup"><span data-stu-id="22489-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="22489-p102">Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="22489-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="22489-181">Entrées de contrôle d’accès ajoutées aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="22489-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22489-182">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="22489-182">ACE</span></span></th>
<th><span data-ttu-id="22489-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="22489-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="22489-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="22489-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22489-185">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="22489-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="22489-186"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="22489-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="22489-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

