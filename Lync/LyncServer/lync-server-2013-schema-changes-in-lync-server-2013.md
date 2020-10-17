---
title: 'Lync Server 2013 : modifications de schéma dans Lync Server 2013'
description: 'Lync Server 2013 : modifications de schéma dans Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557150"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="17333-103">Modifications apportées au schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17333-103">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17333-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="17333-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="17333-105">Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="17333-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="17333-106">Les extensions de schéma ajoutent les classes et attributs requis par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17333-106">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="17333-107">Lync Server 2013 nécessite plusieurs nouvelles classes et attributs et modifie des classes et des attributs existants.</span><span class="sxs-lookup"><span data-stu-id="17333-107">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="17333-108">En outre, la plupart des informations de configuration pour Lync Server 2013 sont stockées dans le magasin central de gestion et non dans AD DS comme dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="17333-108">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="17333-109">Les informations suivantes sont toujours stockées dans les services de domaine Active Directory (AD DS) dans Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="17333-109">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="17333-110">**Extensions de schéma** :</span><span class="sxs-lookup"><span data-stu-id="17333-110">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="17333-111">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="17333-111">User object extensions</span></span>
    
      - <span data-ttu-id="17333-112">Extensions pour les classes Office Communications Server 2007 et Office Communications Server 2007 R2 pour assurer la compatibilité descendante avec les versions précédentes prises en charge</span><span class="sxs-lookup"><span data-stu-id="17333-112">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="17333-113">**Données** (stockées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="17333-113">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="17333-114">URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="17333-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="17333-115">Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="17333-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="17333-116">Pointeur vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="17333-116">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="17333-117">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="17333-117">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="17333-118">Cette rubrique décrit les modifications apportées au schéma Active Directory requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17333-118">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="17333-119">Il ne décrit pas les modifications de schéma qui ont été introduites par des versions antérieures d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="17333-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="17333-120">Pour obtenir la liste des classes et leur description, voir [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="17333-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="17333-121">Pour obtenir la liste des attributs et de leurs descriptions, voir [attributs et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="17333-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="17333-122">Pour obtenir la liste des classes avec les attributs qu’elles peuvent contenir, voir [Schema Attributes by Class dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="17333-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="17333-123">Le préfixe msRTCSIP identifie les classes et les attributs spécifiques à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17333-123">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="17333-124">Nouveaux attributs Active Directory</span><span class="sxs-lookup"><span data-stu-id="17333-124">New Active Directory Attributes</span></span>

<span data-ttu-id="17333-125">Le tableau suivant décrit les attributs Active Directory ajoutés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17333-125">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="17333-126">Attributs ajoutés par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17333-126">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17333-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="17333-127">Attribute</span></span></th>
<th><span data-ttu-id="17333-128">Description</span><span class="sxs-lookup"><span data-stu-id="17333-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17333-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="17333-129">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="17333-130">Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="17333-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="17333-131">Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="17333-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="17333-132">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="17333-132">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17333-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="17333-133">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="17333-p105">Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="17333-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17333-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="17333-136">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="17333-137">Cet attribut est utilisé pour stocker le serveur principal SQL Server mis en miroir utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="17333-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="17333-138">Classes Active Directory modifiées</span><span class="sxs-lookup"><span data-stu-id="17333-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="17333-139">Le tableau suivant décrit les classes Active Directory qui sont modifiées par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17333-139">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="17333-140">Classes modifiées par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17333-140">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17333-141">Class</span><span class="sxs-lookup"><span data-stu-id="17333-141">Class</span></span></th>
<th><span data-ttu-id="17333-142">Modification</span><span class="sxs-lookup"><span data-stu-id="17333-142">Change</span></span></th>
<th><span data-ttu-id="17333-143">Classe ou attribut</span><span class="sxs-lookup"><span data-stu-id="17333-143">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17333-144">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="17333-144">User</span></span></p></td>
<td><p><span data-ttu-id="17333-145">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-145">add: mayContain</span></span></p>
<p><span data-ttu-id="17333-146">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-146">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="17333-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="17333-147">ProxyAddresses</span></span></p>
<p><span data-ttu-id="17333-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="17333-148">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17333-149">Contact</span><span class="sxs-lookup"><span data-stu-id="17333-149">Contact</span></span></p></td>
<td><p><span data-ttu-id="17333-150">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-150">add: mayContain</span></span></p>
<p><span data-ttu-id="17333-151">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-151">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="17333-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="17333-152">ProxyAddresses</span></span></p>
<p><span data-ttu-id="17333-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="17333-153">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17333-154">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="17333-154">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="17333-155">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-155">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="17333-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="17333-156">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17333-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="17333-157">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="17333-158">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="17333-158">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="17333-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="17333-159">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

