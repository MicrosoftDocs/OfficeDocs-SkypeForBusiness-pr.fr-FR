---
title: Modifications apportées au schéma dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et d’exploiter Skype Entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype Entreprise Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813574"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="b9cfc-104">Modifications apportées au schéma dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b9cfc-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="b9cfc-105">Avant de déployer et d’exploiter Skype Entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="b9cfc-106">Les extensions de schéma ajoutent les classes et attributs requis par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="b9cfc-107">Si vous faites une mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015, aucune modification de schéma n’est apportée et, par conséquent, cet article ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="b9cfc-108">Skype Entreprise Server nécessite plusieurs nouvelles classes et attributs et modifie certaines classes et attributs existants.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="b9cfc-109">En outre, de nombreuses informations de configuration pour Skype Entreprise Server sont stockées dans le magasin central de gestion et non dans AD DS comme dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="b9cfc-110">Les informations suivantes sont toujours stockées dans AD DS dans Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="b9cfc-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="b9cfc-111">**Extensions de schéma** :</span><span class="sxs-lookup"><span data-stu-id="b9cfc-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="b9cfc-112">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9cfc-112">User object extensions</span></span>
    
  - <span data-ttu-id="b9cfc-113">Extensions pour les classes afin de maintenir la compatibilité ascendante avec les versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="b9cfc-114">**Données** (stockées dans le schéma étendu Skype Entreprise Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="b9cfc-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="b9cfc-115">URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9cfc-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="b9cfc-116">Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="b9cfc-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="b9cfc-117">Pointeur vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="b9cfc-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="b9cfc-118">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="b9cfc-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="b9cfc-119">Cette rubrique décrit les modifications de schéma Active Directory requises par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="b9cfc-120">Il ne décrit pas les modifications de schéma introduites par les versions précédentes d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="b9cfc-121">Pour obtenir la liste des classes et leurs descriptions, voir Classes de schéma [et descriptions dans Skype Entreprise Server.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="b9cfc-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="b9cfc-122">Pour obtenir la liste des attributs et leurs descriptions, voir [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="b9cfc-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="b9cfc-123">Pour obtenir la liste des classes avec les attributs qu’elles peuvent contenir, voir Attributs de schéma par classe [dans Skype Entreprise Server.](schema-attributes-by-class.md)</span><span class="sxs-lookup"><span data-stu-id="b9cfc-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="b9cfc-124">Le préfixe msRTCSIP identifie les classes et les attributs spécifiques de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="b9cfc-125">Nouveaux attributs Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9cfc-125">New Active Directory Attributes</span></span>

<span data-ttu-id="b9cfc-126">Le tableau suivant décrit les attributs Active Directory ajoutés par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="b9cfc-127">**Attributs ajoutés par Skype Entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="b9cfc-128">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-128">**Attribute**</span></span>|<span data-ttu-id="b9cfc-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9cfc-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b9cfc-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="b9cfc-131">Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="b9cfc-132">Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="b9cfc-133">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="b9cfc-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b9cfc-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="b9cfc-p106">Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="b9cfc-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="b9cfc-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="b9cfc-138">Cet attribut est utilisé pour stocker le pool SQL Server miroir utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="b9cfc-139">Classes Active Directory modifiées</span><span class="sxs-lookup"><span data-stu-id="b9cfc-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="b9cfc-140">Le tableau suivant décrit les classes Active Directory modifiées par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9cfc-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="b9cfc-141">**Classes modifiées par Skype Entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="b9cfc-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-142">**Class**</span></span>|<span data-ttu-id="b9cfc-143">**Remplacez**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-143">**Change**</span></span>|<span data-ttu-id="b9cfc-144">**Classe ou attribut**</span><span class="sxs-lookup"><span data-stu-id="b9cfc-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9cfc-145">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9cfc-145">User</span></span>  <br/> |<span data-ttu-id="b9cfc-146">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-146">add: mayContain</span></span>  <br/> <span data-ttu-id="b9cfc-147">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="b9cfc-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b9cfc-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="b9cfc-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b9cfc-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="b9cfc-150">Contact</span><span class="sxs-lookup"><span data-stu-id="b9cfc-150">Contact</span></span>  <br/> |<span data-ttu-id="b9cfc-151">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-151">add: mayContain</span></span>  <br/> <span data-ttu-id="b9cfc-152">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="b9cfc-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b9cfc-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="b9cfc-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b9cfc-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="b9cfc-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="b9cfc-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="b9cfc-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="b9cfc-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b9cfc-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="b9cfc-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="b9cfc-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="b9cfc-159">ajouté : mayContain</span><span class="sxs-lookup"><span data-stu-id="b9cfc-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="b9cfc-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="b9cfc-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

