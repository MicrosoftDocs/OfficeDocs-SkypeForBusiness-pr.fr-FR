---
title: 'Lync Server 2013 : modifications apportées par Grant-CsOUPermission'
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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="1105b-102">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1105b-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1105b-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1105b-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1105b-104">Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations à des unités d’organisation (UO) spécifiques afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux unités d’organisation sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="1105b-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1105b-105">La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="1105b-106">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="1105b-107">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="1105b-108">Autorisations octroyées pours les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1105b-109">Group</span><span class="sxs-lookup"><span data-stu-id="1105b-109">Group</span></span></th>
<th><span data-ttu-id="1105b-110">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1105b-110">Permission</span></span></th>
<th><span data-ttu-id="1105b-111">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1105b-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1105b-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1105b-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1105b-113">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1105b-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1105b-114">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-116">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-116">List contents</span></span></p>
<p><span data-ttu-id="1105b-117">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-117">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-118">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-119">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-121">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-121">List contents</span></span></p>
<p><span data-ttu-id="1105b-122">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-122">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-123">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-124">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-126">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-127">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-128">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-129">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-130">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1105b-130">Read General-Information</span></span></p>
<p><span data-ttu-id="1105b-131">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1105b-132">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-134">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-135">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1105b-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1105b-136">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-137">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-138">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1105b-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1105b-139">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="1105b-140">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="1105b-141">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="1105b-142">Autorisations octroyées pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="1105b-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1105b-143">Group</span><span class="sxs-lookup"><span data-stu-id="1105b-143">Group</span></span></th>
<th><span data-ttu-id="1105b-144">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1105b-144">Permission</span></span></th>
<th><span data-ttu-id="1105b-145">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1105b-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1105b-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1105b-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1105b-147">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1105b-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1105b-148">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-150">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-150">List contents</span></span></p>
<p><span data-ttu-id="1105b-151">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-151">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-152">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-153">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-155">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-155">List contents</span></span></p>
<p><span data-ttu-id="1105b-156">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-156">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-157">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-158">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-160">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-161">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="1105b-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1105b-162">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-164">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-165">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="1105b-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1105b-166">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="1105b-167">Octroi d’autorisation pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="1105b-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="1105b-168">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="1105b-169">Autorisations octroyées pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="1105b-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1105b-170">Group</span><span class="sxs-lookup"><span data-stu-id="1105b-170">Group</span></span></th>
<th><span data-ttu-id="1105b-171">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1105b-171">Permission</span></span></th>
<th><span data-ttu-id="1105b-172">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1105b-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1105b-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1105b-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1105b-174">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1105b-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1105b-175">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-177">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-177">List contents</span></span></p>
<p><span data-ttu-id="1105b-178">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-178">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-179">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-180">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-182">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-182">List contents</span></span></p>
<p><span data-ttu-id="1105b-183">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-183">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-184">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-185">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-187">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-188">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-189">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-190">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-191">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1105b-191">Read General-Information</span></span></p>
<p><span data-ttu-id="1105b-192">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1105b-193">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1105b-194">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-196">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-197">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1105b-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1105b-198">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1105b-198">Write displayName</span></span></p>
<p><span data-ttu-id="1105b-199">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1105b-199">Write description</span></span></p>
<p><span data-ttu-id="1105b-200">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1105b-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1105b-201">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1105b-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1105b-202">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-203">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-204">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1105b-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1105b-205">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="1105b-206">Octroi d’une autorisation pour les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="1105b-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="1105b-207">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="1105b-208">Autorisations octroyées pours les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="1105b-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1105b-209">Group</span><span class="sxs-lookup"><span data-stu-id="1105b-209">Group</span></span></th>
<th><span data-ttu-id="1105b-210">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1105b-210">Permission</span></span></th>
<th><span data-ttu-id="1105b-211">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1105b-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1105b-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1105b-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1105b-213">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1105b-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1105b-214">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-216">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-216">List contents</span></span></p>
<p><span data-ttu-id="1105b-217">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-217">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-218">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-219">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-221">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-221">List contents</span></span></p>
<p><span data-ttu-id="1105b-222">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-222">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-223">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-224">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-226">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-227">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-228">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-229">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-230">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1105b-231">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1105b-231">Read General-Information</span></span></p>
<p><span data-ttu-id="1105b-232">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1105b-233">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-235">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="1105b-235">Create child</span></span></p>
<p><span data-ttu-id="1105b-236">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="1105b-236">Delete child</span></span></p>
<p><span data-ttu-id="1105b-237">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="1105b-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="1105b-238">Contact</span><span class="sxs-lookup"><span data-stu-id="1105b-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-240">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1105b-240">Write displayName</span></span></p>
<p><span data-ttu-id="1105b-241">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1105b-241">Write description</span></span></p>
<p><span data-ttu-id="1105b-242">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1105b-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1105b-243">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-245">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-246">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1105b-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1105b-247">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1105b-247">Write displayName</span></span></p>
<p><span data-ttu-id="1105b-248">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1105b-248">Write description</span></span></p>
<p><span data-ttu-id="1105b-249">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1105b-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1105b-250">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1105b-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1105b-251">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-252">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-253">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1105b-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1105b-254">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="1105b-255">Octroi d’une autorisation pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="1105b-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="1105b-256">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1105b-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="1105b-257">Autorisations octroyées pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="1105b-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1105b-258">Group</span><span class="sxs-lookup"><span data-stu-id="1105b-258">Group</span></span></th>
<th><span data-ttu-id="1105b-259">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1105b-259">Permission</span></span></th>
<th><span data-ttu-id="1105b-260">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1105b-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1105b-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1105b-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1105b-262">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1105b-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1105b-263">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-265">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-265">List contents</span></span></p>
<p><span data-ttu-id="1105b-266">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-266">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-267">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-268">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-270">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1105b-270">List contents</span></span></p>
<p><span data-ttu-id="1105b-271">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1105b-271">Read all properties</span></span></p>
<p><span data-ttu-id="1105b-272">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1105b-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1105b-273">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1105b-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1105b-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1105b-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1105b-275">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-276">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-277">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-278">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1105b-279">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1105b-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="1105b-280">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1105b-280">Read General-Information</span></span></p>
<p><span data-ttu-id="1105b-281">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1105b-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1105b-282">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1105b-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1105b-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1105b-284">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1105b-285">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1105b-286">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1105b-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1105b-287">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1105b-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1105b-288">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="1105b-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

