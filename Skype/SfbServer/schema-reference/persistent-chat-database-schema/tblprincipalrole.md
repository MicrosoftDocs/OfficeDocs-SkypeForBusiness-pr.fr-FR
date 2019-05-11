---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904180"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="b4059-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="b4059-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="b4059-104">la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="b4059-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="b4059-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="b4059-105">**Columns**</span></span>

|<span data-ttu-id="b4059-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4059-106">**Column**</span></span>|<span data-ttu-id="b4059-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4059-107">**Type**</span></span>|<span data-ttu-id="b4059-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b4059-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4059-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b4059-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b4059-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="b4059-110">int, not null</span></span>  <br/> |<span data-ttu-id="b4059-111">ID du nœud auquel le rôle s’applique à.</span><span class="sxs-lookup"><span data-stu-id="b4059-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="b4059-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b4059-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b4059-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="b4059-113">int, not null</span></span>  <br/> |<span data-ttu-id="b4059-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="b4059-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b4059-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b4059-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b4059-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="b4059-116">int, not null</span></span>  <br/> |<span data-ttu-id="b4059-117">ID de type de rôle (d’après tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="b4059-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="b4059-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b4059-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="b4059-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="b4059-119">int, not null</span></span>  <br/> |<span data-ttu-id="b4059-120">ID du principal dernière mise à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="b4059-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b4059-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="b4059-121">**Keys**</span></span>

|<span data-ttu-id="b4059-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4059-122">**Column**</span></span>|<span data-ttu-id="b4059-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="b4059-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4059-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="b4059-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="b4059-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b4059-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b4059-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b4059-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b4059-127">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b4059-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b4059-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b4059-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b4059-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b4059-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b4059-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b4059-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b4059-131">Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="b4059-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

