---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues affectées aux nœuds.
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924926"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="3f15e-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="3f15e-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="3f15e-104">tblScopePrincipal contient les étendues affectées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="3f15e-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="3f15e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="3f15e-105">**Columns**</span></span>

|<span data-ttu-id="3f15e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3f15e-106">**Column**</span></span>|<span data-ttu-id="3f15e-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="3f15e-107">**Type**</span></span>|<span data-ttu-id="3f15e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="3f15e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f15e-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="3f15e-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="3f15e-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="3f15e-110">int, not null</span></span>  <br/> |<span data-ttu-id="3f15e-111">ID du nœud auquel s’applique à l’étendue.</span><span class="sxs-lookup"><span data-stu-id="3f15e-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="3f15e-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="3f15e-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="3f15e-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="3f15e-113">int, not null</span></span>  <br/> |<span data-ttu-id="3f15e-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="3f15e-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3f15e-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="3f15e-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="3f15e-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="3f15e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3f15e-117">True si le type d’étendue est Refuser ; False pour autoriser.</span><span class="sxs-lookup"><span data-stu-id="3f15e-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="3f15e-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="3f15e-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="3f15e-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="3f15e-119">int, not null</span></span>  <br/> |<span data-ttu-id="3f15e-120">ID du principal dernière mise à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="3f15e-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="3f15e-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="3f15e-121">**Keys**</span></span>

|<span data-ttu-id="3f15e-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3f15e-122">**Column**</span></span>|<span data-ttu-id="3f15e-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="3f15e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f15e-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="3f15e-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="3f15e-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3f15e-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3f15e-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="3f15e-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="3f15e-127">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="3f15e-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="3f15e-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="3f15e-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="3f15e-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="3f15e-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

