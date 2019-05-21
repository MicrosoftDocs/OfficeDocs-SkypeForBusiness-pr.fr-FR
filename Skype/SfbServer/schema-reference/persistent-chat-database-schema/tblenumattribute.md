---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295418"
---
# <a name="tblenumattribute"></a><span data-ttu-id="d932a-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="d932a-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="d932a-104">tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.</span><span class="sxs-lookup"><span data-stu-id="d932a-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d932a-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="d932a-105">**Columns**</span></span>

|<span data-ttu-id="d932a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d932a-106">**Column**</span></span>|<span data-ttu-id="d932a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d932a-107">**Type**</span></span>|<span data-ttu-id="d932a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d932a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d932a-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="d932a-109">attributeID</span></span>  <br/> |<span data-ttu-id="d932a-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="d932a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d932a-111">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="d932a-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d932a-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="d932a-112">attributeName</span></span>  <br/> |<span data-ttu-id="d932a-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="d932a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d932a-114">Nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="d932a-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="d932a-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d932a-115">**Key**</span></span>

|<span data-ttu-id="d932a-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d932a-116">**Column**</span></span>|<span data-ttu-id="d932a-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d932a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d932a-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="d932a-118">attributeID</span></span>  <br/> |<span data-ttu-id="d932a-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d932a-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="d932a-120">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="d932a-120">**Table Values**</span></span>

|<span data-ttu-id="d932a-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="d932a-121">**attributeID**</span></span>|<span data-ttu-id="d932a-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="d932a-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d932a-123">1</span><span class="sxs-lookup"><span data-stu-id="d932a-123">1</span></span>  <br/> |<span data-ttu-id="d932a-124">Notoriété.</span><span class="sxs-lookup"><span data-stu-id="d932a-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="d932a-125">2</span><span class="sxs-lookup"><span data-stu-id="d932a-125">2</span></span>  <br/> |<span data-ttu-id="d932a-126">Fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="d932a-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d932a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d932a-127">See also</span></span>

[<span data-ttu-id="d932a-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="d932a-128">tblNode</span></span>](tblnode.md)
