---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues attribuées aux nœuds.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812442"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="45d8a-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="45d8a-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="45d8a-104">tblScopePrincipal contient les étendues attribuées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="45d8a-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="45d8a-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="45d8a-105">**Columns**</span></span>

|<span data-ttu-id="45d8a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="45d8a-106">**Column**</span></span>|<span data-ttu-id="45d8a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="45d8a-107">**Type**</span></span>|<span data-ttu-id="45d8a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="45d8a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45d8a-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="45d8a-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="45d8a-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d8a-110">int, not null</span></span>  <br/> |<span data-ttu-id="45d8a-111">ID du nœud auquel s’applique l’étendue.</span><span class="sxs-lookup"><span data-stu-id="45d8a-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="45d8a-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="45d8a-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="45d8a-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d8a-113">int, not null</span></span>  <br/> |<span data-ttu-id="45d8a-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="45d8a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="45d8a-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="45d8a-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="45d8a-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="45d8a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="45d8a-117">True si le type d’étendue est Deny ; False si Allow.</span><span class="sxs-lookup"><span data-stu-id="45d8a-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="45d8a-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="45d8a-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="45d8a-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d8a-119">int, not null</span></span>  <br/> |<span data-ttu-id="45d8a-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="45d8a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="45d8a-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="45d8a-121">**Keys**</span></span>

|<span data-ttu-id="45d8a-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="45d8a-122">**Column**</span></span>|<span data-ttu-id="45d8a-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="45d8a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45d8a-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="45d8a-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="45d8a-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="45d8a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="45d8a-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="45d8a-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="45d8a-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="45d8a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="45d8a-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="45d8a-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="45d8a-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="45d8a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

