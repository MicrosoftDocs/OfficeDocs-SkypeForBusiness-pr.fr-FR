---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814182"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="c9db3-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c9db3-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="c9db3-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.</span><span class="sxs-lookup"><span data-stu-id="c9db3-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="c9db3-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="c9db3-105">**Columns**</span></span>

|<span data-ttu-id="c9db3-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c9db3-106">**Column**</span></span>|<span data-ttu-id="c9db3-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c9db3-107">**Type**</span></span>|<span data-ttu-id="c9db3-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c9db3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9db3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c9db3-109">prinID</span></span>  <br/> |<span data-ttu-id="c9db3-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c9db3-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9db3-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="c9db3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c9db3-112">invID</span><span class="sxs-lookup"><span data-stu-id="c9db3-112">invID</span></span>  <br/> |<span data-ttu-id="c9db3-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c9db3-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9db3-114">Numéro séquentiel unique (par ID principal) généré à partir de la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="c9db3-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="c9db3-115">ID</span><span class="sxs-lookup"><span data-stu-id="c9db3-115">nodeID</span></span>  <br/> |<span data-ttu-id="c9db3-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="c9db3-116">int, not null</span></span>  <br/> |<span data-ttu-id="c9db3-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="c9db3-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="c9db3-118">Created</span><span class="sxs-lookup"><span data-stu-id="c9db3-118">createdOn</span></span>  <br/> |<span data-ttu-id="c9db3-119">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="c9db3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c9db3-120">Heure de création</span><span class="sxs-lookup"><span data-stu-id="c9db3-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="c9db3-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="c9db3-121">**Keys**</span></span>

|<span data-ttu-id="c9db3-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c9db3-122">**Column**</span></span>|<span data-ttu-id="c9db3-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="c9db3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9db3-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="c9db3-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="c9db3-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c9db3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9db3-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c9db3-126">prinID</span></span>  <br/> |<span data-ttu-id="c9db3-127">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="c9db3-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c9db3-128">ID</span><span class="sxs-lookup"><span data-stu-id="c9db3-128">nodeID</span></span>  <br/> |<span data-ttu-id="c9db3-129">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="c9db3-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

