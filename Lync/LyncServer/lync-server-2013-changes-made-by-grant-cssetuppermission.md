---
title: 'Lync Server 2013 : modifications apportées par Grant-CsSetupPermission'
description: 'Lync Server 2013 : modifications apportées par Grant-CsSetupPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543600"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="b85f0-103">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b85f0-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b85f0-104">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b85f0-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b85f0-105">Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, permettant ainsi aux membres du groupe RTCUniversalServerAdmins de cette unité d’organisation d’installer Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="b85f0-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="b85f0-106">L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="b85f0-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="b85f0-107">Autorisations accordées aux objets dans l’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="b85f0-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b85f0-108">Les autorisations s’appliquent à :</span><span class="sxs-lookup"><span data-stu-id="b85f0-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="b85f0-109">Les autorisations accordées sont :</span><span class="sxs-lookup"><span data-stu-id="b85f0-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b85f0-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b85f0-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b85f0-111">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-112">Lecture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="b85f0-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="b85f0-113">Écriture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="b85f0-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="b85f0-114">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="b85f0-115">Réplication des modifications d’annuaire</span><span class="sxs-lookup"><span data-stu-id="b85f0-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85f0-116">Objets serviceConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-117">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-118">Autorisations en lecture</span><span class="sxs-lookup"><span data-stu-id="b85f0-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="b85f0-119">Autorisations en écriture</span><span class="sxs-lookup"><span data-stu-id="b85f0-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="b85f0-120">Création de l’enfant</span><span class="sxs-lookup"><span data-stu-id="b85f0-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="b85f0-121">Suppression de l’enfant</span><span class="sxs-lookup"><span data-stu-id="b85f0-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="b85f0-122">Affichage du contenu</span><span class="sxs-lookup"><span data-stu-id="b85f0-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="b85f0-123">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-124">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-125">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85f0-126">Objets msRTCSIP-Server descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-127">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-128">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-129">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-130">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85f0-131">Objets msRTCSIP-WebComponents descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-132">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-133">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-134">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-135">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85f0-136">Objets msRTCSIP-MCU descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-137">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-138">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-139">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-140">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85f0-141">Objets msRTCSIP-MediationServer descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-142">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-143">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-144">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-145">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85f0-146">Objets msRTCSIP-ApplicationServer descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-147">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-148">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-149">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-150">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b85f0-151">Objets msRTCSIP-ConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-152">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="b85f0-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-153">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-154">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="b85f0-155">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b85f0-156">Objets Computer descendants</span><span class="sxs-lookup"><span data-stu-id="b85f0-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="b85f0-157">Accès particulier pour serviceConnectionPoint :</span><span class="sxs-lookup"><span data-stu-id="b85f0-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-158">Création d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="b85f0-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="b85f0-159">Suppression d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="b85f0-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="b85f0-160">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="b85f0-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="b85f0-161">Accès particulier pour les informations publiques :</span><span class="sxs-lookup"><span data-stu-id="b85f0-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-162">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="b85f0-163">Accès particulier pour le nom d’hôte DNS :</span><span class="sxs-lookup"><span data-stu-id="b85f0-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="b85f0-164">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="b85f0-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

