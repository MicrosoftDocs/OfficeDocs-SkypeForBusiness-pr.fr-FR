---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890768"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="bf2d3-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="bf2d3-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="bf2d3-104">la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="bf2d3-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-105">**Columns**</span></span>

|<span data-ttu-id="bf2d3-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-106">**Column**</span></span>|<span data-ttu-id="bf2d3-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-107">**Type**</span></span>|<span data-ttu-id="bf2d3-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf2d3-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="bf2d3-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf2d3-110">int, not null</span></span>  <br/> |<span data-ttu-id="bf2d3-111">ID du nœud auquel le rôle s’applique à.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="bf2d3-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="bf2d3-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf2d3-113">int, not null</span></span>  <br/> |<span data-ttu-id="bf2d3-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="bf2d3-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="bf2d3-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf2d3-116">int, not null</span></span>  <br/> |<span data-ttu-id="bf2d3-117">ID de type de rôle (d’après tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="bf2d3-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="bf2d3-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bf2d3-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="bf2d3-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="bf2d3-119">int, not null</span></span>  <br/> |<span data-ttu-id="bf2d3-120">ID du principal dernière mise à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="bf2d3-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-121">**Keys**</span></span>

|<span data-ttu-id="bf2d3-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-122">**Column**</span></span>|<span data-ttu-id="bf2d3-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="bf2d3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf2d3-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="bf2d3-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="bf2d3-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bf2d3-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="bf2d3-127">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="bf2d3-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="bf2d3-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="bf2d3-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bf2d3-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="bf2d3-131">Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="bf2d3-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

