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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="1be5f-102">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1be5f-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1be5f-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1be5f-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1be5f-104">Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations à des unités d’organisation (UO) spécifiques afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux unités d’organisation sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="1be5f-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1be5f-105">La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="1be5f-106">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="1be5f-107">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="1be5f-108">Autorisations octroyées pours les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1be5f-109">Group</span><span class="sxs-lookup"><span data-stu-id="1be5f-109">Group</span></span></th>
<th><span data-ttu-id="1be5f-110">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1be5f-110">Permission</span></span></th>
<th><span data-ttu-id="1be5f-111">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1be5f-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1be5f-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1be5f-113">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1be5f-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1be5f-114">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-116">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-116">List contents</span></span></p>
<p><span data-ttu-id="1be5f-117">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-117">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-118">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-119">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-121">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-121">List contents</span></span></p>
<p><span data-ttu-id="1be5f-122">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-122">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-123">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-124">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-126">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-127">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-128">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-129">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-130">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1be5f-130">Read General-Information</span></span></p>
<p><span data-ttu-id="1be5f-131">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-132">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-134">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-135">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1be5f-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1be5f-136">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-137">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-138">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1be5f-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1be5f-139">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="1be5f-140">Octroi d’une autorisation pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="1be5f-141">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="1be5f-142">Autorisations octroyées pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1be5f-143">Group</span><span class="sxs-lookup"><span data-stu-id="1be5f-143">Group</span></span></th>
<th><span data-ttu-id="1be5f-144">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1be5f-144">Permission</span></span></th>
<th><span data-ttu-id="1be5f-145">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1be5f-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1be5f-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1be5f-147">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1be5f-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1be5f-148">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-150">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-150">List contents</span></span></p>
<p><span data-ttu-id="1be5f-151">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-151">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-152">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-153">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-155">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-155">List contents</span></span></p>
<p><span data-ttu-id="1be5f-156">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-156">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-157">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-158">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-160">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-161">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="1be5f-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1be5f-162">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-164">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-165">Lire le nom d’hôte DNS validé</span><span class="sxs-lookup"><span data-stu-id="1be5f-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1be5f-166">Objets de l’ordinateur descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="1be5f-167">Octroi d’autorisation pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="1be5f-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="1be5f-168">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="1be5f-169">Autorisations octroyées pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="1be5f-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1be5f-170">Group</span><span class="sxs-lookup"><span data-stu-id="1be5f-170">Group</span></span></th>
<th><span data-ttu-id="1be5f-171">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1be5f-171">Permission</span></span></th>
<th><span data-ttu-id="1be5f-172">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1be5f-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1be5f-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1be5f-174">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1be5f-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1be5f-175">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-177">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-177">List contents</span></span></p>
<p><span data-ttu-id="1be5f-178">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-178">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-179">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-180">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-182">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-182">List contents</span></span></p>
<p><span data-ttu-id="1be5f-183">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-183">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-184">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-185">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-187">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-188">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-189">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-190">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-191">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1be5f-191">Read General-Information</span></span></p>
<p><span data-ttu-id="1be5f-192">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1be5f-193">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-194">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-196">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-197">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1be5f-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1be5f-198">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1be5f-198">Write displayName</span></span></p>
<p><span data-ttu-id="1be5f-199">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1be5f-199">Write description</span></span></p>
<p><span data-ttu-id="1be5f-200">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1be5f-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1be5f-201">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1be5f-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1be5f-202">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-203">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-204">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1be5f-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1be5f-205">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="1be5f-206">Octroi d’une autorisation pour les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="1be5f-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="1be5f-207">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="1be5f-208">Autorisations octroyées pours les objets périphérique</span><span class="sxs-lookup"><span data-stu-id="1be5f-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1be5f-209">Group</span><span class="sxs-lookup"><span data-stu-id="1be5f-209">Group</span></span></th>
<th><span data-ttu-id="1be5f-210">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1be5f-210">Permission</span></span></th>
<th><span data-ttu-id="1be5f-211">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1be5f-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1be5f-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1be5f-213">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1be5f-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1be5f-214">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-216">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-216">List contents</span></span></p>
<p><span data-ttu-id="1be5f-217">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-217">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-218">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-219">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-221">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-221">List contents</span></span></p>
<p><span data-ttu-id="1be5f-222">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-222">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-223">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-224">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-226">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-227">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-228">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-229">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-230">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1be5f-231">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1be5f-231">Read General-Information</span></span></p>
<p><span data-ttu-id="1be5f-232">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-233">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-235">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="1be5f-235">Create child</span></span></p>
<p><span data-ttu-id="1be5f-236">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="1be5f-236">Delete child</span></span></p>
<p><span data-ttu-id="1be5f-237">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="1be5f-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="1be5f-238">Contact</span><span class="sxs-lookup"><span data-stu-id="1be5f-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-240">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1be5f-240">Write displayName</span></span></p>
<p><span data-ttu-id="1be5f-241">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1be5f-241">Write description</span></span></p>
<p><span data-ttu-id="1be5f-242">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1be5f-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1be5f-243">Objets d’utilisateur descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-245">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-246">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1be5f-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1be5f-247">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="1be5f-247">Write displayName</span></span></p>
<p><span data-ttu-id="1be5f-248">Écrire la description</span><span class="sxs-lookup"><span data-stu-id="1be5f-248">Write description</span></span></p>
<p><span data-ttu-id="1be5f-249">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1be5f-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1be5f-250">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1be5f-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1be5f-251">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-252">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-253">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1be5f-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1be5f-254">Objets du contact descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="1be5f-255">Octroi d’une autorisation pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="1be5f-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="1be5f-256">Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1be5f-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="1be5f-257">Autorisations octroyées pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="1be5f-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1be5f-258">Group</span><span class="sxs-lookup"><span data-stu-id="1be5f-258">Group</span></span></th>
<th><span data-ttu-id="1be5f-259">Autorisation</span><span class="sxs-lookup"><span data-stu-id="1be5f-259">Permission</span></span></th>
<th><span data-ttu-id="1be5f-260">S’applique à :</span><span class="sxs-lookup"><span data-stu-id="1be5f-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1be5f-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1be5f-262">Réplication des modifications du répertoire</span><span class="sxs-lookup"><span data-stu-id="1be5f-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1be5f-263">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-265">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-265">List contents</span></span></p>
<p><span data-ttu-id="1be5f-266">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-266">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-267">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-268">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-270">Lister le contenu</span><span class="sxs-lookup"><span data-stu-id="1be5f-270">List contents</span></span></p>
<p><span data-ttu-id="1be5f-271">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="1be5f-271">Read all properties</span></span></p>
<p><span data-ttu-id="1be5f-272">Lire les autorisations</span><span class="sxs-lookup"><span data-stu-id="1be5f-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-273">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="1be5f-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be5f-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1be5f-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1be5f-275">Lire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-276">Lire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-277">Lire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-278">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1be5f-279">Lire les informations publiques</span><span class="sxs-lookup"><span data-stu-id="1be5f-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="1be5f-280">Lire les informations générales</span><span class="sxs-lookup"><span data-stu-id="1be5f-280">Read General-Information</span></span></p>
<p><span data-ttu-id="1be5f-281">Lire les restrictions de compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="1be5f-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1be5f-282">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be5f-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1be5f-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1be5f-284">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-285">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-286">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1be5f-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1be5f-287">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1be5f-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1be5f-288">Objets du InetOrgPerson descendant</span><span class="sxs-lookup"><span data-stu-id="1be5f-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

