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
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="8546b-102">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8546b-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8546b-103">_**Dernière modification de la rubrique :** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="8546b-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="8546b-p101">Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="8546b-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="8546b-106">Entrées de contrôle d’accès ajoutées à la racine de domaine</span><span class="sxs-lookup"><span data-stu-id="8546b-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="8546b-107">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="8546b-107">ACE</span></span></th>
<th><span data-ttu-id="8546b-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8546b-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="8546b-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8546b-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="8546b-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="8546b-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="8546b-111">RTCHSUniversal-services</span><span class="sxs-lookup"><span data-stu-id="8546b-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="8546b-112">Utilisateurs authentifiés</span><span class="sxs-lookup"><span data-stu-id="8546b-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8546b-113">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="8546b-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="8546b-114"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-116">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-116">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-117">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-117">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-118">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546b-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8546b-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8546b-120"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-121">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-121">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-122">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-122">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-123">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-123">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-124">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8546b-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="8546b-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="8546b-126"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-127">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-127">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-128">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-128">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-129">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-129">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-130">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546b-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="8546b-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="8546b-132"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-133">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-133">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-134">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-134">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-135">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-135">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-136">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8546b-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="8546b-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="8546b-138"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-139">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-139">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-140">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-140">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-141">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-141">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-142">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546b-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="8546b-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="8546b-144"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-145">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-145">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-146">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-146">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-147">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-147">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-148"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8546b-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8546b-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="8546b-150"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-151">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-151">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-152">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-152">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-153">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-153">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-154">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546b-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="8546b-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="8546b-156">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-156">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-157">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-157">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-158"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-159">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-159">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-160">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8546b-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="8546b-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="8546b-162">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-162">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-163">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-163">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-164"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-165">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-165">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-166">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546b-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8546b-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="8546b-168">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-168">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-169">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-169">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-170"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-171">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-171">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-172">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8546b-173">Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="8546b-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="8546b-174">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-174">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-175">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-175">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-176">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-176">No</span></span></p></td>
<td><p><span data-ttu-id="8546b-177"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-178">Non</span><span class="sxs-lookup"><span data-stu-id="8546b-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8546b-p102">Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="8546b-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="8546b-181">Entrées de contrôle d’accès ajoutées aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="8546b-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8546b-182">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="8546b-182">ACE</span></span></th>
<th><span data-ttu-id="8546b-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8546b-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="8546b-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8546b-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8546b-185">Read Container (non héritée)</span><span class="sxs-lookup"><span data-stu-id="8546b-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="8546b-186"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8546b-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="8546b-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

