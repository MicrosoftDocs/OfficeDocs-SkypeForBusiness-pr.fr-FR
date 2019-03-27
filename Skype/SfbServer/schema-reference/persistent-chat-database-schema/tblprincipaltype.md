---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887435"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="16cf2-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="16cf2-103">tblPrincipalType</span></span>
 
<span data-ttu-id="16cf2-104">tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="16cf2-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="16cf2-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="16cf2-105">**Columns**</span></span>

|<span data-ttu-id="16cf2-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16cf2-106">**Column**</span></span>|<span data-ttu-id="16cf2-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="16cf2-107">**Type**</span></span>|<span data-ttu-id="16cf2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="16cf2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16cf2-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="16cf2-109">ptypeID</span></span>  <br/> |<span data-ttu-id="16cf2-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="16cf2-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="16cf2-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="16cf2-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="16cf2-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="16cf2-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="16cf2-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="16cf2-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="16cf2-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="16cf2-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="16cf2-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="16cf2-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="16cf2-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="16cf2-116">bit, not null</span></span>  <br/> |<span data-ttu-id="16cf2-117">True si le type correspond aux principaux qui sont utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="16cf2-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="16cf2-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="16cf2-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="16cf2-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="16cf2-119">bit, not null</span></span>  <br/> |<span data-ttu-id="16cf2-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16cf2-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="16cf2-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="16cf2-121">**Key**</span></span>

|<span data-ttu-id="16cf2-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="16cf2-122">**Column**</span></span>|<span data-ttu-id="16cf2-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="16cf2-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16cf2-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="16cf2-124">ptypeID</span></span>  <br/> |<span data-ttu-id="16cf2-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="16cf2-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="16cf2-126">**Valeurs principales**</span><span class="sxs-lookup"><span data-stu-id="16cf2-126">**Principal Values**</span></span>

|<span data-ttu-id="16cf2-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="16cf2-127">**ID**</span></span>|<span data-ttu-id="16cf2-128">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="16cf2-128">**Role**</span></span>|<span data-ttu-id="16cf2-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="16cf2-129">**Description**</span></span>|<span data-ttu-id="16cf2-130">**User**</span><span class="sxs-lookup"><span data-stu-id="16cf2-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16cf2-131">1</span><span class="sxs-lookup"><span data-stu-id="16cf2-131">1</span></span>  <br/> |<span data-ttu-id="16cf2-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="16cf2-132">Any</span></span>  <br/> |<span data-ttu-id="16cf2-133">Entité de sécurité générique avec aucun type connu.</span><span class="sxs-lookup"><span data-stu-id="16cf2-133">Generic principal with no known type.</span></span> <span data-ttu-id="16cf2-134">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="16cf2-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="16cf2-135">2</span><span class="sxs-lookup"><span data-stu-id="16cf2-135">2</span></span>  <br/> |<span data-ttu-id="16cf2-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="16cf2-136">AnyUser</span></span>  <br/> |<span data-ttu-id="16cf2-137">Entité de sécurité générique de type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16cf2-137">Generic principal of user type.</span></span> <span data-ttu-id="16cf2-138">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="16cf2-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="16cf2-139">Oui</span><span class="sxs-lookup"><span data-stu-id="16cf2-139">Yes</span></span>  <br/> |
|<span data-ttu-id="16cf2-140">3</span><span class="sxs-lookup"><span data-stu-id="16cf2-140">3</span></span>  <br/> |<span data-ttu-id="16cf2-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="16cf2-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="16cf2-142">Entité de sécurité générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="16cf2-142">Generic principal with group semantic.</span></span> <span data-ttu-id="16cf2-143">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="16cf2-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="16cf2-144">4</span><span class="sxs-lookup"><span data-stu-id="16cf2-144">4</span></span>  <br/> |<span data-ttu-id="16cf2-145">Système</span><span class="sxs-lookup"><span data-stu-id="16cf2-145">SystemUser</span></span>  <br/> |<span data-ttu-id="16cf2-146">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="16cf2-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="16cf2-147">5</span><span class="sxs-lookup"><span data-stu-id="16cf2-147">5</span></span>  <br/> |<span data-ttu-id="16cf2-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="16cf2-148">User</span></span>  <br/> |<span data-ttu-id="16cf2-149">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="16cf2-149">Regular user.</span></span>  <br/> |<span data-ttu-id="16cf2-150">Oui</span><span class="sxs-lookup"><span data-stu-id="16cf2-150">Yes</span></span>  <br/> |
|<span data-ttu-id="16cf2-151">8</span><span class="sxs-lookup"><span data-stu-id="16cf2-151">8</span></span>  <br/> |<span data-ttu-id="16cf2-152">CONTRÔLEUR DE DOMAINE</span><span class="sxs-lookup"><span data-stu-id="16cf2-152">DC</span></span>  <br/> |<span data-ttu-id="16cf2-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="16cf2-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="16cf2-154">9</span><span class="sxs-lookup"><span data-stu-id="16cf2-154">9</span></span>  <br/> |<span data-ttu-id="16cf2-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="16cf2-155">Group</span></span>  <br/> |<span data-ttu-id="16cf2-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16cf2-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="16cf2-157">10</span><span class="sxs-lookup"><span data-stu-id="16cf2-157">10</span></span>  <br/> |<span data-ttu-id="16cf2-158">Dossier</span><span class="sxs-lookup"><span data-stu-id="16cf2-158">Folder</span></span>  <br/> |<span data-ttu-id="16cf2-159">Unité d’organisation ou conteneur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16cf2-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="16cf2-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16cf2-160">See also</span></span>

[<span data-ttu-id="16cf2-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="16cf2-161">tblPrincipal</span></span>](tblprincipal.md)
