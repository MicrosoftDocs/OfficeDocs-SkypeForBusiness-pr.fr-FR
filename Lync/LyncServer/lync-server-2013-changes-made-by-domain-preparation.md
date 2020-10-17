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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529501"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="d4b39-102">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4b39-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b39-103">_**Dernière modification de la rubrique :** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="d4b39-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="d4b39-p101">Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="d4b39-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="d4b39-106">Entrées de contrôle d’accès ajoutées à la racine de domaine</span><span class="sxs-lookup"><span data-stu-id="d4b39-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="d4b39-107">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="d4b39-107">ACE</span></span></th>
<th><span data-ttu-id="d4b39-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d4b39-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d4b39-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d4b39-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="d4b39-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="d4b39-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="d4b39-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="d4b39-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="d4b39-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="d4b39-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-113">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="d4b39-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d4b39-114"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-116">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-116">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-117">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-117">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-118">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b39-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="d4b39-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d4b39-120"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-121">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-121">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-122">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-122">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-123">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-123">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-124">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="d4b39-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="d4b39-126"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-127">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-127">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-128">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-128">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-129">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-129">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-130">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b39-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="d4b39-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="d4b39-132"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-133">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-133">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-134">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-134">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-135">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-135">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-136">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="d4b39-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="d4b39-138"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-139">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-139">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-140">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-140">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-141">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-141">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-142">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b39-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d4b39-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d4b39-144"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-145">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-145">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-146">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-146">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-147">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-147">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-148"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d4b39-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d4b39-150"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-151">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-151">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-152">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-152">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-153">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-153">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-154">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b39-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="d4b39-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="d4b39-156">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-156">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-157">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-157">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-158"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-159">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-159">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-160">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d4b39-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d4b39-162">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-162">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-163">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-163">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-164"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-165">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-165">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-166">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b39-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d4b39-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d4b39-168">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-168">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-169">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-169">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-170"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-171">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-171">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-172">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-173">Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4b39-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="d4b39-174">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-174">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-175">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-175">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-176">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-176">No</span></span></p></td>
<td><p><span data-ttu-id="d4b39-177"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-178">Non</span><span class="sxs-lookup"><span data-stu-id="d4b39-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4b39-p102">Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="d4b39-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="d4b39-181">Entrées de contrôle d’accès ajoutées aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="d4b39-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4b39-182">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="d4b39-182">ACE</span></span></th>
<th><span data-ttu-id="d4b39-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d4b39-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d4b39-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d4b39-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4b39-185">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="d4b39-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d4b39-186"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d4b39-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="d4b39-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

