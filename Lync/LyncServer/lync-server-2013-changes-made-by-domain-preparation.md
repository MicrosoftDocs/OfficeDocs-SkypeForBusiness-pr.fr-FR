---
title: 'Lync Server 2013: modifications apportées par la préparation du domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="134af-102">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="134af-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="134af-103">_**Dernière modification de la rubrique:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="134af-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="134af-104">Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) créées par la préparation du domaine à la racine du domaine.</span><span class="sxs-lookup"><span data-stu-id="134af-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="134af-105">Toutes les entrées ACE sont héritées sauf mention contraire.</span><span class="sxs-lookup"><span data-stu-id="134af-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="134af-106">ACE ajoutés à la racine du domaine</span><span class="sxs-lookup"><span data-stu-id="134af-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="134af-107">MAILLOTS</span><span class="sxs-lookup"><span data-stu-id="134af-107">ACE</span></span></th>
<th><span data-ttu-id="134af-108">RTCUniversal-UserReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="134af-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="134af-109">RTCUniversal-ServerReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="134af-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="134af-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="134af-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="134af-111">RTCHSUniversal-services</span><span class="sxs-lookup"><span data-stu-id="134af-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="134af-112">Utilisateurs authentifiés</span><span class="sxs-lookup"><span data-stu-id="134af-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="134af-113">Lire le conteneur (non hérité)</span><span class="sxs-lookup"><span data-stu-id="134af-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="134af-114"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-116">Non</span><span class="sxs-lookup"><span data-stu-id="134af-116">No</span></span></p></td>
<td><p><span data-ttu-id="134af-117">Non</span><span class="sxs-lookup"><span data-stu-id="134af-117">No</span></span></p></td>
<td><p><span data-ttu-id="134af-118">Non</span><span class="sxs-lookup"><span data-stu-id="134af-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134af-119">Lire User PropertySet-compte-restrictions</span><span class="sxs-lookup"><span data-stu-id="134af-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="134af-120"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-121">Non</span><span class="sxs-lookup"><span data-stu-id="134af-121">No</span></span></p></td>
<td><p><span data-ttu-id="134af-122">Non</span><span class="sxs-lookup"><span data-stu-id="134af-122">No</span></span></p></td>
<td><p><span data-ttu-id="134af-123">Non</span><span class="sxs-lookup"><span data-stu-id="134af-123">No</span></span></p></td>
<td><p><span data-ttu-id="134af-124">Non</span><span class="sxs-lookup"><span data-stu-id="134af-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134af-125">Lire Personal User PropertySet-informations</span><span class="sxs-lookup"><span data-stu-id="134af-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="134af-126"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-127">Non</span><span class="sxs-lookup"><span data-stu-id="134af-127">No</span></span></p></td>
<td><p><span data-ttu-id="134af-128">Non</span><span class="sxs-lookup"><span data-stu-id="134af-128">No</span></span></p></td>
<td><p><span data-ttu-id="134af-129">Non</span><span class="sxs-lookup"><span data-stu-id="134af-129">No</span></span></p></td>
<td><p><span data-ttu-id="134af-130">Non</span><span class="sxs-lookup"><span data-stu-id="134af-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134af-131">Lecture générale de User PropertySet-informations</span><span class="sxs-lookup"><span data-stu-id="134af-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="134af-132"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-133">Non</span><span class="sxs-lookup"><span data-stu-id="134af-133">No</span></span></p></td>
<td><p><span data-ttu-id="134af-134">Non</span><span class="sxs-lookup"><span data-stu-id="134af-134">No</span></span></p></td>
<td><p><span data-ttu-id="134af-135">Non</span><span class="sxs-lookup"><span data-stu-id="134af-135">No</span></span></p></td>
<td><p><span data-ttu-id="134af-136">Non</span><span class="sxs-lookup"><span data-stu-id="134af-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134af-137">Lire le public user PropertySet public-information</span><span class="sxs-lookup"><span data-stu-id="134af-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="134af-138"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-139">Non</span><span class="sxs-lookup"><span data-stu-id="134af-139">No</span></span></p></td>
<td><p><span data-ttu-id="134af-140">Non</span><span class="sxs-lookup"><span data-stu-id="134af-140">No</span></span></p></td>
<td><p><span data-ttu-id="134af-141">Non</span><span class="sxs-lookup"><span data-stu-id="134af-141">No</span></span></p></td>
<td><p><span data-ttu-id="134af-142">Non</span><span class="sxs-lookup"><span data-stu-id="134af-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134af-143">Lecture utilisateur PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="134af-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="134af-144"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-145">Non</span><span class="sxs-lookup"><span data-stu-id="134af-145">No</span></span></p></td>
<td><p><span data-ttu-id="134af-146">Non</span><span class="sxs-lookup"><span data-stu-id="134af-146">No</span></span></p></td>
<td><p><span data-ttu-id="134af-147">Non</span><span class="sxs-lookup"><span data-stu-id="134af-147">No</span></span></p></td>
<td><p><span data-ttu-id="134af-148"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134af-149">Lire User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="134af-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="134af-150"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-151">Non</span><span class="sxs-lookup"><span data-stu-id="134af-151">No</span></span></p></td>
<td><p><span data-ttu-id="134af-152">Non</span><span class="sxs-lookup"><span data-stu-id="134af-152">No</span></span></p></td>
<td><p><span data-ttu-id="134af-153">Non</span><span class="sxs-lookup"><span data-stu-id="134af-153">No</span></span></p></td>
<td><p><span data-ttu-id="134af-154">Non</span><span class="sxs-lookup"><span data-stu-id="134af-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134af-155">Écrire les adresses proxy de propriété utilisateur</span><span class="sxs-lookup"><span data-stu-id="134af-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="134af-156">Non</span><span class="sxs-lookup"><span data-stu-id="134af-156">No</span></span></p></td>
<td><p><span data-ttu-id="134af-157">Non</span><span class="sxs-lookup"><span data-stu-id="134af-157">No</span></span></p></td>
<td><p><span data-ttu-id="134af-158"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="134af-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-159">Non</span><span class="sxs-lookup"><span data-stu-id="134af-159">No</span></span></p></td>
<td><p><span data-ttu-id="134af-160">Non</span><span class="sxs-lookup"><span data-stu-id="134af-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134af-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="134af-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="134af-162">Non</span><span class="sxs-lookup"><span data-stu-id="134af-162">No</span></span></p></td>
<td><p><span data-ttu-id="134af-163">Non</span><span class="sxs-lookup"><span data-stu-id="134af-163">No</span></span></p></td>
<td><p><span data-ttu-id="134af-164"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="134af-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-165">Non</span><span class="sxs-lookup"><span data-stu-id="134af-165">No</span></span></p></td>
<td><p><span data-ttu-id="134af-166">Non</span><span class="sxs-lookup"><span data-stu-id="134af-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134af-167">Écrire RTCPropertySet utilisateur</span><span class="sxs-lookup"><span data-stu-id="134af-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="134af-168">Non</span><span class="sxs-lookup"><span data-stu-id="134af-168">No</span></span></p></td>
<td><p><span data-ttu-id="134af-169">Non</span><span class="sxs-lookup"><span data-stu-id="134af-169">No</span></span></p></td>
<td><p><span data-ttu-id="134af-170"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="134af-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-171">Non</span><span class="sxs-lookup"><span data-stu-id="134af-171">No</span></span></p></td>
<td><p><span data-ttu-id="134af-172">Non</span><span class="sxs-lookup"><span data-stu-id="134af-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134af-173">Lecture de PropertySet DS-réplication-obtention-modification de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="134af-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="134af-174">Non</span><span class="sxs-lookup"><span data-stu-id="134af-174">No</span></span></p></td>
<td><p><span data-ttu-id="134af-175">Non</span><span class="sxs-lookup"><span data-stu-id="134af-175">No</span></span></p></td>
<td><p><span data-ttu-id="134af-176">Non</span><span class="sxs-lookup"><span data-stu-id="134af-176">No</span></span></p></td>
<td><p><span data-ttu-id="134af-177"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="134af-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-178">Non</span><span class="sxs-lookup"><span data-stu-id="134af-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="134af-179">Le tableau suivant répertorie les entrées de contrôle d’accès qu’il est créé dans les trois conteneurs intégrés: utilisateurs, ordinateurs et contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="134af-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="134af-180">Toutes les entrées ACE sont héritées sauf mention contraire.</span><span class="sxs-lookup"><span data-stu-id="134af-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="134af-181">ACE ajoutés aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="134af-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="134af-182">MAILLOTS</span><span class="sxs-lookup"><span data-stu-id="134af-182">ACE</span></span></th>
<th><span data-ttu-id="134af-183">RTCUniversal-UserReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="134af-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="134af-184">RTCUniversal-ServerReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="134af-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="134af-185">Lire le conteneur (non hérité)</span><span class="sxs-lookup"><span data-stu-id="134af-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="134af-186"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="134af-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="134af-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

