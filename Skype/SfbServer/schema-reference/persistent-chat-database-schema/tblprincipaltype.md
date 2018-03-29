---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient les principaux types pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a><span data-ttu-id="9fec1-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="9fec1-103">tblPrincipalType</span></span>
 
<span data-ttu-id="9fec1-104">tblPrincipalType contient les principaux types pour classer les nouveautés dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9fec1-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="9fec1-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="9fec1-105">**Columns**</span></span>

|<span data-ttu-id="9fec1-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9fec1-106">**Column**</span></span>|<span data-ttu-id="9fec1-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="9fec1-107">**Type**</span></span>|<span data-ttu-id="9fec1-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="9fec1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9fec1-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="9fec1-109">ptypeID</span></span>  <br/> |<span data-ttu-id="9fec1-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="9fec1-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="9fec1-111">Code de type d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9fec1-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="9fec1-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="9fec1-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="9fec1-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="9fec1-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9fec1-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="9fec1-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="9fec1-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="9fec1-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="9fec1-116">bits, non null</span><span class="sxs-lookup"><span data-stu-id="9fec1-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9fec1-117">True si le type correspond aux entités qui sont utilisées à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="9fec1-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="9fec1-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="9fec1-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="9fec1-119">bits, non null</span><span class="sxs-lookup"><span data-stu-id="9fec1-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9fec1-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9fec1-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="9fec1-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="9fec1-121">**Key**</span></span>

|<span data-ttu-id="9fec1-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9fec1-122">**Column**</span></span>|<span data-ttu-id="9fec1-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="9fec1-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9fec1-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="9fec1-124">ptypeID</span></span>  <br/> |<span data-ttu-id="9fec1-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9fec1-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="9fec1-126">**Valeurs de l’entité de sécurité**</span><span class="sxs-lookup"><span data-stu-id="9fec1-126">**Principal Values**</span></span>

|<span data-ttu-id="9fec1-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="9fec1-127">**ID**</span></span>|<span data-ttu-id="9fec1-128">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="9fec1-128">**Role**</span></span>|<span data-ttu-id="9fec1-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="9fec1-129">**Description**</span></span>|<span data-ttu-id="9fec1-130">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9fec1-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fec1-131">1</span><span class="sxs-lookup"><span data-stu-id="9fec1-131">1</span></span>  <br/> |<span data-ttu-id="9fec1-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="9fec1-132">Any</span></span>  <br/> |<span data-ttu-id="9fec1-133">Entité de sécurité générique avec aucun type connu.</span><span class="sxs-lookup"><span data-stu-id="9fec1-133">Generic principal with no known type.</span></span> <span data-ttu-id="9fec1-134">Non utilisé dans la table de tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9fec1-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="9fec1-135">2</span><span class="sxs-lookup"><span data-stu-id="9fec1-135">2</span></span>  <br/> |<span data-ttu-id="9fec1-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="9fec1-136">AnyUser</span></span>  <br/> |<span data-ttu-id="9fec1-137">Entité de sécurité générique du type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9fec1-137">Generic principal of user type.</span></span> <span data-ttu-id="9fec1-138">Non utilisé dans la table de tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9fec1-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="9fec1-139">Oui</span><span class="sxs-lookup"><span data-stu-id="9fec1-139">Yes</span></span>  <br/> |
|<span data-ttu-id="9fec1-140">3</span><span class="sxs-lookup"><span data-stu-id="9fec1-140">3</span></span>  <br/> |<span data-ttu-id="9fec1-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="9fec1-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="9fec1-142">Entité de sécurité générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="9fec1-142">Generic principal with group semantic.</span></span> <span data-ttu-id="9fec1-143">Non utilisé dans la table de tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9fec1-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="9fec1-144">4</span><span class="sxs-lookup"><span data-stu-id="9fec1-144">4</span></span>  <br/> |<span data-ttu-id="9fec1-145">Utilisateur système</span><span class="sxs-lookup"><span data-stu-id="9fec1-145">SystemUser</span></span>  <br/> |<span data-ttu-id="9fec1-146">Entité utilisée en interne par le serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="9fec1-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="9fec1-147">5</span><span class="sxs-lookup"><span data-stu-id="9fec1-147">5</span></span>  <br/> |<span data-ttu-id="9fec1-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9fec1-148">User</span></span>  <br/> |<span data-ttu-id="9fec1-149">Utilisateur normal.</span><span class="sxs-lookup"><span data-stu-id="9fec1-149">Regular user.</span></span>  <br/> |<span data-ttu-id="9fec1-150">Oui</span><span class="sxs-lookup"><span data-stu-id="9fec1-150">Yes</span></span>  <br/> |
|<span data-ttu-id="9fec1-151">8</span><span class="sxs-lookup"><span data-stu-id="9fec1-151">8</span></span>  <br/> |<span data-ttu-id="9fec1-152">CONTRÔLEUR DE DOMAINE</span><span class="sxs-lookup"><span data-stu-id="9fec1-152">DC</span></span>  <br/> |<span data-ttu-id="9fec1-153">Contrôleur de domaine Active Directory des Services de domaine.</span><span class="sxs-lookup"><span data-stu-id="9fec1-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="9fec1-154">9</span><span class="sxs-lookup"><span data-stu-id="9fec1-154">9</span></span>  <br/> |<span data-ttu-id="9fec1-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="9fec1-155">Group</span></span>  <br/> |<span data-ttu-id="9fec1-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9fec1-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="9fec1-157">10</span><span class="sxs-lookup"><span data-stu-id="9fec1-157">10</span></span>  <br/> |<span data-ttu-id="9fec1-158">Dossier</span><span class="sxs-lookup"><span data-stu-id="9fec1-158">Folder</span></span>  <br/> |<span data-ttu-id="9fec1-159">Conteneur Active Directory ou l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="9fec1-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="9fec1-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9fec1-160">See also</span></span>

#### 

[<span data-ttu-id="9fec1-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="9fec1-161">tblPrincipal</span></span>](tblprincipal.md)

