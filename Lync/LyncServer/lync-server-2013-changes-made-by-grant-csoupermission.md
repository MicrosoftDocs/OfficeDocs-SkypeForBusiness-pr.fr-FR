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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="a2dbf-102">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2dbf-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2dbf-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a2dbf-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a2dbf-104">Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations aux unités d’organisation (UO) spécifiées de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans être membres du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="a2dbf-105">L’applet **de commande Grant-CsOuPermission** accorde des autorisations aux objets de l’unité d’organisation spécifiée, comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="a2dbf-106">Octroi d’autorisations pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="a2dbf-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="a2dbf-107">Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets utilisateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="a2dbf-108">Autorisations accordées pour les objets utilisateur</span><span class="sxs-lookup"><span data-stu-id="a2dbf-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2dbf-109">Groupe</span><span class="sxs-lookup"><span data-stu-id="a2dbf-109">Group</span></span></th>
<th><span data-ttu-id="a2dbf-110">Permission</span><span class="sxs-lookup"><span data-stu-id="a2dbf-110">Permission</span></span></th>
<th><span data-ttu-id="a2dbf-111">S’applique à</span><span class="sxs-lookup"><span data-stu-id="a2dbf-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a2dbf-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-113">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="a2dbf-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-114">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-116">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-116">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-117">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-117">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-118">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-119">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-121">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-121">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-122">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-122">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-123">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-124">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-126">Lecture de RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-127">Lecture de RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-128">Lecture de RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-129">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-130">Lecture générale-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-130">Read General-Information</span></span></p>
<p><span data-ttu-id="a2dbf-131">Lire le compte d’utilisateur-restrictions</span><span class="sxs-lookup"><span data-stu-id="a2dbf-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-132">Objets utilisateur descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-134">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-135">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a2dbf-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a2dbf-136">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-137">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-138">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a2dbf-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-139">Objets utilisateur descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="a2dbf-140">Octroi d’autorisations pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="a2dbf-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="a2dbf-141">Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets ordinateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="a2dbf-142">Autorisations accordées pour les objets ordinateur</span><span class="sxs-lookup"><span data-stu-id="a2dbf-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2dbf-143">Groupe</span><span class="sxs-lookup"><span data-stu-id="a2dbf-143">Group</span></span></th>
<th><span data-ttu-id="a2dbf-144">Permission</span><span class="sxs-lookup"><span data-stu-id="a2dbf-144">Permission</span></span></th>
<th><span data-ttu-id="a2dbf-145">S’applique à</span><span class="sxs-lookup"><span data-stu-id="a2dbf-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a2dbf-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-147">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="a2dbf-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-148">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-150">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-150">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-151">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-151">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-152">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-153">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-155">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-155">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-156">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-156">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-157">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-158">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-160">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-161">Lecture validée de DNS-nom d’hôte-nom</span><span class="sxs-lookup"><span data-stu-id="a2dbf-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-162">Objets ordinateur descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-164">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-165">Lecture validée de DNS-nom d’hôte-nom</span><span class="sxs-lookup"><span data-stu-id="a2dbf-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-166">Objets ordinateur descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="a2dbf-167">Octroi d’autorisations de contact ou d’objets AppContact</span><span class="sxs-lookup"><span data-stu-id="a2dbf-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="a2dbf-168">Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets de contact ou les objets AppContact sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="a2dbf-169">Autorisations accordées pour les objets contact ou AppContact</span><span class="sxs-lookup"><span data-stu-id="a2dbf-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2dbf-170">Groupe</span><span class="sxs-lookup"><span data-stu-id="a2dbf-170">Group</span></span></th>
<th><span data-ttu-id="a2dbf-171">Permission</span><span class="sxs-lookup"><span data-stu-id="a2dbf-171">Permission</span></span></th>
<th><span data-ttu-id="a2dbf-172">S’applique à</span><span class="sxs-lookup"><span data-stu-id="a2dbf-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a2dbf-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-174">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="a2dbf-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-175">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-177">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-177">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-178">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-178">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-179">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-180">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-182">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-182">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-183">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-183">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-184">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-185">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-187">Lecture de RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-188">Lecture de RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-189">Lecture de RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-190">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-191">Lecture générale-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-191">Read General-Information</span></span></p>
<p><span data-ttu-id="a2dbf-192">Lire les informations personnelles</span><span class="sxs-lookup"><span data-stu-id="a2dbf-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a2dbf-193">Lire le compte d’utilisateur-restrictions</span><span class="sxs-lookup"><span data-stu-id="a2dbf-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-194">Objets contact descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-196">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-197">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="a2dbf-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="a2dbf-198">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="a2dbf-198">Write displayName</span></span></p>
<p><span data-ttu-id="a2dbf-199">Entrer une description</span><span class="sxs-lookup"><span data-stu-id="a2dbf-199">Write description</span></span></p>
<p><span data-ttu-id="a2dbf-200">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="a2dbf-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="a2dbf-201">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a2dbf-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a2dbf-202">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-203">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-204">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a2dbf-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-205">Objets contact descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="a2dbf-206">Octroi d’autorisations pour les objets appareil</span><span class="sxs-lookup"><span data-stu-id="a2dbf-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="a2dbf-207">Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets d’appareil sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="a2dbf-208">Autorisations accordées pour les objets appareil</span><span class="sxs-lookup"><span data-stu-id="a2dbf-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2dbf-209">Groupe</span><span class="sxs-lookup"><span data-stu-id="a2dbf-209">Group</span></span></th>
<th><span data-ttu-id="a2dbf-210">Permission</span><span class="sxs-lookup"><span data-stu-id="a2dbf-210">Permission</span></span></th>
<th><span data-ttu-id="a2dbf-211">S’applique à</span><span class="sxs-lookup"><span data-stu-id="a2dbf-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a2dbf-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-213">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="a2dbf-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-214">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-216">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-216">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-217">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-217">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-218">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-219">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-221">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-221">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-222">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-222">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-223">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-224">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-226">Lecture de RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-227">Lecture de RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-228">Lecture de RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-229">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-230">Lire les informations personnelles</span><span class="sxs-lookup"><span data-stu-id="a2dbf-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a2dbf-231">Lecture générale-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-231">Read General-Information</span></span></p>
<p><span data-ttu-id="a2dbf-232">Lire le compte d’utilisateur-restrictions</span><span class="sxs-lookup"><span data-stu-id="a2dbf-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-233">Objets contact descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-235">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="a2dbf-235">Create child</span></span></p>
<p><span data-ttu-id="a2dbf-236">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="a2dbf-236">Delete child</span></span></p>
<p><span data-ttu-id="a2dbf-237">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a2dbf-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-238">Locuteur</span><span class="sxs-lookup"><span data-stu-id="a2dbf-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-240">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="a2dbf-240">Write displayName</span></span></p>
<p><span data-ttu-id="a2dbf-241">Entrer une description</span><span class="sxs-lookup"><span data-stu-id="a2dbf-241">Write description</span></span></p>
<p><span data-ttu-id="a2dbf-242">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="a2dbf-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-243">Objets utilisateur descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-245">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-246">Écrire otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="a2dbf-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="a2dbf-247">Écrire displayName</span><span class="sxs-lookup"><span data-stu-id="a2dbf-247">Write displayName</span></span></p>
<p><span data-ttu-id="a2dbf-248">Entrer une description</span><span class="sxs-lookup"><span data-stu-id="a2dbf-248">Write description</span></span></p>
<p><span data-ttu-id="a2dbf-249">Écrire telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="a2dbf-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="a2dbf-250">Écrire msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a2dbf-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a2dbf-251">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-252">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-253">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a2dbf-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-254">Objets contact descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="a2dbf-255">Octroi d’autorisations pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="a2dbf-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="a2dbf-256">Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets InetOrgPerson sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a2dbf-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="a2dbf-257">Autorisations accordées pour les objets InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="a2dbf-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2dbf-258">Groupe</span><span class="sxs-lookup"><span data-stu-id="a2dbf-258">Group</span></span></th>
<th><span data-ttu-id="a2dbf-259">Permission</span><span class="sxs-lookup"><span data-stu-id="a2dbf-259">Permission</span></span></th>
<th><span data-ttu-id="a2dbf-260">S’applique à</span><span class="sxs-lookup"><span data-stu-id="a2dbf-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a2dbf-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-262">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="a2dbf-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-263">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-265">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-265">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-266">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-266">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-267">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-268">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-270">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="a2dbf-270">List contents</span></span></p>
<p><span data-ttu-id="a2dbf-271">Lire toutes les propriétés</span><span class="sxs-lookup"><span data-stu-id="a2dbf-271">Read all properties</span></span></p>
<p><span data-ttu-id="a2dbf-272">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="a2dbf-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-273">Cet objet uniquement</span><span class="sxs-lookup"><span data-stu-id="a2dbf-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2dbf-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a2dbf-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-275">Lecture de RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-276">Lecture de RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-277">Lecture de RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-278">Lire les informations personnelles</span><span class="sxs-lookup"><span data-stu-id="a2dbf-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a2dbf-279">Lecture publique-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="a2dbf-280">Lecture générale-informations</span><span class="sxs-lookup"><span data-stu-id="a2dbf-280">Read General-Information</span></span></p>
<p><span data-ttu-id="a2dbf-281">Lire le compte d’utilisateur-restrictions</span><span class="sxs-lookup"><span data-stu-id="a2dbf-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-282">Objets inetOrgPerson descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2dbf-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a2dbf-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-284">Écrire RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-285">Écrire RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-286">Écrire RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a2dbf-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a2dbf-287">Écrire proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a2dbf-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a2dbf-288">Objets inetOrgPerson descendants</span><span class="sxs-lookup"><span data-stu-id="a2dbf-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

