---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831554"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="fa5be-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="fa5be-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="fa5be-104">La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="fa5be-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="fa5be-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="fa5be-105">**Columns**</span></span>

|<span data-ttu-id="fa5be-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fa5be-106">**Column**</span></span>|<span data-ttu-id="fa5be-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="fa5be-107">**Type**</span></span>|<span data-ttu-id="fa5be-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="fa5be-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa5be-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="fa5be-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="fa5be-110">entier, non null</span><span class="sxs-lookup"><span data-stu-id="fa5be-110">int, not null</span></span>  <br/> |<span data-ttu-id="fa5be-111">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="fa5be-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="fa5be-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="fa5be-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="fa5be-113">entier, non null</span><span class="sxs-lookup"><span data-stu-id="fa5be-113">int, not null</span></span>  <br/> |<span data-ttu-id="fa5be-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="fa5be-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fa5be-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="fa5be-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="fa5be-116">entier, non null</span><span class="sxs-lookup"><span data-stu-id="fa5be-116">int, not null</span></span>  <br/> |<span data-ttu-id="fa5be-117">ID du type de rôle (d’après tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="fa5be-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="fa5be-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="fa5be-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="fa5be-119">entier, non null</span><span class="sxs-lookup"><span data-stu-id="fa5be-119">int, not null</span></span>  <br/> |<span data-ttu-id="fa5be-120">ID du principal qui a mis à jour cette entrée en dernier.</span><span class="sxs-lookup"><span data-stu-id="fa5be-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="fa5be-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="fa5be-121">**Keys**</span></span>

|<span data-ttu-id="fa5be-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fa5be-122">**Column**</span></span>|<span data-ttu-id="fa5be-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="fa5be-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="fa5be-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="fa5be-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fa5be-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="fa5be-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="fa5be-126">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="fa5be-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="fa5be-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="fa5be-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="fa5be-128">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fa5be-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="fa5be-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="fa5be-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="fa5be-130">Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="fa5be-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

