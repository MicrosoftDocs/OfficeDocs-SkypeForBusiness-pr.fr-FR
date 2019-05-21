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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contient des rôles explicites attribués aux nœuds.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295236"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="73454-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="73454-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="73454-104">tblPrincipalRole contient des rôles explicites attribués aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="73454-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="73454-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="73454-105">**Columns**</span></span>

|<span data-ttu-id="73454-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="73454-106">**Column**</span></span>|<span data-ttu-id="73454-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="73454-107">**Type**</span></span>|<span data-ttu-id="73454-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="73454-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73454-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="73454-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="73454-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="73454-110">int, not null</span></span>  <br/> |<span data-ttu-id="73454-111">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="73454-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="73454-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="73454-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="73454-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="73454-113">int, not null</span></span>  <br/> |<span data-ttu-id="73454-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="73454-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="73454-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="73454-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="73454-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="73454-116">int, not null</span></span>  <br/> |<span data-ttu-id="73454-117">ID du type de rôle (de tblRoleType)</span><span class="sxs-lookup"><span data-stu-id="73454-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="73454-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="73454-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="73454-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="73454-119">int, not null</span></span>  <br/> |<span data-ttu-id="73454-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="73454-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="73454-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="73454-121">**Keys**</span></span>

|<span data-ttu-id="73454-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="73454-122">**Column**</span></span>|<span data-ttu-id="73454-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="73454-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73454-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="73454-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="73454-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="73454-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="73454-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="73454-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="73454-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="73454-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="73454-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="73454-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="73454-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="73454-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="73454-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="73454-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="73454-131">Clé étrangère avec recherche dans la table tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="73454-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

