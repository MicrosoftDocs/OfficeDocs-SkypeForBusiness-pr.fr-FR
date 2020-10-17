---
title: 'Lync Server 2013 : modifications de schéma dans Lync Server 2013'
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
ms.openlocfilehash: 1c3733eee90fb1ea0bb3e0a67be88243dee56aa7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510781"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="e6a51-102">Modifications apportées au schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a51-102">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a51-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e6a51-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e6a51-104">Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="e6a51-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="e6a51-105">Les extensions de schéma ajoutent les classes et attributs requis par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6a51-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="e6a51-106">Lync Server 2013 nécessite plusieurs nouvelles classes et attributs et modifie des classes et des attributs existants.</span><span class="sxs-lookup"><span data-stu-id="e6a51-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="e6a51-107">En outre, la plupart des informations de configuration pour Lync Server 2013 sont stockées dans le magasin central de gestion et non dans AD DS comme dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="e6a51-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="e6a51-108">Les informations suivantes sont toujours stockées dans les services de domaine Active Directory (AD DS) dans Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="e6a51-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="e6a51-109">**Extensions de schéma** :</span><span class="sxs-lookup"><span data-stu-id="e6a51-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="e6a51-110">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6a51-110">User object extensions</span></span>
    
      - <span data-ttu-id="e6a51-111">Extensions pour les classes Office Communications Server 2007 et Office Communications Server 2007 R2 pour assurer la compatibilité descendante avec les versions précédentes prises en charge</span><span class="sxs-lookup"><span data-stu-id="e6a51-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="e6a51-112">**Données** (stockées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="e6a51-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="e6a51-113">URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6a51-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="e6a51-114">Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="e6a51-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="e6a51-115">Pointeur vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="e6a51-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="e6a51-116">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="e6a51-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="e6a51-117">Cette rubrique décrit les modifications apportées au schéma Active Directory requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6a51-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="e6a51-118">Il ne décrit pas les modifications de schéma qui ont été introduites par des versions antérieures d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="e6a51-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="e6a51-119">Pour obtenir la liste des classes et leur description, voir [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="e6a51-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="e6a51-120">Pour obtenir la liste des attributs et de leurs descriptions, voir [attributs et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="e6a51-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="e6a51-121">Pour obtenir la liste des classes avec les attributs qu’elles peuvent contenir, voir [Schema Attributes by Class dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="e6a51-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="e6a51-122">Le préfixe msRTCSIP identifie les classes et les attributs spécifiques à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6a51-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="e6a51-123">Nouveaux attributs Active Directory</span><span class="sxs-lookup"><span data-stu-id="e6a51-123">New Active Directory Attributes</span></span>

<span data-ttu-id="e6a51-124">Le tableau suivant décrit les attributs Active Directory ajoutés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6a51-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="e6a51-125">Attributs ajoutés par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a51-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6a51-126">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6a51-126">Attribute</span></span></th>
<th><span data-ttu-id="e6a51-127">Description</span><span class="sxs-lookup"><span data-stu-id="e6a51-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6a51-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e6a51-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="e6a51-129">Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e6a51-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="e6a51-130">Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="e6a51-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="e6a51-131">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e6a51-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a51-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e6a51-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="e6a51-p105">Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e6a51-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a51-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e6a51-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e6a51-136">Cet attribut est utilisé pour stocker le serveur principal SQL Server mis en miroir utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="e6a51-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="e6a51-137">Classes Active Directory modifiées</span><span class="sxs-lookup"><span data-stu-id="e6a51-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="e6a51-138">Le tableau suivant décrit les classes Active Directory qui sont modifiées par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6a51-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="e6a51-139">Classes modifiées par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a51-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6a51-140">Class</span><span class="sxs-lookup"><span data-stu-id="e6a51-140">Class</span></span></th>
<th><span data-ttu-id="e6a51-141">Modification</span><span class="sxs-lookup"><span data-stu-id="e6a51-141">Change</span></span></th>
<th><span data-ttu-id="e6a51-142">Classe ou attribut</span><span class="sxs-lookup"><span data-stu-id="e6a51-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6a51-143">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6a51-143">User</span></span></p></td>
<td><p><span data-ttu-id="e6a51-144">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-144">add: mayContain</span></span></p>
<p><span data-ttu-id="e6a51-145">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="e6a51-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e6a51-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="e6a51-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e6a51-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a51-148">Contact</span><span class="sxs-lookup"><span data-stu-id="e6a51-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="e6a51-149">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-149">add: mayContain</span></span></p>
<p><span data-ttu-id="e6a51-150">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="e6a51-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e6a51-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="e6a51-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e6a51-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a51-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="e6a51-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="e6a51-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="e6a51-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e6a51-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a51-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="e6a51-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="e6a51-157">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="e6a51-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="e6a51-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e6a51-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

