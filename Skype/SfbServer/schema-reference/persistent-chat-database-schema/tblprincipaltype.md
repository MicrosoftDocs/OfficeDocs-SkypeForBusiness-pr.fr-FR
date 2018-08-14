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
description: tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505124"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="92d6a-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="92d6a-103">tblPrincipalType</span></span>
 
<span data-ttu-id="92d6a-104">tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="92d6a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="92d6a-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="92d6a-105">**Columns**</span></span>

|<span data-ttu-id="92d6a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="92d6a-106">**Column**</span></span>|<span data-ttu-id="92d6a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="92d6a-107">**Type**</span></span>|<span data-ttu-id="92d6a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="92d6a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92d6a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="92d6a-109">ptypeID</span></span>  <br/> |<span data-ttu-id="92d6a-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="92d6a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="92d6a-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="92d6a-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="92d6a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="92d6a-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="92d6a-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="92d6a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="92d6a-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="92d6a-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="92d6a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="92d6a-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="92d6a-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="92d6a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="92d6a-117">True si le type correspond aux principaux qui sont utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="92d6a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="92d6a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="92d6a-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="92d6a-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="92d6a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="92d6a-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92d6a-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="92d6a-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="92d6a-121">**Key**</span></span>

|<span data-ttu-id="92d6a-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="92d6a-122">**Column**</span></span>|<span data-ttu-id="92d6a-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="92d6a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="92d6a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="92d6a-124">ptypeID</span></span>  <br/> |<span data-ttu-id="92d6a-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="92d6a-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="92d6a-126">**Valeurs principales**</span><span class="sxs-lookup"><span data-stu-id="92d6a-126">**Principal Values**</span></span>

|<span data-ttu-id="92d6a-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="92d6a-127">**ID**</span></span>|<span data-ttu-id="92d6a-128">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="92d6a-128">**Role**</span></span>|<span data-ttu-id="92d6a-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="92d6a-129">**Description**</span></span>|<span data-ttu-id="92d6a-130">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="92d6a-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92d6a-131">1</span><span class="sxs-lookup"><span data-stu-id="92d6a-131">1</span></span>  <br/> |<span data-ttu-id="92d6a-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="92d6a-132">Any</span></span>  <br/> |<span data-ttu-id="92d6a-133">Entité de sécurité générique avec aucun type connu.</span><span class="sxs-lookup"><span data-stu-id="92d6a-133">Generic principal with no known type.</span></span> <span data-ttu-id="92d6a-134">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="92d6a-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="92d6a-135">2</span><span class="sxs-lookup"><span data-stu-id="92d6a-135">2</span></span>  <br/> |<span data-ttu-id="92d6a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="92d6a-136">AnyUser</span></span>  <br/> |<span data-ttu-id="92d6a-137">Entité de sécurité générique de type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92d6a-137">Generic principal of user type.</span></span> <span data-ttu-id="92d6a-138">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="92d6a-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="92d6a-139">Oui</span><span class="sxs-lookup"><span data-stu-id="92d6a-139">Yes</span></span>  <br/> |
|<span data-ttu-id="92d6a-140">3</span><span class="sxs-lookup"><span data-stu-id="92d6a-140">3</span></span>  <br/> |<span data-ttu-id="92d6a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="92d6a-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="92d6a-142">Entité de sécurité générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="92d6a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="92d6a-143">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="92d6a-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="92d6a-144">4</span><span class="sxs-lookup"><span data-stu-id="92d6a-144">4</span></span>  <br/> |<span data-ttu-id="92d6a-145">Système</span><span class="sxs-lookup"><span data-stu-id="92d6a-145">SystemUser</span></span>  <br/> |<span data-ttu-id="92d6a-146">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="92d6a-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="92d6a-147">5</span><span class="sxs-lookup"><span data-stu-id="92d6a-147">5</span></span>  <br/> |<span data-ttu-id="92d6a-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="92d6a-148">User</span></span>  <br/> |<span data-ttu-id="92d6a-149">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="92d6a-149">Regular user.</span></span>  <br/> |<span data-ttu-id="92d6a-150">Oui</span><span class="sxs-lookup"><span data-stu-id="92d6a-150">Yes</span></span>  <br/> |
|<span data-ttu-id="92d6a-151">8</span><span class="sxs-lookup"><span data-stu-id="92d6a-151">8</span></span>  <br/> |<span data-ttu-id="92d6a-152">CONTRÔLEUR DE DOMAINE</span><span class="sxs-lookup"><span data-stu-id="92d6a-152">DC</span></span>  <br/> |<span data-ttu-id="92d6a-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="92d6a-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="92d6a-154">9</span><span class="sxs-lookup"><span data-stu-id="92d6a-154">9</span></span>  <br/> |<span data-ttu-id="92d6a-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="92d6a-155">Group</span></span>  <br/> |<span data-ttu-id="92d6a-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92d6a-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="92d6a-157">10</span><span class="sxs-lookup"><span data-stu-id="92d6a-157">10</span></span>  <br/> |<span data-ttu-id="92d6a-158">Dossier</span><span class="sxs-lookup"><span data-stu-id="92d6a-158">Folder</span></span>  <br/> |<span data-ttu-id="92d6a-159">Unité d’organisation ou conteneur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92d6a-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="92d6a-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92d6a-160">See also</span></span>

[<span data-ttu-id="92d6a-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="92d6a-161">tblPrincipal</span></span>](tblprincipal.md)