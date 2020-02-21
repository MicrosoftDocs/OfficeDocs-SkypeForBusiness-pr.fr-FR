---
title: 'Lync Server 2013 : modifications apportées par Grant-CsSetupPermission'
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
ms.openlocfilehash: 98ac8f4f84280fb8980d38170fc964157b8037ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="cbd68-102">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd68-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbd68-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="cbd68-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="cbd68-104">Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, permettant ainsi aux membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation d’installer Lync Server 2013 dans le domaine sans être membre du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="cbd68-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="cbd68-105">L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="cbd68-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="cbd68-106">Autorisations accordées aux objets dans l’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="cbd68-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbd68-107">Les autorisations s’appliquent à :</span><span class="sxs-lookup"><span data-stu-id="cbd68-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="cbd68-108">Les autorisations accordées sont :</span><span class="sxs-lookup"><span data-stu-id="cbd68-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbd68-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cbd68-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cbd68-110">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-111">Lecture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="cbd68-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="cbd68-112">Écriture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="cbd68-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="cbd68-113">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="cbd68-114">Réplication des modifications d’annuaire</span><span class="sxs-lookup"><span data-stu-id="cbd68-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbd68-115">Objets serviceConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-116">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-117">Autorisations en lecture</span><span class="sxs-lookup"><span data-stu-id="cbd68-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="cbd68-118">Autorisations en écriture</span><span class="sxs-lookup"><span data-stu-id="cbd68-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="cbd68-119">Création de l’enfant</span><span class="sxs-lookup"><span data-stu-id="cbd68-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="cbd68-120">Suppression de l’enfant</span><span class="sxs-lookup"><span data-stu-id="cbd68-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="cbd68-121">Affichage du contenu</span><span class="sxs-lookup"><span data-stu-id="cbd68-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="cbd68-122">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-123">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-124">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbd68-125">Objets msRTCSIP-Server descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-126">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-127">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-128">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-129">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbd68-130">Objets msRTCSIP-WebComponents descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-131">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-132">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-133">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-134">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbd68-135">Objets msRTCSIP-MCU descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-136">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-137">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-138">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-139">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbd68-140">Objets msRTCSIP-MediationServer descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-141">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-142">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-143">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-144">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbd68-145">Objets msRTCSIP-ApplicationServer descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-146">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-147">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-148">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-149">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbd68-150">Objets msRTCSIP-ConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-151">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="cbd68-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-152">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-153">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="cbd68-154">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbd68-155">Objets Computer descendants</span><span class="sxs-lookup"><span data-stu-id="cbd68-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="cbd68-156">Accès particulier pour serviceConnectionPoint :</span><span class="sxs-lookup"><span data-stu-id="cbd68-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-157">Création d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="cbd68-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="cbd68-158">Suppression d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="cbd68-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="cbd68-159">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="cbd68-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="cbd68-160">Accès particulier pour les informations publiques :</span><span class="sxs-lookup"><span data-stu-id="cbd68-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-161">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="cbd68-162">Accès particulier pour le nom d’hôte DNS :</span><span class="sxs-lookup"><span data-stu-id="cbd68-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbd68-163">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="cbd68-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

