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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529431"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="f4edd-102">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4edd-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4edd-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f4edd-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f4edd-104">Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations à des unités d’organisation (UO) spécifiques afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux unités d’organisation sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="f4edd-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f4edd-105">La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="f4edd-106">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="f4edd-107">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="f4edd-108">Autorisations octroyées pours les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4edd-109">Groupe</span><span class="sxs-lookup"><span data-stu-id="f4edd-109">Group</span></span></th>
<th><span data-ttu-id="f4edd-110">Autorisation</span><span class="sxs-lookup"><span data-stu-id="f4edd-110">Permission</span></span></th>
<th><span data-ttu-id="f4edd-111">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="f4edd-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f4edd-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f4edd-113">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="f4edd-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f4edd-114">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-116">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-116">List contents</span></span></p>
<p><span data-ttu-id="f4edd-117">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-117">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-118">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-119">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-121">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-121">List contents</span></span></p>
<p><span data-ttu-id="f4edd-122">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-122">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-123">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-124">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-126">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-127">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-128">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-129">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-130">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="f4edd-130">Read General-Information</span></span></p>
<p><span data-ttu-id="f4edd-131">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-132">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-134">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-135">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f4edd-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f4edd-136">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-137">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-138">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f4edd-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f4edd-139">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="f4edd-140">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="f4edd-141">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="f4edd-142">Autorisations octroyées pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4edd-143">Groupe</span><span class="sxs-lookup"><span data-stu-id="f4edd-143">Group</span></span></th>
<th><span data-ttu-id="f4edd-144">Autorisation</span><span class="sxs-lookup"><span data-stu-id="f4edd-144">Permission</span></span></th>
<th><span data-ttu-id="f4edd-145">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="f4edd-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f4edd-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f4edd-147">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="f4edd-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f4edd-148">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-150">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-150">List contents</span></span></p>
<p><span data-ttu-id="f4edd-151">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-151">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-152">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-153">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-155">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-155">List contents</span></span></p>
<p><span data-ttu-id="f4edd-156">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-156">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-157">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-158">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-160">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-161">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="f4edd-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="f4edd-162">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-164">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-165">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="f4edd-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="f4edd-166">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="f4edd-167">Octroi d’autorisation pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="f4edd-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="f4edd-168">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="f4edd-169">Autorisations octroyées pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="f4edd-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4edd-170">Groupe</span><span class="sxs-lookup"><span data-stu-id="f4edd-170">Group</span></span></th>
<th><span data-ttu-id="f4edd-171">Autorisation</span><span class="sxs-lookup"><span data-stu-id="f4edd-171">Permission</span></span></th>
<th><span data-ttu-id="f4edd-172">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="f4edd-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f4edd-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f4edd-174">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="f4edd-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f4edd-175">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-177">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-177">List contents</span></span></p>
<p><span data-ttu-id="f4edd-178">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-178">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-179">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-180">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-182">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-182">List contents</span></span></p>
<p><span data-ttu-id="f4edd-183">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-183">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-184">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-185">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-187">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-188">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-189">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-190">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-191">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="f4edd-191">Read General-Information</span></span></p>
<p><span data-ttu-id="f4edd-192">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f4edd-193">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-194">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-196">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-197">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="f4edd-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="f4edd-198">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="f4edd-198">Write displayName</span></span></p>
<p><span data-ttu-id="f4edd-199">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="f4edd-199">Write description</span></span></p>
<p><span data-ttu-id="f4edd-200">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f4edd-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="f4edd-201">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f4edd-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f4edd-202">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-203">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-204">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f4edd-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f4edd-205">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="f4edd-206">Octroi d’une autorisation pour les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="f4edd-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="f4edd-207">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="f4edd-208">Autorisations octroyées pours les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="f4edd-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4edd-209">Groupe</span><span class="sxs-lookup"><span data-stu-id="f4edd-209">Group</span></span></th>
<th><span data-ttu-id="f4edd-210">Autorisation</span><span class="sxs-lookup"><span data-stu-id="f4edd-210">Permission</span></span></th>
<th><span data-ttu-id="f4edd-211">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="f4edd-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f4edd-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f4edd-213">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="f4edd-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f4edd-214">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-216">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-216">List contents</span></span></p>
<p><span data-ttu-id="f4edd-217">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-217">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-218">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-219">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-221">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-221">List contents</span></span></p>
<p><span data-ttu-id="f4edd-222">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-222">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-223">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-224">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-226">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-227">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-228">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-229">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-230">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f4edd-231">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="f4edd-231">Read General-Information</span></span></p>
<p><span data-ttu-id="f4edd-232">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-233">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-235">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="f4edd-235">Create child</span></span></p>
<p><span data-ttu-id="f4edd-236">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="f4edd-236">Delete child</span></span></p>
<p><span data-ttu-id="f4edd-237">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="f4edd-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="f4edd-238">Contact</span><span class="sxs-lookup"><span data-stu-id="f4edd-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-240">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="f4edd-240">Write displayName</span></span></p>
<p><span data-ttu-id="f4edd-241">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="f4edd-241">Write description</span></span></p>
<p><span data-ttu-id="f4edd-242">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f4edd-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="f4edd-243">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-245">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-246">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="f4edd-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="f4edd-247">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="f4edd-247">Write displayName</span></span></p>
<p><span data-ttu-id="f4edd-248">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="f4edd-248">Write description</span></span></p>
<p><span data-ttu-id="f4edd-249">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f4edd-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="f4edd-250">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f4edd-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f4edd-251">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-252">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-253">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f4edd-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f4edd-254">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="f4edd-255">Octroi d’une autorisation pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="f4edd-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="f4edd-256">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="f4edd-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="f4edd-257">Autorisations octroyées pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="f4edd-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4edd-258">Groupe</span><span class="sxs-lookup"><span data-stu-id="f4edd-258">Group</span></span></th>
<th><span data-ttu-id="f4edd-259">Autorisation</span><span class="sxs-lookup"><span data-stu-id="f4edd-259">Permission</span></span></th>
<th><span data-ttu-id="f4edd-260">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="f4edd-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f4edd-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f4edd-262">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="f4edd-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f4edd-263">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-265">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-265">List contents</span></span></p>
<p><span data-ttu-id="f4edd-266">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-266">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-267">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-268">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-270">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="f4edd-270">List contents</span></span></p>
<p><span data-ttu-id="f4edd-271">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="f4edd-271">Read all properties</span></span></p>
<p><span data-ttu-id="f4edd-272">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="f4edd-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-273">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="f4edd-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4edd-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f4edd-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f4edd-275">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-276">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-277">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-278">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f4edd-279">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="f4edd-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="f4edd-280">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="f4edd-280">Read General-Information</span></span></p>
<p><span data-ttu-id="f4edd-281">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4edd-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f4edd-282">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4edd-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f4edd-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f4edd-284">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-285">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-286">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f4edd-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f4edd-287">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f4edd-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f4edd-288">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="f4edd-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

