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
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="39292-102">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39292-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39292-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="39292-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="39292-104">Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette UO d’installer Lync Server 2013 dans le dossier spécifié. domaine sans être membre du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="39292-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="39292-105">L’applet de commande **Grant-CsSetupPermission** accorde aux autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="39292-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="39292-106">Autorisations accordées aux objets dans l’unité d’organisation</span><span class="sxs-lookup"><span data-stu-id="39292-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39292-107">Les autorisations s’appliquent à :</span><span class="sxs-lookup"><span data-stu-id="39292-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="39292-108">Les autorisations accordées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="39292-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39292-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="39292-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="39292-110">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-111">Lire servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="39292-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="39292-112">Écrire le servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="39292-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="39292-113">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="39292-114">Répliquer les modifications de l’annuaire</span><span class="sxs-lookup"><span data-stu-id="39292-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39292-115">Objets serviceConnectionPoint descendants</span><span class="sxs-lookup"><span data-stu-id="39292-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="39292-116">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-117">Autorisations de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="39292-118">Autorisations d’écriture</span><span class="sxs-lookup"><span data-stu-id="39292-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="39292-119">Créer un enfant</span><span class="sxs-lookup"><span data-stu-id="39292-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="39292-120">Supprimer un enfant</span><span class="sxs-lookup"><span data-stu-id="39292-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="39292-121">Contenu de la liste</span><span class="sxs-lookup"><span data-stu-id="39292-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="39292-122">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-123">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-124">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39292-125">Objets enfants msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="39292-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="39292-126">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-127">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-128">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-129">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39292-130">Objets enfants msRTCSIP-webcomposants</span><span class="sxs-lookup"><span data-stu-id="39292-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="39292-131">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-132">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-133">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-134">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39292-135">Objets descendants msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="39292-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="39292-136">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-137">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-138">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-139">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39292-140">Objets MediationServer en descendant</span><span class="sxs-lookup"><span data-stu-id="39292-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="39292-141">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-142">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-143">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-144">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39292-145">Objets ApplicationServer en descendant</span><span class="sxs-lookup"><span data-stu-id="39292-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="39292-146">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-147">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-148">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-149">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39292-150">Objets descendants de msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="39292-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="39292-151">Accès spécial :</span><span class="sxs-lookup"><span data-stu-id="39292-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-152">Propriété Write</span><span class="sxs-lookup"><span data-stu-id="39292-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="39292-153">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="39292-154">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39292-155">Objets ordinateur descendants</span><span class="sxs-lookup"><span data-stu-id="39292-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="39292-156">Accès spécial pour serviceConnectionPoint :</span><span class="sxs-lookup"><span data-stu-id="39292-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-157">Créer des objets enfants</span><span class="sxs-lookup"><span data-stu-id="39292-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="39292-158">Supprimer des objets enfants</span><span class="sxs-lookup"><span data-stu-id="39292-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="39292-159">Supprimer l’arborescence</span><span class="sxs-lookup"><span data-stu-id="39292-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="39292-160">Accès spécial pour les informations publiques :</span><span class="sxs-lookup"><span data-stu-id="39292-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-161">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="39292-162">Accès spécial pour le nom d’hôte DNS :</span><span class="sxs-lookup"><span data-stu-id="39292-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="39292-163">Propriété de lecture</span><span class="sxs-lookup"><span data-stu-id="39292-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

