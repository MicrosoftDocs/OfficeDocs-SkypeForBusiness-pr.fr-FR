---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295243"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="ea242-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="ea242-103">tblPrincipalType</span></span>
 
<span data-ttu-id="ea242-104">tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="ea242-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="ea242-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="ea242-105">**Columns**</span></span>

|<span data-ttu-id="ea242-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ea242-106">**Column**</span></span>|<span data-ttu-id="ea242-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="ea242-107">**Type**</span></span>|<span data-ttu-id="ea242-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ea242-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea242-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="ea242-109">ptypeID</span></span>  <br/> |<span data-ttu-id="ea242-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="ea242-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="ea242-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="ea242-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="ea242-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="ea242-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="ea242-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="ea242-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ea242-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="ea242-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="ea242-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="ea242-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="ea242-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="ea242-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ea242-117">True si le type correspond aux éléments principaux utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="ea242-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="ea242-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="ea242-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="ea242-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="ea242-119">bit, not null</span></span>  <br/> |<span data-ttu-id="ea242-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ea242-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="ea242-121">**Clé**</span><span class="sxs-lookup"><span data-stu-id="ea242-121">**Key**</span></span>

|<span data-ttu-id="ea242-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ea242-122">**Column**</span></span>|<span data-ttu-id="ea242-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="ea242-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea242-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="ea242-124">ptypeID</span></span>  <br/> |<span data-ttu-id="ea242-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ea242-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="ea242-126">**Valeurs principales**</span><span class="sxs-lookup"><span data-stu-id="ea242-126">**Principal Values**</span></span>

|<span data-ttu-id="ea242-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="ea242-127">**ID**</span></span>|<span data-ttu-id="ea242-128">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="ea242-128">**Role**</span></span>|<span data-ttu-id="ea242-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="ea242-129">**Description**</span></span>|<span data-ttu-id="ea242-130">**User**</span><span class="sxs-lookup"><span data-stu-id="ea242-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea242-131">1</span><span class="sxs-lookup"><span data-stu-id="ea242-131">1</span></span>  <br/> |<span data-ttu-id="ea242-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="ea242-132">Any</span></span>  <br/> |<span data-ttu-id="ea242-133">Principal générique sans type connu.</span><span class="sxs-lookup"><span data-stu-id="ea242-133">Generic principal with no known type.</span></span> <span data-ttu-id="ea242-134">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="ea242-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="ea242-135">2</span><span class="sxs-lookup"><span data-stu-id="ea242-135">2</span></span>  <br/> |<span data-ttu-id="ea242-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="ea242-136">AnyUser</span></span>  <br/> |<span data-ttu-id="ea242-137">Principal générique de type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ea242-137">Generic principal of user type.</span></span> <span data-ttu-id="ea242-138">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="ea242-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="ea242-139">Oui</span><span class="sxs-lookup"><span data-stu-id="ea242-139">Yes</span></span>  <br/> |
|<span data-ttu-id="ea242-140">3</span><span class="sxs-lookup"><span data-stu-id="ea242-140">3</span></span>  <br/> |<span data-ttu-id="ea242-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="ea242-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="ea242-142">Principal générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="ea242-142">Generic principal with group semantic.</span></span> <span data-ttu-id="ea242-143">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="ea242-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="ea242-144">4</span><span class="sxs-lookup"><span data-stu-id="ea242-144">4</span></span>  <br/> |<span data-ttu-id="ea242-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="ea242-145">SystemUser</span></span>  <br/> |<span data-ttu-id="ea242-146">Principal utilisé par le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="ea242-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="ea242-147">5</span><span class="sxs-lookup"><span data-stu-id="ea242-147">5</span></span>  <br/> |<span data-ttu-id="ea242-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ea242-148">User</span></span>  <br/> |<span data-ttu-id="ea242-149">Utilisateur ordinaire.</span><span class="sxs-lookup"><span data-stu-id="ea242-149">Regular user.</span></span>  <br/> |<span data-ttu-id="ea242-150">Oui</span><span class="sxs-lookup"><span data-stu-id="ea242-150">Yes</span></span>  <br/> |
|<span data-ttu-id="ea242-151">version8</span><span class="sxs-lookup"><span data-stu-id="ea242-151">8</span></span>  <br/> |<span data-ttu-id="ea242-152">CD</span><span class="sxs-lookup"><span data-stu-id="ea242-152">DC</span></span>  <br/> |<span data-ttu-id="ea242-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="ea242-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="ea242-154">09</span><span class="sxs-lookup"><span data-stu-id="ea242-154">9</span></span>  <br/> |<span data-ttu-id="ea242-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="ea242-155">Group</span></span>  <br/> |<span data-ttu-id="ea242-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ea242-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="ea242-157">0,10</span><span class="sxs-lookup"><span data-stu-id="ea242-157">10</span></span>  <br/> |<span data-ttu-id="ea242-158">Folder</span><span class="sxs-lookup"><span data-stu-id="ea242-158">Folder</span></span>  <br/> |<span data-ttu-id="ea242-159">Conteneur Active Directory ou unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="ea242-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="ea242-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea242-160">See also</span></span>

[<span data-ttu-id="ea242-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="ea242-161">tblPrincipal</span></span>](tblprincipal.md)
