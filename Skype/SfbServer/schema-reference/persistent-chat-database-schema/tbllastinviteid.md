---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: la table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873936"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="d6c28-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="d6c28-103">tblLastInviteId</span></span>
 
<span data-ttu-id="d6c28-104">la table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d6c28-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="d6c28-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d6c28-105">**Columns**</span></span>

|<span data-ttu-id="d6c28-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d6c28-106">**Column**</span></span>|<span data-ttu-id="d6c28-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d6c28-107">**Type**</span></span>|<span data-ttu-id="d6c28-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d6c28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6c28-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d6c28-109">prinID</span></span>  <br/> |<span data-ttu-id="d6c28-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="d6c28-110">int, not null</span></span>  <br/> |<span data-ttu-id="d6c28-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="d6c28-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d6c28-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="d6c28-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="d6c28-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="d6c28-113">int, not null</span></span>  <br/> |<span data-ttu-id="d6c28-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="d6c28-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="d6c28-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="d6c28-115">**Keys**</span></span>

|<span data-ttu-id="d6c28-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d6c28-116">**Column**</span></span>|<span data-ttu-id="d6c28-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d6c28-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6c28-118">prinID</span><span class="sxs-lookup"><span data-stu-id="d6c28-118">prinID</span></span>  <br/> |<span data-ttu-id="d6c28-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d6c28-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d6c28-120">prinID</span><span class="sxs-lookup"><span data-stu-id="d6c28-120">prinID</span></span>  <br/> |<span data-ttu-id="d6c28-121">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d6c28-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d6c28-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6c28-122">See also</span></span>

[<span data-ttu-id="d6c28-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d6c28-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
