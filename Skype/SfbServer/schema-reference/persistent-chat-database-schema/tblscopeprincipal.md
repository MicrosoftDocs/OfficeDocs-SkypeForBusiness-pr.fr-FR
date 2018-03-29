---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues affectées aux nœuds.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="75c53-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="75c53-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="75c53-104">tblScopePrincipal contient les étendues affectées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="75c53-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="75c53-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="75c53-105">**Columns**</span></span>

|<span data-ttu-id="75c53-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="75c53-106">**Column**</span></span>|<span data-ttu-id="75c53-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="75c53-107">**Type**</span></span>|<span data-ttu-id="75c53-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="75c53-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75c53-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="75c53-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="75c53-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="75c53-110">int, not null</span></span>  <br/> |<span data-ttu-id="75c53-111">ID de nœud que l’étendue s’applique à.</span><span class="sxs-lookup"><span data-stu-id="75c53-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="75c53-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="75c53-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="75c53-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="75c53-113">int, not null</span></span>  <br/> |<span data-ttu-id="75c53-114">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="75c53-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="75c53-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="75c53-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="75c53-116">bits, non null</span><span class="sxs-lookup"><span data-stu-id="75c53-116">bit, not null</span></span>  <br/> |<span data-ttu-id="75c53-117">True si le type d’étendue est Refuser ; False si autoriser.</span><span class="sxs-lookup"><span data-stu-id="75c53-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="75c53-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="75c53-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="75c53-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="75c53-119">int, not null</span></span>  <br/> |<span data-ttu-id="75c53-120">ID de l’entité de dernière mise à jour de cette entrée.</span><span class="sxs-lookup"><span data-stu-id="75c53-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="75c53-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="75c53-121">**Keys**</span></span>

|<span data-ttu-id="75c53-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="75c53-122">**Column**</span></span>|<span data-ttu-id="75c53-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="75c53-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75c53-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="75c53-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="75c53-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="75c53-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="75c53-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="75c53-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="75c53-127">Clé étrangère avec la recherche dans la table de tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="75c53-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="75c53-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="75c53-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="75c53-129">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="75c53-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

