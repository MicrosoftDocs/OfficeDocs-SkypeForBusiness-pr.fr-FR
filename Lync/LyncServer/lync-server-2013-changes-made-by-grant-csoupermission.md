---
title: 'Lync Server 2013 : modifications apportées par Grant-CsOUPermission'
description: 'Lync Server 2013 : modifications apportées par Grant-CsOUPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543610"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="abc66-103">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc66-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc66-104">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="abc66-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="abc66-105">Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations à des unités d’organisation (UO) spécifiques afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux unités d’organisation sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="abc66-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="abc66-106">La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="abc66-107">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="abc66-108">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="abc66-109">Autorisations octroyées pours les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abc66-110">Groupe</span><span class="sxs-lookup"><span data-stu-id="abc66-110">Group</span></span></th>
<th><span data-ttu-id="abc66-111">Autorisation</span><span class="sxs-lookup"><span data-stu-id="abc66-111">Permission</span></span></th>
<th><span data-ttu-id="abc66-112">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="abc66-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abc66-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="abc66-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="abc66-114">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="abc66-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="abc66-115">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-117">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-117">List contents</span></span></p>
<p><span data-ttu-id="abc66-118">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-118">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-119">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-120">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-122">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-122">List contents</span></span></p>
<p><span data-ttu-id="abc66-123">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-123">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-124">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-125">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-127">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-128">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-129">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-130">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-131">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="abc66-131">Read General-Information</span></span></p>
<p><span data-ttu-id="abc66-132">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="abc66-133">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-135">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-136">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="abc66-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="abc66-137">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-138">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-139">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="abc66-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="abc66-140">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="abc66-141">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="abc66-142">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="abc66-143">Autorisations octroyées pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="abc66-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abc66-144">Groupe</span><span class="sxs-lookup"><span data-stu-id="abc66-144">Group</span></span></th>
<th><span data-ttu-id="abc66-145">Autorisation</span><span class="sxs-lookup"><span data-stu-id="abc66-145">Permission</span></span></th>
<th><span data-ttu-id="abc66-146">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="abc66-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abc66-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="abc66-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="abc66-148">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="abc66-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="abc66-149">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-151">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-151">List contents</span></span></p>
<p><span data-ttu-id="abc66-152">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-152">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-153">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-154">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-156">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-156">List contents</span></span></p>
<p><span data-ttu-id="abc66-157">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-157">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-158">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-159">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-161">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-162">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="abc66-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="abc66-163">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-165">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-166">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="abc66-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="abc66-167">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="abc66-168">Octroi d’autorisation pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="abc66-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="abc66-169">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="abc66-170">Autorisations octroyées pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="abc66-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abc66-171">Groupe</span><span class="sxs-lookup"><span data-stu-id="abc66-171">Group</span></span></th>
<th><span data-ttu-id="abc66-172">Autorisation</span><span class="sxs-lookup"><span data-stu-id="abc66-172">Permission</span></span></th>
<th><span data-ttu-id="abc66-173">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="abc66-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abc66-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="abc66-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="abc66-175">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="abc66-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="abc66-176">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-178">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-178">List contents</span></span></p>
<p><span data-ttu-id="abc66-179">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-179">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-180">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-181">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-183">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-183">List contents</span></span></p>
<p><span data-ttu-id="abc66-184">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-184">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-185">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-186">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-188">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-189">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-190">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-191">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-192">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="abc66-192">Read General-Information</span></span></p>
<p><span data-ttu-id="abc66-193">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="abc66-194">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="abc66-195">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-197">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-198">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="abc66-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="abc66-199">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="abc66-199">Write displayName</span></span></p>
<p><span data-ttu-id="abc66-200">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="abc66-200">Write description</span></span></p>
<p><span data-ttu-id="abc66-201">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="abc66-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="abc66-202">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="abc66-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="abc66-203">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-204">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-205">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="abc66-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="abc66-206">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="abc66-207">Octroi d’une autorisation pour les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="abc66-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="abc66-208">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="abc66-209">Autorisations octroyées pours les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="abc66-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abc66-210">Groupe</span><span class="sxs-lookup"><span data-stu-id="abc66-210">Group</span></span></th>
<th><span data-ttu-id="abc66-211">Autorisation</span><span class="sxs-lookup"><span data-stu-id="abc66-211">Permission</span></span></th>
<th><span data-ttu-id="abc66-212">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="abc66-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abc66-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="abc66-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="abc66-214">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="abc66-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="abc66-215">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-217">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-217">List contents</span></span></p>
<p><span data-ttu-id="abc66-218">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-218">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-219">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-220">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-222">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-222">List contents</span></span></p>
<p><span data-ttu-id="abc66-223">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-223">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-224">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-225">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-227">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-228">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-229">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-230">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-231">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="abc66-232">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="abc66-232">Read General-Information</span></span></p>
<p><span data-ttu-id="abc66-233">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="abc66-234">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-236">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="abc66-236">Create child</span></span></p>
<p><span data-ttu-id="abc66-237">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="abc66-237">Delete child</span></span></p>
<p><span data-ttu-id="abc66-238">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="abc66-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="abc66-239">Contact</span><span class="sxs-lookup"><span data-stu-id="abc66-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-241">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="abc66-241">Write displayName</span></span></p>
<p><span data-ttu-id="abc66-242">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="abc66-242">Write description</span></span></p>
<p><span data-ttu-id="abc66-243">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="abc66-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="abc66-244">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-246">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-247">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="abc66-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="abc66-248">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="abc66-248">Write displayName</span></span></p>
<p><span data-ttu-id="abc66-249">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="abc66-249">Write description</span></span></p>
<p><span data-ttu-id="abc66-250">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="abc66-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="abc66-251">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="abc66-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="abc66-252">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-253">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-254">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="abc66-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="abc66-255">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="abc66-256">Octroi d’une autorisation pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="abc66-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="abc66-257">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="abc66-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="abc66-258">Autorisations octroyées pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="abc66-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abc66-259">Groupe</span><span class="sxs-lookup"><span data-stu-id="abc66-259">Group</span></span></th>
<th><span data-ttu-id="abc66-260">Autorisation</span><span class="sxs-lookup"><span data-stu-id="abc66-260">Permission</span></span></th>
<th><span data-ttu-id="abc66-261">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="abc66-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abc66-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="abc66-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="abc66-263">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="abc66-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="abc66-264">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-266">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-266">List contents</span></span></p>
<p><span data-ttu-id="abc66-267">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-267">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-268">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-269">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-271">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="abc66-271">List contents</span></span></p>
<p><span data-ttu-id="abc66-272">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="abc66-272">Read all properties</span></span></p>
<p><span data-ttu-id="abc66-273">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="abc66-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="abc66-274">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="abc66-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abc66-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="abc66-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="abc66-276">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-277">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-278">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-279">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="abc66-280">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="abc66-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="abc66-281">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="abc66-281">Read General-Information</span></span></p>
<p><span data-ttu-id="abc66-282">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="abc66-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="abc66-283">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abc66-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="abc66-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="abc66-285">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="abc66-286">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="abc66-287">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="abc66-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="abc66-288">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="abc66-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="abc66-289">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="abc66-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

