---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814572"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="50cc8-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="50cc8-103">tblLastInviteId</span></span>
 
<span data-ttu-id="50cc8-104">tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50cc8-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="50cc8-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="50cc8-105">**Columns**</span></span>

|<span data-ttu-id="50cc8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="50cc8-106">**Column**</span></span>|<span data-ttu-id="50cc8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="50cc8-107">**Type**</span></span>|<span data-ttu-id="50cc8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="50cc8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50cc8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="50cc8-109">prinID</span></span>  <br/> |<span data-ttu-id="50cc8-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="50cc8-110">int, not null</span></span>  <br/> |<span data-ttu-id="50cc8-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="50cc8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="50cc8-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="50cc8-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="50cc8-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="50cc8-113">int, not null</span></span>  <br/> |<span data-ttu-id="50cc8-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="50cc8-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="50cc8-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="50cc8-115">**Keys**</span></span>

|<span data-ttu-id="50cc8-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="50cc8-116">**Column**</span></span>|<span data-ttu-id="50cc8-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="50cc8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50cc8-118">prinID</span><span class="sxs-lookup"><span data-stu-id="50cc8-118">prinID</span></span>  <br/> |<span data-ttu-id="50cc8-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="50cc8-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="50cc8-120">prinID</span><span class="sxs-lookup"><span data-stu-id="50cc8-120">prinID</span></span>  <br/> |<span data-ttu-id="50cc8-121">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="50cc8-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="50cc8-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50cc8-122">See also</span></span>

[<span data-ttu-id="50cc8-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="50cc8-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
