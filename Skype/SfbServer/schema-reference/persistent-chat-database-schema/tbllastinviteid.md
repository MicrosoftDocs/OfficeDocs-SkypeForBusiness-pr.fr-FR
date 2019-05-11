---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: la table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929902"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="b942f-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="b942f-103">tblLastInviteId</span></span>
 
<span data-ttu-id="b942f-104">la table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b942f-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="b942f-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="b942f-105">**Columns**</span></span>

|<span data-ttu-id="b942f-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b942f-106">**Column**</span></span>|<span data-ttu-id="b942f-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b942f-107">**Type**</span></span>|<span data-ttu-id="b942f-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b942f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b942f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b942f-109">prinID</span></span>  <br/> |<span data-ttu-id="b942f-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="b942f-110">int, not null</span></span>  <br/> |<span data-ttu-id="b942f-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="b942f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b942f-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="b942f-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="b942f-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="b942f-113">int, not null</span></span>  <br/> |<span data-ttu-id="b942f-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="b942f-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="b942f-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="b942f-115">**Keys**</span></span>

|<span data-ttu-id="b942f-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b942f-116">**Column**</span></span>|<span data-ttu-id="b942f-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="b942f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b942f-118">prinID</span><span class="sxs-lookup"><span data-stu-id="b942f-118">prinID</span></span>  <br/> |<span data-ttu-id="b942f-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b942f-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b942f-120">prinID</span><span class="sxs-lookup"><span data-stu-id="b942f-120">prinID</span></span>  <br/> |<span data-ttu-id="b942f-121">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b942f-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b942f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b942f-122">See also</span></span>

[<span data-ttu-id="b942f-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b942f-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
