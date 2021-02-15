---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831534"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="47f46-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="47f46-103">tblPrincipalType</span></span>
 
<span data-ttu-id="47f46-104">La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="47f46-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="47f46-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="47f46-105">**Columns**</span></span>

|<span data-ttu-id="47f46-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="47f46-106">**Column**</span></span>|<span data-ttu-id="47f46-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="47f46-107">**Type**</span></span>|<span data-ttu-id="47f46-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="47f46-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47f46-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="47f46-109">ptypeID</span></span>  <br/> |<span data-ttu-id="47f46-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="47f46-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="47f46-111">ID de type Principal.</span><span class="sxs-lookup"><span data-stu-id="47f46-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="47f46-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="47f46-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="47f46-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="47f46-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="47f46-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="47f46-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="47f46-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="47f46-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="47f46-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="47f46-116">bit, not null</span></span>  <br/> |<span data-ttu-id="47f46-117">Vrai si le type correspond aux principaux qui sont utilisés pour des fonctions internes.</span><span class="sxs-lookup"><span data-stu-id="47f46-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="47f46-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="47f46-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="47f46-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="47f46-119">bit, not null</span></span>  <br/> |<span data-ttu-id="47f46-120">Vrai si le type est un type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="47f46-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="47f46-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="47f46-121">**Key**</span></span>

|<span data-ttu-id="47f46-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="47f46-122">**Column**</span></span>|<span data-ttu-id="47f46-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="47f46-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="47f46-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="47f46-124">ptypeID</span></span>  <br/> |<span data-ttu-id="47f46-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="47f46-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="47f46-126">**Valeurs principales**</span><span class="sxs-lookup"><span data-stu-id="47f46-126">**Principal Values**</span></span>

|<span data-ttu-id="47f46-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="47f46-127">**ID**</span></span>|<span data-ttu-id="47f46-128">**Role**</span><span class="sxs-lookup"><span data-stu-id="47f46-128">**Role**</span></span>|<span data-ttu-id="47f46-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="47f46-129">**Description**</span></span>|<span data-ttu-id="47f46-130">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="47f46-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47f46-131">1 </span><span class="sxs-lookup"><span data-stu-id="47f46-131">1</span></span>  <br/> |<span data-ttu-id="47f46-132">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="47f46-132">Any</span></span>  <br/> |<span data-ttu-id="47f46-p101">Principal générique sans type connu. Inutilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="47f46-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="47f46-135">2 </span><span class="sxs-lookup"><span data-stu-id="47f46-135">2</span></span>  <br/> |<span data-ttu-id="47f46-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="47f46-136">AnyUser</span></span>  <br/> |<span data-ttu-id="47f46-p102">Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="47f46-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="47f46-139">Oui</span><span class="sxs-lookup"><span data-stu-id="47f46-139">Yes</span></span>  <br/> |
|<span data-ttu-id="47f46-140">3 </span><span class="sxs-lookup"><span data-stu-id="47f46-140">3</span></span>  <br/> |<span data-ttu-id="47f46-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="47f46-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="47f46-p103">Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="47f46-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="47f46-144">4 </span><span class="sxs-lookup"><span data-stu-id="47f46-144">4</span></span>  <br/> |<span data-ttu-id="47f46-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="47f46-145">SystemUser</span></span>  <br/> |<span data-ttu-id="47f46-146">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="47f46-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="47f46-147">5 </span><span class="sxs-lookup"><span data-stu-id="47f46-147">5</span></span>  <br/> |<span data-ttu-id="47f46-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="47f46-148">User</span></span>  <br/> |<span data-ttu-id="47f46-149">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="47f46-149">Regular user.</span></span>  <br/> |<span data-ttu-id="47f46-150">Oui</span><span class="sxs-lookup"><span data-stu-id="47f46-150">Yes</span></span>  <br/> |
|<span data-ttu-id="47f46-151">8 </span><span class="sxs-lookup"><span data-stu-id="47f46-151">8</span></span>  <br/> |<span data-ttu-id="47f46-152">DC</span><span class="sxs-lookup"><span data-stu-id="47f46-152">DC</span></span>  <br/> |<span data-ttu-id="47f46-153">Contrôleur de domaine des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47f46-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="47f46-154">9 </span><span class="sxs-lookup"><span data-stu-id="47f46-154">9</span></span>  <br/> |<span data-ttu-id="47f46-155">Group</span><span class="sxs-lookup"><span data-stu-id="47f46-155">Group</span></span>  <br/> |<span data-ttu-id="47f46-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47f46-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="47f46-157">10 </span><span class="sxs-lookup"><span data-stu-id="47f46-157">10</span></span>  <br/> |<span data-ttu-id="47f46-158">Folder</span><span class="sxs-lookup"><span data-stu-id="47f46-158">Folder</span></span>  <br/> |<span data-ttu-id="47f46-159">Conteneur ou unité d’organisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47f46-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="47f46-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47f46-160">See also</span></span>

[<span data-ttu-id="47f46-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="47f46-161">tblPrincipal</span></span>](tblprincipal.md)
