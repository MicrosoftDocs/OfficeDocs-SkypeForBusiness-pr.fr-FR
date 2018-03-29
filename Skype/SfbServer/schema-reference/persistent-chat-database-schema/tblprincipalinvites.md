---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs mis en service pour tous les nœuds avec auto-invitation sur.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="fda39-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="fda39-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="fda39-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs mis en service pour tous les nœuds avec auto-invitation sur.</span><span class="sxs-lookup"><span data-stu-id="fda39-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="fda39-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="fda39-105">**Columns**</span></span>

|<span data-ttu-id="fda39-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fda39-106">**Column**</span></span>|<span data-ttu-id="fda39-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="fda39-107">**Type**</span></span>|<span data-ttu-id="fda39-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="fda39-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fda39-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fda39-109">prinID</span></span>  <br/> |<span data-ttu-id="fda39-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="fda39-110">int, not null</span></span>  <br/> |<span data-ttu-id="fda39-111">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="fda39-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fda39-112">invID</span><span class="sxs-lookup"><span data-stu-id="fda39-112">invID</span></span>  <br/> |<span data-ttu-id="fda39-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="fda39-113">int, not null</span></span>  <br/> |<span data-ttu-id="fda39-114">Numéro séquentiel unique (par ID de l’entité de sécurité) généré à partir de la table de tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="fda39-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="fda39-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="fda39-115">nodeID</span></span>  <br/> |<span data-ttu-id="fda39-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="fda39-116">int, not null</span></span>  <br/> |<span data-ttu-id="fda39-117">ID de nœud (conversation).</span><span class="sxs-lookup"><span data-stu-id="fda39-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="fda39-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="fda39-118">createdOn</span></span>  <br/> |<span data-ttu-id="fda39-119">DateTime, non null</span><span class="sxs-lookup"><span data-stu-id="fda39-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="fda39-120">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="fda39-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="fda39-121">**Clés**</span><span class="sxs-lookup"><span data-stu-id="fda39-121">**Keys**</span></span>

|<span data-ttu-id="fda39-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fda39-122">**Column**</span></span>|<span data-ttu-id="fda39-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="fda39-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fda39-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="fda39-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="fda39-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="fda39-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fda39-126">prinID</span><span class="sxs-lookup"><span data-stu-id="fda39-126">prinID</span></span>  <br/> |<span data-ttu-id="fda39-127">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fda39-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="fda39-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="fda39-128">nodeID</span></span>  <br/> |<span data-ttu-id="fda39-129">Clé étrangère avec la recherche dans la table de tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="fda39-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

