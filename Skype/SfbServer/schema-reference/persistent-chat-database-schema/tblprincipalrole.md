---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contient des rôles explicites attribués aux nœuds.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813362"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="39bf4-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="39bf4-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="39bf4-104">tblPrincipalRole contient des rôles explicites attribués aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="39bf4-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="39bf4-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="39bf4-105">**Columns**</span></span>

|<span data-ttu-id="39bf4-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="39bf4-106">**Column**</span></span>|<span data-ttu-id="39bf4-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="39bf4-107">**Type**</span></span>|<span data-ttu-id="39bf4-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="39bf4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39bf4-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="39bf4-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="39bf4-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="39bf4-110">int, not null</span></span>  <br/> |<span data-ttu-id="39bf4-111">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="39bf4-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="39bf4-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="39bf4-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="39bf4-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="39bf4-113">int, not null</span></span>  <br/> |<span data-ttu-id="39bf4-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="39bf4-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="39bf4-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="39bf4-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="39bf4-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="39bf4-116">int, not null</span></span>  <br/> |<span data-ttu-id="39bf4-117">ID du type de rôle (de tblRoleType)</span><span class="sxs-lookup"><span data-stu-id="39bf4-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="39bf4-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="39bf4-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="39bf4-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="39bf4-119">int, not null</span></span>  <br/> |<span data-ttu-id="39bf4-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="39bf4-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="39bf4-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="39bf4-121">**Keys**</span></span>

|<span data-ttu-id="39bf4-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="39bf4-122">**Column**</span></span>|<span data-ttu-id="39bf4-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="39bf4-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39bf4-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="39bf4-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="39bf4-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="39bf4-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39bf4-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="39bf4-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="39bf4-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="39bf4-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="39bf4-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="39bf4-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="39bf4-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="39bf4-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="39bf4-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="39bf4-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="39bf4-131">Clé étrangère avec recherche dans la table tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="39bf4-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

