---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924457"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="edd39-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="edd39-103">tblPrincipalType</span></span>
 
<span data-ttu-id="edd39-104">tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="edd39-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="edd39-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="edd39-105">**Columns**</span></span>

|<span data-ttu-id="edd39-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="edd39-106">**Column**</span></span>|<span data-ttu-id="edd39-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="edd39-107">**Type**</span></span>|<span data-ttu-id="edd39-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="edd39-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="edd39-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="edd39-109">ptypeID</span></span>  <br/> |<span data-ttu-id="edd39-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="edd39-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="edd39-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="edd39-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="edd39-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="edd39-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="edd39-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="edd39-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="edd39-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="edd39-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="edd39-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="edd39-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="edd39-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="edd39-116">bit, not null</span></span>  <br/> |<span data-ttu-id="edd39-117">True si le type correspond aux principaux qui sont utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="edd39-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="edd39-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="edd39-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="edd39-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="edd39-119">bit, not null</span></span>  <br/> |<span data-ttu-id="edd39-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edd39-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="edd39-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="edd39-121">**Key**</span></span>

|<span data-ttu-id="edd39-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="edd39-122">**Column**</span></span>|<span data-ttu-id="edd39-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="edd39-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edd39-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="edd39-124">ptypeID</span></span>  <br/> |<span data-ttu-id="edd39-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="edd39-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="edd39-126">**Valeurs principales**</span><span class="sxs-lookup"><span data-stu-id="edd39-126">**Principal Values**</span></span>

|<span data-ttu-id="edd39-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="edd39-127">**ID**</span></span>|<span data-ttu-id="edd39-128">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="edd39-128">**Role**</span></span>|<span data-ttu-id="edd39-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="edd39-129">**Description**</span></span>|<span data-ttu-id="edd39-130">**User**</span><span class="sxs-lookup"><span data-stu-id="edd39-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="edd39-131">1</span><span class="sxs-lookup"><span data-stu-id="edd39-131">1</span></span>  <br/> |<span data-ttu-id="edd39-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="edd39-132">Any</span></span>  <br/> |<span data-ttu-id="edd39-133">Entité de sécurité générique avec aucun type connu.</span><span class="sxs-lookup"><span data-stu-id="edd39-133">Generic principal with no known type.</span></span> <span data-ttu-id="edd39-134">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="edd39-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="edd39-135">2</span><span class="sxs-lookup"><span data-stu-id="edd39-135">2</span></span>  <br/> |<span data-ttu-id="edd39-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="edd39-136">AnyUser</span></span>  <br/> |<span data-ttu-id="edd39-137">Entité de sécurité générique de type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edd39-137">Generic principal of user type.</span></span> <span data-ttu-id="edd39-138">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="edd39-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="edd39-139">Oui</span><span class="sxs-lookup"><span data-stu-id="edd39-139">Yes</span></span>  <br/> |
|<span data-ttu-id="edd39-140">3</span><span class="sxs-lookup"><span data-stu-id="edd39-140">3</span></span>  <br/> |<span data-ttu-id="edd39-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="edd39-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="edd39-142">Entité de sécurité générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="edd39-142">Generic principal with group semantic.</span></span> <span data-ttu-id="edd39-143">Pas utilisée dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="edd39-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="edd39-144">4</span><span class="sxs-lookup"><span data-stu-id="edd39-144">4</span></span>  <br/> |<span data-ttu-id="edd39-145">Système</span><span class="sxs-lookup"><span data-stu-id="edd39-145">SystemUser</span></span>  <br/> |<span data-ttu-id="edd39-146">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="edd39-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="edd39-147">5</span><span class="sxs-lookup"><span data-stu-id="edd39-147">5</span></span>  <br/> |<span data-ttu-id="edd39-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="edd39-148">User</span></span>  <br/> |<span data-ttu-id="edd39-149">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="edd39-149">Regular user.</span></span>  <br/> |<span data-ttu-id="edd39-150">Oui</span><span class="sxs-lookup"><span data-stu-id="edd39-150">Yes</span></span>  <br/> |
|<span data-ttu-id="edd39-151">8</span><span class="sxs-lookup"><span data-stu-id="edd39-151">8</span></span>  <br/> |<span data-ttu-id="edd39-152">CONTRÔLEUR DE DOMAINE</span><span class="sxs-lookup"><span data-stu-id="edd39-152">DC</span></span>  <br/> |<span data-ttu-id="edd39-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="edd39-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="edd39-154">9</span><span class="sxs-lookup"><span data-stu-id="edd39-154">9</span></span>  <br/> |<span data-ttu-id="edd39-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="edd39-155">Group</span></span>  <br/> |<span data-ttu-id="edd39-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="edd39-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="edd39-157">10</span><span class="sxs-lookup"><span data-stu-id="edd39-157">10</span></span>  <br/> |<span data-ttu-id="edd39-158">Dossier</span><span class="sxs-lookup"><span data-stu-id="edd39-158">Folder</span></span>  <br/> |<span data-ttu-id="edd39-159">Unité d’organisation ou conteneur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="edd39-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="edd39-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edd39-160">See also</span></span>

[<span data-ttu-id="edd39-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="edd39-161">tblPrincipal</span></span>](tblprincipal.md)
