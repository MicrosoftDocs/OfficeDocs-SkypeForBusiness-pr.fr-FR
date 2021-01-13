---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815964"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c97e3-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c97e3-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c97e3-104">La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c97e3-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c97e3-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c97e3-105">**Columns**</span></span>

|<span data-ttu-id="c97e3-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c97e3-106">**Column**</span></span>|<span data-ttu-id="c97e3-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c97e3-107">**Type**</span></span>|<span data-ttu-id="c97e3-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c97e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c97e3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c97e3-109">prinID</span></span>  <br/> |<span data-ttu-id="c97e3-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="c97e3-110">int, not null</span></span>  <br/> |<span data-ttu-id="c97e3-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="c97e3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c97e3-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c97e3-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c97e3-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="c97e3-113">int, not null</span></span>  <br/> |<span data-ttu-id="c97e3-114">ID d’invitation le plus récemment utilisé.</span><span class="sxs-lookup"><span data-stu-id="c97e3-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c97e3-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="c97e3-115">**Keys**</span></span>

|<span data-ttu-id="c97e3-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c97e3-116">**Column**</span></span>|<span data-ttu-id="c97e3-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="c97e3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c97e3-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c97e3-118">prinID</span></span>  <br/> |<span data-ttu-id="c97e3-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c97e3-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c97e3-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c97e3-120">prinID</span></span>  <br/> |<span data-ttu-id="c97e3-121">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c97e3-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c97e3-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c97e3-122">See also</span></span>

[<span data-ttu-id="c97e3-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c97e3-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
