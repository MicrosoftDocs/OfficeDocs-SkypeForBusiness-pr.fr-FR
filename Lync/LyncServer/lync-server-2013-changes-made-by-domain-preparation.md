---
title: 'Lync Server 2013 : modifications apportées par la préparation du domaine'
description: 'Lync Server 2013 : modifications apportées par la préparation du domaine.'
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
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543690"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="f3984-103">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3984-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3984-104">_**Dernière modification de la rubrique :** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="f3984-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="f3984-p101">Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="f3984-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="f3984-107">Entrées de contrôle d’accès ajoutées à la racine de domaine</span><span class="sxs-lookup"><span data-stu-id="f3984-107">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="f3984-108">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="f3984-108">ACE</span></span></th>
<th><span data-ttu-id="f3984-109">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="f3984-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="f3984-110">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="f3984-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="f3984-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="f3984-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="f3984-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="f3984-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="f3984-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="f3984-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3984-114">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="f3984-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="f3984-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-116"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-117">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-117">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-118">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-118">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-119">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3984-120">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="f3984-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f3984-121"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-122">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-122">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-123">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-123">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-124">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-124">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-125">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3984-126">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="f3984-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="f3984-127"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-128">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-128">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-129">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-129">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-130">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-130">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-131">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3984-132">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="f3984-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="f3984-133"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-134">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-134">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-135">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-135">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-136">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-136">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-137">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3984-138">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="f3984-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="f3984-139"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-140">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-140">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-141">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-141">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-142">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-142">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-143">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3984-144">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="f3984-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="f3984-145"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-146">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-146">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-147">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-147">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-148">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-148">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-149"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3984-150">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f3984-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="f3984-151"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-152">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-152">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-153">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-153">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-154">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-154">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-155">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3984-156">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="f3984-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="f3984-157">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-157">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-158">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-158">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-159"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-160">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-160">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-161">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3984-162">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="f3984-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="f3984-163">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-163">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-164">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-164">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-165"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-166">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-166">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-167">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3984-168">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f3984-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="f3984-169">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-169">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-170">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-170">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-171"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-172">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-172">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-173">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3984-174">Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="f3984-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="f3984-175">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-175">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-176">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-176">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-177">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-177">No</span></span></p></td>
<td><p><span data-ttu-id="f3984-178"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-179">Non</span><span class="sxs-lookup"><span data-stu-id="f3984-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f3984-p102">Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="f3984-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="f3984-182">Entrées de contrôle d’accès ajoutées aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="f3984-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3984-183">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="f3984-183">ACE</span></span></th>
<th><span data-ttu-id="f3984-184">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="f3984-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="f3984-185">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="f3984-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3984-186">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="f3984-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="f3984-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="f3984-188"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="f3984-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

