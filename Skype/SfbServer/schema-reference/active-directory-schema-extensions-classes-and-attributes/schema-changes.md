---
title: Modifications de schéma dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et d’utiliser Skype entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype entreprise Server.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815482"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="6d0b2-104">Modifications de schéma dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6d0b2-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="6d0b2-105">Avant de déployer et d’utiliser Skype entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="6d0b2-106">Les extensions de schéma ajoutent les classes et attributs requis par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="6d0b2-107">Si vous effectuez une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015, il n’y a aucune modification de schéma et c’est pourquoi cet article ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="6d0b2-108">Skype entreprise Server nécessite plusieurs nouvelles classes et attributs, et modifie les classes et attributs existants.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="6d0b2-109">De plus, de nombreuses informations de configuration pour Skype entreprise Server sont stockées dans le magasin de gestion central plutôt que dans AD DS comme dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="6d0b2-110">Les informations suivantes sont toujours stockées dans AD DS dans Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="6d0b2-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="6d0b2-111">**Extensions de schéma**:</span><span class="sxs-lookup"><span data-stu-id="6d0b2-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="6d0b2-112">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d0b2-112">User object extensions</span></span>
    
  - <span data-ttu-id="6d0b2-113">Extensions de classes permettant de maintenir la compatibilité descendante avec les versions précédentes de Lync Server prises en charge.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="6d0b2-114">**Données** (stockées dans le schéma étendu de Skype entreprise Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="6d0b2-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="6d0b2-115">URL (Uniform Resource Identifier) de l’utilisateur SIP et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d0b2-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="6d0b2-116">Objets de contact pour des applications telles que Response Group et attendant</span><span class="sxs-lookup"><span data-stu-id="6d0b2-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="6d0b2-117">Pointeur vers le magasin de gestion central</span><span class="sxs-lookup"><span data-stu-id="6d0b2-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="6d0b2-118">Compte d’authentification Kerberos (objet facultatif de l’ordinateur)</span><span class="sxs-lookup"><span data-stu-id="6d0b2-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="6d0b2-119">Cette rubrique décrit les modifications de schéma Active Directory requises par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="6d0b2-120">Elle ne décrit pas les modifications de schéma introduites par des versions antérieures d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="6d0b2-121">Pour obtenir la liste des classes et leurs descriptions, voir [classes et descriptions de schéma dans Skype entreprise Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6d0b2-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="6d0b2-122">Pour obtenir la liste des attributs et leur description, voir [attributs et descriptions de schéma dans Skype entreprise Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6d0b2-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="6d0b2-123">Pour obtenir la liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype entreprise Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="6d0b2-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="6d0b2-124">Le préfixe msRTCSIP identifie les classes et attributs spécifiques à Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="6d0b2-125">Nouveaux attributs Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d0b2-125">New Active Directory Attributes</span></span>

<span data-ttu-id="6d0b2-126">Le tableau suivant décrit les attributs Active Directory ajoutés par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="6d0b2-127">**Attributs ajoutés par Skype entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="6d0b2-128">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-128">**Attribute**</span></span>|<span data-ttu-id="6d0b2-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d0b2-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6d0b2-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="6d0b2-131">Cet attribut à plusieurs valeurs contient des identificateurs pour les stratégies de conservation qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="6d0b2-132">Les stratégies de blocage préservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la conservation.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="6d0b2-133">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="6d0b2-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6d0b2-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="6d0b2-135">Il s’agit de l’ID du groupe de routage SIP.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="6d0b2-136">Les utilisateurs du même groupe seront enregistrés sur le même serveur principal.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="6d0b2-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6d0b2-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="6d0b2-138">Cet attribut est utilisé pour stocker le serveur principal SQL Server utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="6d0b2-139">Classes Active Directory modifiées</span><span class="sxs-lookup"><span data-stu-id="6d0b2-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="6d0b2-140">Le tableau suivant décrit les classes Active Directory modifiées par Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6d0b2-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="6d0b2-141">**Classes modifiées par Skype entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="6d0b2-142">**Cours**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-142">**Class**</span></span>|<span data-ttu-id="6d0b2-143">**Modification**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-143">**Change**</span></span>|<span data-ttu-id="6d0b2-144">**Classe ou attribut**</span><span class="sxs-lookup"><span data-stu-id="6d0b2-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d0b2-145">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d0b2-145">User</span></span>  <br/> |<span data-ttu-id="6d0b2-146">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-146">add: mayContain</span></span>  <br/> <span data-ttu-id="6d0b2-147">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="6d0b2-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6d0b2-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="6d0b2-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6d0b2-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="6d0b2-150">Locuteur</span><span class="sxs-lookup"><span data-stu-id="6d0b2-150">Contact</span></span>  <br/> |<span data-ttu-id="6d0b2-151">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-151">add: mayContain</span></span>  <br/> <span data-ttu-id="6d0b2-152">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="6d0b2-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6d0b2-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="6d0b2-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6d0b2-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="6d0b2-155">Mail-destinataire</span><span class="sxs-lookup"><span data-stu-id="6d0b2-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="6d0b2-156">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="6d0b2-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6d0b2-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="6d0b2-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="6d0b2-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="6d0b2-159">Ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="6d0b2-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="6d0b2-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6d0b2-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

