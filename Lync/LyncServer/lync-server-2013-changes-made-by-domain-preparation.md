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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="97383-102">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97383-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97383-103">_**Dernière modification de la rubrique :** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="97383-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="97383-104">Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) créées par la préparation du domaine à la racine du domaine.</span><span class="sxs-lookup"><span data-stu-id="97383-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="97383-105">Toutes les entrées ACE sont héritées sauf mention contraire.</span><span class="sxs-lookup"><span data-stu-id="97383-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="97383-106">ACE ajoutés à la racine du domaine</span><span class="sxs-lookup"><span data-stu-id="97383-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="97383-107">MAILLOTS</span><span class="sxs-lookup"><span data-stu-id="97383-107">ACE</span></span></th>
<th><span data-ttu-id="97383-108">RTCUniversal-UserReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="97383-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="97383-109">RTCUniversal-ServerReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="97383-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="97383-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="97383-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="97383-111">RTCHSUniversal-services</span><span class="sxs-lookup"><span data-stu-id="97383-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="97383-112">Utilisateurs authentifiés</span><span class="sxs-lookup"><span data-stu-id="97383-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97383-113">Lire le conteneur (non hérité)</span><span class="sxs-lookup"><span data-stu-id="97383-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="97383-114"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="97383-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-115"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-116">Non</span><span class="sxs-lookup"><span data-stu-id="97383-116">No</span></span></p></td>
<td><p><span data-ttu-id="97383-117">Non</span><span class="sxs-lookup"><span data-stu-id="97383-117">No</span></span></p></td>
<td><p><span data-ttu-id="97383-118">Non</span><span class="sxs-lookup"><span data-stu-id="97383-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97383-119">Lire User PropertySet-compte-restrictions</span><span class="sxs-lookup"><span data-stu-id="97383-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="97383-120"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-121">Non</span><span class="sxs-lookup"><span data-stu-id="97383-121">No</span></span></p></td>
<td><p><span data-ttu-id="97383-122">Non</span><span class="sxs-lookup"><span data-stu-id="97383-122">No</span></span></p></td>
<td><p><span data-ttu-id="97383-123">Non</span><span class="sxs-lookup"><span data-stu-id="97383-123">No</span></span></p></td>
<td><p><span data-ttu-id="97383-124">Non</span><span class="sxs-lookup"><span data-stu-id="97383-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97383-125">Lire Personal User PropertySet-informations</span><span class="sxs-lookup"><span data-stu-id="97383-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="97383-126"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-127">Non</span><span class="sxs-lookup"><span data-stu-id="97383-127">No</span></span></p></td>
<td><p><span data-ttu-id="97383-128">Non</span><span class="sxs-lookup"><span data-stu-id="97383-128">No</span></span></p></td>
<td><p><span data-ttu-id="97383-129">Non</span><span class="sxs-lookup"><span data-stu-id="97383-129">No</span></span></p></td>
<td><p><span data-ttu-id="97383-130">Non</span><span class="sxs-lookup"><span data-stu-id="97383-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97383-131">Lecture générale de User PropertySet-informations</span><span class="sxs-lookup"><span data-stu-id="97383-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="97383-132"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-133">Non</span><span class="sxs-lookup"><span data-stu-id="97383-133">No</span></span></p></td>
<td><p><span data-ttu-id="97383-134">Non</span><span class="sxs-lookup"><span data-stu-id="97383-134">No</span></span></p></td>
<td><p><span data-ttu-id="97383-135">Non</span><span class="sxs-lookup"><span data-stu-id="97383-135">No</span></span></p></td>
<td><p><span data-ttu-id="97383-136">Non</span><span class="sxs-lookup"><span data-stu-id="97383-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97383-137">Lire le public user PropertySet public-information</span><span class="sxs-lookup"><span data-stu-id="97383-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="97383-138"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-139">Non</span><span class="sxs-lookup"><span data-stu-id="97383-139">No</span></span></p></td>
<td><p><span data-ttu-id="97383-140">Non</span><span class="sxs-lookup"><span data-stu-id="97383-140">No</span></span></p></td>
<td><p><span data-ttu-id="97383-141">Non</span><span class="sxs-lookup"><span data-stu-id="97383-141">No</span></span></p></td>
<td><p><span data-ttu-id="97383-142">Non</span><span class="sxs-lookup"><span data-stu-id="97383-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97383-143">Lecture utilisateur PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="97383-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="97383-144"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-145">Non</span><span class="sxs-lookup"><span data-stu-id="97383-145">No</span></span></p></td>
<td><p><span data-ttu-id="97383-146">Non</span><span class="sxs-lookup"><span data-stu-id="97383-146">No</span></span></p></td>
<td><p><span data-ttu-id="97383-147">Non</span><span class="sxs-lookup"><span data-stu-id="97383-147">No</span></span></p></td>
<td><p><span data-ttu-id="97383-148"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97383-149">Lire User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="97383-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="97383-150"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-151">Non</span><span class="sxs-lookup"><span data-stu-id="97383-151">No</span></span></p></td>
<td><p><span data-ttu-id="97383-152">Non</span><span class="sxs-lookup"><span data-stu-id="97383-152">No</span></span></p></td>
<td><p><span data-ttu-id="97383-153">Non</span><span class="sxs-lookup"><span data-stu-id="97383-153">No</span></span></p></td>
<td><p><span data-ttu-id="97383-154">Non</span><span class="sxs-lookup"><span data-stu-id="97383-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97383-155">Écrire les adresses proxy de propriété utilisateur</span><span class="sxs-lookup"><span data-stu-id="97383-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="97383-156">Non</span><span class="sxs-lookup"><span data-stu-id="97383-156">No</span></span></p></td>
<td><p><span data-ttu-id="97383-157">Non</span><span class="sxs-lookup"><span data-stu-id="97383-157">No</span></span></p></td>
<td><p><span data-ttu-id="97383-158"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-159">Non</span><span class="sxs-lookup"><span data-stu-id="97383-159">No</span></span></p></td>
<td><p><span data-ttu-id="97383-160">Non</span><span class="sxs-lookup"><span data-stu-id="97383-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97383-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="97383-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="97383-162">Non</span><span class="sxs-lookup"><span data-stu-id="97383-162">No</span></span></p></td>
<td><p><span data-ttu-id="97383-163">Non</span><span class="sxs-lookup"><span data-stu-id="97383-163">No</span></span></p></td>
<td><p><span data-ttu-id="97383-164"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-165">Non</span><span class="sxs-lookup"><span data-stu-id="97383-165">No</span></span></p></td>
<td><p><span data-ttu-id="97383-166">Non</span><span class="sxs-lookup"><span data-stu-id="97383-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97383-167">Écrire RTCPropertySet utilisateur</span><span class="sxs-lookup"><span data-stu-id="97383-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="97383-168">Non</span><span class="sxs-lookup"><span data-stu-id="97383-168">No</span></span></p></td>
<td><p><span data-ttu-id="97383-169">Non</span><span class="sxs-lookup"><span data-stu-id="97383-169">No</span></span></p></td>
<td><p><span data-ttu-id="97383-170"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-171">Non</span><span class="sxs-lookup"><span data-stu-id="97383-171">No</span></span></p></td>
<td><p><span data-ttu-id="97383-172">Non</span><span class="sxs-lookup"><span data-stu-id="97383-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97383-173">Lecture de PropertySet DS-réplication-obtention-modification de tous les objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="97383-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="97383-174">Non</span><span class="sxs-lookup"><span data-stu-id="97383-174">No</span></span></p></td>
<td><p><span data-ttu-id="97383-175">Non</span><span class="sxs-lookup"><span data-stu-id="97383-175">No</span></span></p></td>
<td><p><span data-ttu-id="97383-176">Non</span><span class="sxs-lookup"><span data-stu-id="97383-176">No</span></span></p></td>
<td><p><span data-ttu-id="97383-177"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-178">Non</span><span class="sxs-lookup"><span data-stu-id="97383-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="97383-179">Le tableau suivant répertorie les entrées de contrôle d’accès qu’il est créé dans les trois conteneurs intégrés : utilisateurs, ordinateurs et contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="97383-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="97383-180">Toutes les entrées ACE sont héritées sauf mention contraire.</span><span class="sxs-lookup"><span data-stu-id="97383-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="97383-181">ACE ajoutés aux conteneurs intégrés</span><span class="sxs-lookup"><span data-stu-id="97383-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97383-182">MAILLOTS</span><span class="sxs-lookup"><span data-stu-id="97383-182">ACE</span></span></th>
<th><span data-ttu-id="97383-183">RTCUniversal-UserReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="97383-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="97383-184">RTCUniversal-ServerReadOnly-groupe</span><span class="sxs-lookup"><span data-stu-id="97383-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97383-185">Lire le conteneur (non hérité)</span><span class="sxs-lookup"><span data-stu-id="97383-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="97383-186"><strong>Positive</strong></span><span class="sxs-lookup"><span data-stu-id="97383-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="97383-187"><strong>Oui</strong></span><span class="sxs-lookup"><span data-stu-id="97383-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

