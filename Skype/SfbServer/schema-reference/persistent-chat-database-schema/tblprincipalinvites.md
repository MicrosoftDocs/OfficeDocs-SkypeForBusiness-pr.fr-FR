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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876689"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="40ee7-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="40ee7-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="40ee7-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour tous les nœuds d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="40ee7-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="40ee7-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="40ee7-105">**Columns**</span></span>

|<span data-ttu-id="40ee7-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="40ee7-106">**Column**</span></span>|<span data-ttu-id="40ee7-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="40ee7-107">**Type**</span></span>|<span data-ttu-id="40ee7-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="40ee7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40ee7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="40ee7-109">prinID</span></span>  <br/> |<span data-ttu-id="40ee7-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="40ee7-110">int, not null</span></span>  <br/> |<span data-ttu-id="40ee7-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="40ee7-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="40ee7-112">invID</span><span class="sxs-lookup"><span data-stu-id="40ee7-112">invID</span></span>  <br/> |<span data-ttu-id="40ee7-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="40ee7-113">int, not null</span></span>  <br/> |<span data-ttu-id="40ee7-114">Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="40ee7-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="40ee7-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="40ee7-115">nodeID</span></span>  <br/> |<span data-ttu-id="40ee7-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="40ee7-116">int, not null</span></span>  <br/> |<span data-ttu-id="40ee7-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="40ee7-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="40ee7-118">Créé</span><span class="sxs-lookup"><span data-stu-id="40ee7-118">createdOn</span></span>  <br/> |<span data-ttu-id="40ee7-119">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="40ee7-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="40ee7-120">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="40ee7-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="40ee7-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="40ee7-121">**Keys**</span></span>

|<span data-ttu-id="40ee7-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="40ee7-122">**Column**</span></span>|<span data-ttu-id="40ee7-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="40ee7-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40ee7-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="40ee7-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="40ee7-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="40ee7-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="40ee7-126">prinID</span><span class="sxs-lookup"><span data-stu-id="40ee7-126">prinID</span></span>  <br/> |<span data-ttu-id="40ee7-127">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="40ee7-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="40ee7-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="40ee7-128">nodeID</span></span>  <br/> |<span data-ttu-id="40ee7-129">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="40ee7-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

