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
ms.openlocfilehash: 8ec13a23daf0f3dae47ae0ce0dc630e64c596e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529411"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="a07ee-102">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a07ee-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a07ee-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a07ee-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a07ee-104">Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, permettant ainsi aux membres du groupe RTCUniversalServerAdmins de cette unité d’organisation d’installer Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="a07ee-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="a07ee-105">L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="a07ee-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="a07ee-106">Autorisations accordées aux objets dans l’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="a07ee-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a07ee-107">Les autorisations s’appliquent à :</span><span class="sxs-lookup"><span data-stu-id="a07ee-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="a07ee-108">Les autorisations accordées sont :</span><span class="sxs-lookup"><span data-stu-id="a07ee-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07ee-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a07ee-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a07ee-110">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-111">Lecture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="a07ee-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="a07ee-112">Écriture servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="a07ee-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="a07ee-113">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="a07ee-114">Réplication des modifications d’annuaire</span><span class="sxs-lookup"><span data-stu-id="a07ee-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07ee-115">Objets serviceConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-116">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-117">Autorisations en lecture</span><span class="sxs-lookup"><span data-stu-id="a07ee-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="a07ee-118">Autorisations en écriture</span><span class="sxs-lookup"><span data-stu-id="a07ee-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="a07ee-119">Création de l’enfant</span><span class="sxs-lookup"><span data-stu-id="a07ee-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="a07ee-120">Suppression de l’enfant</span><span class="sxs-lookup"><span data-stu-id="a07ee-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="a07ee-121">Affichage du contenu</span><span class="sxs-lookup"><span data-stu-id="a07ee-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="a07ee-122">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-123">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-124">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07ee-125">Objets msRTCSIP-Server descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-126">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-127">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-128">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-129">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07ee-130">Objets msRTCSIP-WebComponents descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-131">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-132">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-133">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-134">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07ee-135">Objets msRTCSIP-MCU descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-136">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-137">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-138">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-139">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07ee-140">Objets msRTCSIP-MediationServer descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-141">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-142">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-143">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-144">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07ee-145">Objets msRTCSIP-ApplicationServer descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-146">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-147">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-148">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-149">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07ee-150">Objets msRTCSIP-ConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-151">Accès particulier :</span><span class="sxs-lookup"><span data-stu-id="a07ee-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-152">Écriture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-153">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="a07ee-154">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07ee-155">Objets Computer descendants</span><span class="sxs-lookup"><span data-stu-id="a07ee-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="a07ee-156">Accès particulier pour serviceConnectionPoint :</span><span class="sxs-lookup"><span data-stu-id="a07ee-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-157">Création d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="a07ee-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="a07ee-158">Suppression d’objets enfants</span><span class="sxs-lookup"><span data-stu-id="a07ee-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="a07ee-159">Suppression de l’arborescence</span><span class="sxs-lookup"><span data-stu-id="a07ee-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="a07ee-160">Accès particulier pour les informations publiques :</span><span class="sxs-lookup"><span data-stu-id="a07ee-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-161">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="a07ee-162">Accès particulier pour le nom d’hôte DNS :</span><span class="sxs-lookup"><span data-stu-id="a07ee-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="a07ee-163">Lecture de propriété</span><span class="sxs-lookup"><span data-stu-id="a07ee-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

