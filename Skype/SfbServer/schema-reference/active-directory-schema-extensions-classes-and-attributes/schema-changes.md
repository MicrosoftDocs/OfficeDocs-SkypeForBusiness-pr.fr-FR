---
title: Modifications de schéma dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype pour Business Server.
ms.openlocfilehash: 5b6c3f036b1bc194331c721ea2d45564f0827d1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924842"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="9d3e3-104">Modifications de schéma dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9d3e3-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="9d3e3-105">Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="9d3e3-106">Les extensions de schéma ajoutent les classes et attributs requis par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3e3-107">Si vous mettez à niveau à partir de Lync Server 2013 Skype pour Business Server 2015, aucune modification de schéma n’apportées et par conséquent, cet article ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="9d3e3-108">Skype pour Business Server requiert plusieurs nouvelles classes et attributs et modifie certains attributs et les classes existantes.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="9d3e3-109">En outre, bien informations de configuration de Skype pour Business Server sont stockées dans le magasin Central de gestion et non dans AD DS que dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="9d3e3-110">Les informations suivantes sont toujours stockées dans AD DS dans Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="9d3e3-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="9d3e3-111">**Extensions de schéma**:</span><span class="sxs-lookup"><span data-stu-id="9d3e3-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="9d3e3-112">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="9d3e3-112">User object extensions</span></span>
    
  - <span data-ttu-id="9d3e3-113">Extensions pour les classes maintenir la compatibilité descendante avec les versions précédentes pris en charge de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="9d3e3-114">**Données** (stocké dans Skype pour le schéma étendu Business Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="9d3e3-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="9d3e3-115">Utilisateur SIP identificateur URI (Uniform Resource) et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="9d3e3-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="9d3e3-116">Objets contact pour les applications telles que le service Response Group et intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="9d3e3-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="9d3e3-117">Un pointeur vers le magasin Central de gestion</span><span class="sxs-lookup"><span data-stu-id="9d3e3-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="9d3e3-118">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="9d3e3-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="9d3e3-119">Cette rubrique décrit les modifications de schéma Active Directory requises par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="9d3e3-120">Il ne décrit pas les modifications de schéma qui ont été introduites par les versions précédentes d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="9d3e3-121">Pour obtenir la liste des classes et leurs descriptions, voir [classes de schéma et les descriptions de Skype pour Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="9d3e3-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="9d3e3-122">Pour obtenir la liste des attributs et leurs descriptions, voir [attributs de schéma et les descriptions de Skype pour Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="9d3e3-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="9d3e3-123">Pour obtenir la liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype pour Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="9d3e3-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="9d3e3-124">Le préfixe msRTCSIP identifie les classes et attributs spécifiques à Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="9d3e3-125">Nouveaux attributs Active Directory</span><span class="sxs-lookup"><span data-stu-id="9d3e3-125">New Active Directory Attributes</span></span>

<span data-ttu-id="9d3e3-126">Le tableau suivant décrit les attributs Active Directory qui sont ajoutés par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="9d3e3-127">**Attributs ajoutés par Skype pour Business Server**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="9d3e3-128">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-128">**Attribute**</span></span>|<span data-ttu-id="9d3e3-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d3e3-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="9d3e3-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="9d3e3-131">Cet attribut à valeurs multiples conserve les identificateurs pour contenir les stratégies qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="9d3e3-132">Maintenez les stratégies de conserver les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="9d3e3-133">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="9d3e3-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9d3e3-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="9d3e3-135">Il s’agit de la SIP routage ID de groupe.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="9d3e3-136">Les utilisateurs dans le même groupe inscrira sur le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="9d3e3-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="9d3e3-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="9d3e3-138">Cet attribut est utilisé pour stocker la mise en miroir principal SQL Server utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="9d3e3-139">Classes Active Directory modifiées</span><span class="sxs-lookup"><span data-stu-id="9d3e3-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="9d3e3-140">Le tableau suivant décrit les classes Active Directory qui sont modifiées par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d3e3-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="9d3e3-141">**Classes modifiées par Skype pour Business Server**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="9d3e3-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-142">**Class**</span></span>|<span data-ttu-id="9d3e3-143">**Modification**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-143">**Change**</span></span>|<span data-ttu-id="9d3e3-144">**Classe ou un attribut**</span><span class="sxs-lookup"><span data-stu-id="9d3e3-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d3e3-145">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9d3e3-145">User</span></span>  <br/> |<span data-ttu-id="9d3e3-146">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-146">add: mayContain</span></span>  <br/> <span data-ttu-id="9d3e3-147">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="9d3e3-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9d3e3-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="9d3e3-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9d3e3-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="9d3e3-150">Contact</span><span class="sxs-lookup"><span data-stu-id="9d3e3-150">Contact</span></span>  <br/> |<span data-ttu-id="9d3e3-151">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-151">add: mayContain</span></span>  <br/> <span data-ttu-id="9d3e3-152">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="9d3e3-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9d3e3-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="9d3e3-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9d3e3-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="9d3e3-155">Destinataire du message</span><span class="sxs-lookup"><span data-stu-id="9d3e3-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="9d3e3-156">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="9d3e3-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="9d3e3-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="9d3e3-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="9d3e3-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="9d3e3-159">ajouter : mayContain</span><span class="sxs-lookup"><span data-stu-id="9d3e3-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="9d3e3-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="9d3e3-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

