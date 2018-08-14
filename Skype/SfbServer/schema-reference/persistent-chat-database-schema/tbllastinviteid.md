---
title: table tblLastInviteId
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
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504851"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="8885e-103">table tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="8885e-103">tblLastInviteId</span></span>
 
<span data-ttu-id="8885e-104">la table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8885e-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="8885e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8885e-105">**Columns**</span></span>

|<span data-ttu-id="8885e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8885e-106">**Column**</span></span>|<span data-ttu-id="8885e-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="8885e-107">**Type**</span></span>|<span data-ttu-id="8885e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="8885e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8885e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8885e-109">prinID</span></span>  <br/> |<span data-ttu-id="8885e-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="8885e-110">int, not null</span></span>  <br/> |<span data-ttu-id="8885e-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="8885e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8885e-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="8885e-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="8885e-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="8885e-113">int, not null</span></span>  <br/> |<span data-ttu-id="8885e-114">Dernier ID d’invitation utilisé.</span><span class="sxs-lookup"><span data-stu-id="8885e-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="8885e-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="8885e-115">**Keys**</span></span>

|<span data-ttu-id="8885e-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8885e-116">**Column**</span></span>|<span data-ttu-id="8885e-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="8885e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8885e-118">prinID</span><span class="sxs-lookup"><span data-stu-id="8885e-118">prinID</span></span>  <br/> |<span data-ttu-id="8885e-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="8885e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8885e-120">prinID</span><span class="sxs-lookup"><span data-stu-id="8885e-120">prinID</span></span>  <br/> |<span data-ttu-id="8885e-121">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="8885e-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8885e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8885e-122">See also</span></span>

[<span data-ttu-id="8885e-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="8885e-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)