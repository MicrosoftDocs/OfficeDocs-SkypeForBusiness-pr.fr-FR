---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815854"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="d4b66-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d4b66-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="d4b66-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="d4b66-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="d4b66-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d4b66-105">**Columns**</span></span>

|<span data-ttu-id="d4b66-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d4b66-106">**Column**</span></span>|<span data-ttu-id="d4b66-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d4b66-107">**Type**</span></span>|<span data-ttu-id="d4b66-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d4b66-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4b66-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d4b66-109">prinID</span></span>  <br/> |<span data-ttu-id="d4b66-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="d4b66-110">int, not null</span></span>  <br/> |<span data-ttu-id="d4b66-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="d4b66-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d4b66-112">invID</span><span class="sxs-lookup"><span data-stu-id="d4b66-112">invID</span></span>  <br/> |<span data-ttu-id="d4b66-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="d4b66-113">int, not null</span></span>  <br/> |<span data-ttu-id="d4b66-114">Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="d4b66-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="d4b66-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d4b66-115">nodeID</span></span>  <br/> |<span data-ttu-id="d4b66-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="d4b66-116">int, not null</span></span>  <br/> |<span data-ttu-id="d4b66-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="d4b66-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="d4b66-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="d4b66-118">createdOn</span></span>  <br/> |<span data-ttu-id="d4b66-119">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="d4b66-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="d4b66-120">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="d4b66-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="d4b66-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="d4b66-121">**Keys**</span></span>

|<span data-ttu-id="d4b66-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d4b66-122">**Column**</span></span>|<span data-ttu-id="d4b66-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="d4b66-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="d4b66-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d4b66-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d4b66-125">prinID</span><span class="sxs-lookup"><span data-stu-id="d4b66-125">prinID</span></span>  <br/> |<span data-ttu-id="d4b66-126">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d4b66-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d4b66-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="d4b66-127">nodeID</span></span>  <br/> |<span data-ttu-id="d4b66-128">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="d4b66-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

