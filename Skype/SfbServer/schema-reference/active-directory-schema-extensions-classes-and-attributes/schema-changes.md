---
title: Modifications de schéma dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et les attributs qui sont requis par Skype pour Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="d92ee-104">Modifications de schéma dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="d92ee-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="d92ee-105">Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="d92ee-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="d92ee-106">Les extensions de schéma ajoutent les classes et les attributs qui sont requis par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="d92ee-107">Skype pour Business Server requiert plusieurs nouvelles classes et attributs et modifie certaines classes existantes et les attributs.</span><span class="sxs-lookup"><span data-stu-id="d92ee-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="d92ee-108">En outre, volume informations de configuration pour Skype pour Business Server sont stockées dans le magasin Central de gestion et non dans les services AD DS que dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="d92ee-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="d92ee-109">Les informations suivantes sont toujours stockées dans AD DS dans Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="d92ee-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="d92ee-110">**Extensions de schéma**:</span><span class="sxs-lookup"><span data-stu-id="d92ee-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="d92ee-111">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="d92ee-111">User object extensions</span></span>
    
  - <span data-ttu-id="d92ee-112">Extensions pour les classes assurer la compatibilité descendante avec les versions précédentes prises en charge de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="d92ee-113">**Données** (stockés dans Skype pour schéma étendu du serveur de l’entreprise et dans les classes de schéma existant) :</span><span class="sxs-lookup"><span data-stu-id="d92ee-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="d92ee-114">Utilisateur SIP identificateur URI (Uniform Resource) et autres paramètres de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d92ee-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="d92ee-115">Objets de contact pour les applications comme groupe de réponse et intendant</span><span class="sxs-lookup"><span data-stu-id="d92ee-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="d92ee-116">Pointeur vers le magasin Central de gestion</span><span class="sxs-lookup"><span data-stu-id="d92ee-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="d92ee-117">Compte d’authentification de Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="d92ee-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="d92ee-118">Cette rubrique décrit les modifications de schéma Active Directory requises par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="d92ee-119">Il ne décrit pas les modifications de schéma qui ont été introduites par les versions précédentes d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="d92ee-120">Pour obtenir une liste de classes et de leurs descriptions, voir [classes de schéma et de descriptions dans Skype pour Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="d92ee-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="d92ee-121">Pour obtenir une liste des attributs et leurs descriptions, voir [attributs de schéma et de descriptions dans Skype pour Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="d92ee-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="d92ee-122">Pour obtenir une liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype pour Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="d92ee-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="d92ee-123">Le préfixe de msRTCSIP identifie les classes et les attributs qui sont spécifiques à Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="d92ee-124">Nouveaux attributs d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="d92ee-124">New Active Directory Attributes</span></span>

<span data-ttu-id="d92ee-125">Le tableau suivant décrit les attributs Active Directory qui sont ajoutés par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="d92ee-126">**Attributs ajoutés par Skype pour Business Server**</span><span class="sxs-lookup"><span data-stu-id="d92ee-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="d92ee-127">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="d92ee-127">**Attribute**</span></span>|<span data-ttu-id="d92ee-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="d92ee-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d92ee-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d92ee-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="d92ee-130">Cet attribut à valeurs multiples conserve les identificateurs pour contiennent les stratégies qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d92ee-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="d92ee-131">Maintenez les stratégies de conserver des éléments de boîte aux lettres de l’utilisateur pendant toute la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="d92ee-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="d92ee-132">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d92ee-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="d92ee-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d92ee-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="d92ee-134">Il s’agit de l’ID de groupe de routage de SIP</span><span class="sxs-lookup"><span data-stu-id="d92ee-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="d92ee-135">Enregistrent les utilisateurs dans le même groupe sur le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d92ee-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="d92ee-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d92ee-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="d92ee-137">Cet attribut est utilisé pour stocker la mise en miroir back-end SQL Server utilisé par le pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="d92ee-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="d92ee-138">Classes de modification Active Directory</span><span class="sxs-lookup"><span data-stu-id="d92ee-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="d92ee-139">Le tableau suivant décrit les classes Active Directory qui sont modifiés par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d92ee-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="d92ee-140">**Classes modifiés par Skype pour Business Server**</span><span class="sxs-lookup"><span data-stu-id="d92ee-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="d92ee-141">**Classe**</span><span class="sxs-lookup"><span data-stu-id="d92ee-141">**Class**</span></span>|<span data-ttu-id="d92ee-142">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="d92ee-142">**Change**</span></span>|<span data-ttu-id="d92ee-143">**Classe ou un attribut**</span><span class="sxs-lookup"><span data-stu-id="d92ee-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d92ee-144">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="d92ee-144">User</span></span>  <br/> |<span data-ttu-id="d92ee-145">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-145">add: mayContain</span></span>  <br/> <span data-ttu-id="d92ee-146">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="d92ee-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d92ee-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="d92ee-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d92ee-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="d92ee-149">Contact</span><span class="sxs-lookup"><span data-stu-id="d92ee-149">Contact</span></span>  <br/> |<span data-ttu-id="d92ee-150">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-150">add: mayContain</span></span>  <br/> <span data-ttu-id="d92ee-151">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="d92ee-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d92ee-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="d92ee-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d92ee-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="d92ee-154">Destinataire du message</span><span class="sxs-lookup"><span data-stu-id="d92ee-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="d92ee-155">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="d92ee-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d92ee-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="d92ee-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="d92ee-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="d92ee-158">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="d92ee-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="d92ee-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d92ee-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

