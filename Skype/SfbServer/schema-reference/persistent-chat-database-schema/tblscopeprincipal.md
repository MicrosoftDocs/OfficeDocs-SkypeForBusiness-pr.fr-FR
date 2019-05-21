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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues attribuées aux nœuds.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295194"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="e8d41-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="e8d41-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="e8d41-104">tblScopePrincipal contient les étendues attribuées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="e8d41-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="e8d41-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="e8d41-105">**Columns**</span></span>

|<span data-ttu-id="e8d41-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8d41-106">**Column**</span></span>|<span data-ttu-id="e8d41-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e8d41-107">**Type**</span></span>|<span data-ttu-id="e8d41-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8d41-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8d41-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="e8d41-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="e8d41-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e8d41-110">int, not null</span></span>  <br/> |<span data-ttu-id="e8d41-111">ID du nœud auquel s’applique l’étendue.</span><span class="sxs-lookup"><span data-stu-id="e8d41-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="e8d41-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="e8d41-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="e8d41-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e8d41-113">int, not null</span></span>  <br/> |<span data-ttu-id="e8d41-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="e8d41-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e8d41-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="e8d41-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="e8d41-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="e8d41-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e8d41-117">True si le type d’étendue est Deny; False si Allow.</span><span class="sxs-lookup"><span data-stu-id="e8d41-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="e8d41-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e8d41-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="e8d41-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e8d41-119">int, not null</span></span>  <br/> |<span data-ttu-id="e8d41-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="e8d41-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="e8d41-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="e8d41-121">**Keys**</span></span>

|<span data-ttu-id="e8d41-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8d41-122">**Column**</span></span>|<span data-ttu-id="e8d41-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8d41-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8d41-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="e8d41-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="e8d41-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e8d41-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e8d41-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="e8d41-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="e8d41-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="e8d41-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="e8d41-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="e8d41-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="e8d41-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="e8d41-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

