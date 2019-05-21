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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295355"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="d60c1-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="d60c1-103">tblLastInviteId</span></span>
 
<span data-ttu-id="d60c1-104">tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d60c1-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="d60c1-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="d60c1-105">**Columns**</span></span>

|<span data-ttu-id="d60c1-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d60c1-106">**Column**</span></span>|<span data-ttu-id="d60c1-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d60c1-107">**Type**</span></span>|<span data-ttu-id="d60c1-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d60c1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d60c1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d60c1-109">prinID</span></span>  <br/> |<span data-ttu-id="d60c1-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="d60c1-110">int, not null</span></span>  <br/> |<span data-ttu-id="d60c1-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="d60c1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d60c1-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="d60c1-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="d60c1-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="d60c1-113">int, not null</span></span>  <br/> |<span data-ttu-id="d60c1-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="d60c1-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="d60c1-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="d60c1-115">**Keys**</span></span>

|<span data-ttu-id="d60c1-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d60c1-116">**Column**</span></span>|<span data-ttu-id="d60c1-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d60c1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d60c1-118">prinID</span><span class="sxs-lookup"><span data-stu-id="d60c1-118">prinID</span></span>  <br/> |<span data-ttu-id="d60c1-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d60c1-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d60c1-120">prinID</span><span class="sxs-lookup"><span data-stu-id="d60c1-120">prinID</span></span>  <br/> |<span data-ttu-id="d60c1-121">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="d60c1-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d60c1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d60c1-122">See also</span></span>

[<span data-ttu-id="d60c1-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d60c1-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
