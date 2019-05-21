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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295292"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="5e6ba-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="5e6ba-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="5e6ba-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="5e6ba-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-105">**Columns**</span></span>

|<span data-ttu-id="5e6ba-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-106">**Column**</span></span>|<span data-ttu-id="5e6ba-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-107">**Type**</span></span>|<span data-ttu-id="5e6ba-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e6ba-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5e6ba-109">prinID</span></span>  <br/> |<span data-ttu-id="5e6ba-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5e6ba-110">int, not null</span></span>  <br/> |<span data-ttu-id="5e6ba-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5e6ba-112">invID</span><span class="sxs-lookup"><span data-stu-id="5e6ba-112">invID</span></span>  <br/> |<span data-ttu-id="5e6ba-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5e6ba-113">int, not null</span></span>  <br/> |<span data-ttu-id="5e6ba-114">Numéro séquentiel unique (par ID principal) généré à partir de la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="5e6ba-115">ID</span><span class="sxs-lookup"><span data-stu-id="5e6ba-115">nodeID</span></span>  <br/> |<span data-ttu-id="5e6ba-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="5e6ba-116">int, not null</span></span>  <br/> |<span data-ttu-id="5e6ba-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="5e6ba-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="5e6ba-118">Created</span><span class="sxs-lookup"><span data-stu-id="5e6ba-118">createdOn</span></span>  <br/> |<span data-ttu-id="5e6ba-119">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="5e6ba-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="5e6ba-120">Heure de création</span><span class="sxs-lookup"><span data-stu-id="5e6ba-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="5e6ba-121">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-121">**Keys**</span></span>

|<span data-ttu-id="5e6ba-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-122">**Column**</span></span>|<span data-ttu-id="5e6ba-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e6ba-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="5e6ba-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="5e6ba-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5e6ba-126">prinID</span><span class="sxs-lookup"><span data-stu-id="5e6ba-126">prinID</span></span>  <br/> |<span data-ttu-id="5e6ba-127">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5e6ba-128">ID</span><span class="sxs-lookup"><span data-stu-id="5e6ba-128">nodeID</span></span>  <br/> |<span data-ttu-id="5e6ba-129">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

