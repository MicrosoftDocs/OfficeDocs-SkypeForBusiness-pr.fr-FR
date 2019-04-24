---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour tous les nœuds d’invitation automatique activée.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212466"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="da6e3-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="da6e3-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="da6e3-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour tous les nœuds d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="da6e3-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="da6e3-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="da6e3-105">**Columns**</span></span>

|<span data-ttu-id="da6e3-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="da6e3-106">**Column**</span></span>|<span data-ttu-id="da6e3-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="da6e3-107">**Type**</span></span>|<span data-ttu-id="da6e3-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="da6e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da6e3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="da6e3-109">prinID</span></span>  <br/> |<span data-ttu-id="da6e3-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="da6e3-110">int, not null</span></span>  <br/> |<span data-ttu-id="da6e3-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="da6e3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="da6e3-112">invID</span><span class="sxs-lookup"><span data-stu-id="da6e3-112">invID</span></span>  <br/> |<span data-ttu-id="da6e3-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="da6e3-113">int, not null</span></span>  <br/> |<span data-ttu-id="da6e3-114">Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="da6e3-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="da6e3-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="da6e3-115">nodeID</span></span>  <br/> |<span data-ttu-id="da6e3-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="da6e3-116">int, not null</span></span>  <br/> |<span data-ttu-id="da6e3-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="da6e3-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="da6e3-118">Créé</span><span class="sxs-lookup"><span data-stu-id="da6e3-118">createdOn</span></span>  <br/> |<span data-ttu-id="da6e3-119">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="da6e3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="da6e3-120">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="da6e3-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="da6e3-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="da6e3-121">**Keys**</span></span>

|<span data-ttu-id="da6e3-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="da6e3-122">**Column**</span></span>|<span data-ttu-id="da6e3-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="da6e3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da6e3-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="da6e3-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="da6e3-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="da6e3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="da6e3-126">prinID</span><span class="sxs-lookup"><span data-stu-id="da6e3-126">prinID</span></span>  <br/> |<span data-ttu-id="da6e3-127">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="da6e3-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="da6e3-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="da6e3-128">nodeID</span></span>  <br/> |<span data-ttu-id="da6e3-129">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="da6e3-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

