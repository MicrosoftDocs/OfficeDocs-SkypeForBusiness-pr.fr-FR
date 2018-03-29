---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contient le dernier ID d’invitation qui a été généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="d7f5e-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="d7f5e-103">tblLastInviteId</span></span>
 
<span data-ttu-id="d7f5e-104">tblLastInviteId contient le dernier ID d’invitation qui a été généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d7f5e-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="d7f5e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-105">**Columns**</span></span>

|<span data-ttu-id="d7f5e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-106">**Column**</span></span>|<span data-ttu-id="d7f5e-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-107">**Type**</span></span>|<span data-ttu-id="d7f5e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7f5e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d7f5e-109">prinID</span></span>  <br/> |<span data-ttu-id="d7f5e-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="d7f5e-110">int, not null</span></span>  <br/> |<span data-ttu-id="d7f5e-111">ID d’entité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d7f5e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d7f5e-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="d7f5e-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="d7f5e-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="d7f5e-113">int, not null</span></span>  <br/> |<span data-ttu-id="d7f5e-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="d7f5e-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="d7f5e-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-115">**Keys**</span></span>

|<span data-ttu-id="d7f5e-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-116">**Column**</span></span>|<span data-ttu-id="d7f5e-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7f5e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7f5e-118">prinID</span><span class="sxs-lookup"><span data-stu-id="d7f5e-118">prinID</span></span>  <br/> |<span data-ttu-id="d7f5e-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d7f5e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d7f5e-120">prinID</span><span class="sxs-lookup"><span data-stu-id="d7f5e-120">prinID</span></span>  <br/> |<span data-ttu-id="d7f5e-121">Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d7f5e-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d7f5e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7f5e-122">See also</span></span>

#### 

[<span data-ttu-id="d7f5e-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d7f5e-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

