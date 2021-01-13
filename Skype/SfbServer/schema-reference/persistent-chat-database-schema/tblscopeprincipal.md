---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues assignées aux nœuds.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831514"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="9cb75-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="9cb75-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="9cb75-104">tblScopePrincipal contient les étendues assignées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="9cb75-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="9cb75-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9cb75-105">**Columns**</span></span>

|<span data-ttu-id="9cb75-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9cb75-106">**Column**</span></span>|<span data-ttu-id="9cb75-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cb75-107">**Type**</span></span>|<span data-ttu-id="9cb75-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="9cb75-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9cb75-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="9cb75-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="9cb75-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9cb75-110">int, not null</span></span>  <br/> |<span data-ttu-id="9cb75-111">ID du nœud auquel s’applique l’étendue.</span><span class="sxs-lookup"><span data-stu-id="9cb75-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="9cb75-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="9cb75-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="9cb75-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="9cb75-113">int, not null</span></span>  <br/> |<span data-ttu-id="9cb75-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="9cb75-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9cb75-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="9cb75-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="9cb75-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="9cb75-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9cb75-117">Valeur True si le type d’étendue est Refuser ; False pour Autoriser.</span><span class="sxs-lookup"><span data-stu-id="9cb75-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="9cb75-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9cb75-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="9cb75-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="9cb75-119">int, not null</span></span>  <br/> |<span data-ttu-id="9cb75-120">ID du principal qui a mis à jour cette entrée en dernier.</span><span class="sxs-lookup"><span data-stu-id="9cb75-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="9cb75-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="9cb75-121">**Keys**</span></span>

|<span data-ttu-id="9cb75-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9cb75-122">**Column**</span></span>|<span data-ttu-id="9cb75-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="9cb75-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="9cb75-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9cb75-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9cb75-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="9cb75-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="9cb75-126">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="9cb75-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="9cb75-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="9cb75-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="9cb75-128">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9cb75-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

