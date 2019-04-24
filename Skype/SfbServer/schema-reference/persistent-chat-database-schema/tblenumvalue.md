---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212879"
---
# <a name="tblenumvalue"></a><span data-ttu-id="c4aa9-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="c4aa9-103">tblEnumValue</span></span>
 
<span data-ttu-id="c4aa9-104">tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="c4aa9-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-105">**Columns**</span></span>

|<span data-ttu-id="c4aa9-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-106">**Column**</span></span>|<span data-ttu-id="c4aa9-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-107">**Type**</span></span>|<span data-ttu-id="c4aa9-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4aa9-109">valueID</span><span class="sxs-lookup"><span data-stu-id="c4aa9-109">valueID</span></span>  <br/> |<span data-ttu-id="c4aa9-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="c4aa9-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="c4aa9-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="c4aa9-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="c4aa9-112">attributeID</span></span>  <br/> |<span data-ttu-id="c4aa9-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="c4aa9-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="c4aa9-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="c4aa9-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="c4aa9-115">attributeValue</span></span>  <br/> |<span data-ttu-id="c4aa9-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="c4aa9-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c4aa9-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="c4aa9-118">**Clés**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-118">**Keys**</span></span>

|<span data-ttu-id="c4aa9-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-119">**Column**</span></span>|<span data-ttu-id="c4aa9-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4aa9-121">valueID</span><span class="sxs-lookup"><span data-stu-id="c4aa9-121">valueID</span></span>  <br/> |<span data-ttu-id="c4aa9-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c4aa9-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="c4aa9-123">attributeID</span></span>  <br/> |<span data-ttu-id="c4aa9-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="c4aa9-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="c4aa9-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-125">**Table Values**</span></span>

|<span data-ttu-id="c4aa9-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-126">**valueID**</span></span>|<span data-ttu-id="c4aa9-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-127">**attributeID**</span></span>|<span data-ttu-id="c4aa9-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="c4aa9-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4aa9-129">2</span><span class="sxs-lookup"><span data-stu-id="c4aa9-129">2</span></span>  <br/> |<span data-ttu-id="c4aa9-130">1</span><span class="sxs-lookup"><span data-stu-id="c4aa9-130">1</span></span>  <br/> |<span data-ttu-id="c4aa9-131">privé</span><span class="sxs-lookup"><span data-stu-id="c4aa9-131">private</span></span>  <br/> |
|<span data-ttu-id="c4aa9-132">3</span><span class="sxs-lookup"><span data-stu-id="c4aa9-132">3</span></span>  <br/> |<span data-ttu-id="c4aa9-133">1</span><span class="sxs-lookup"><span data-stu-id="c4aa9-133">1</span></span>  <br/> |<span data-ttu-id="c4aa9-134">étendue</span><span class="sxs-lookup"><span data-stu-id="c4aa9-134">scope</span></span>  <br/> |
|<span data-ttu-id="c4aa9-135">4</span><span class="sxs-lookup"><span data-stu-id="c4aa9-135">4</span></span>  <br/> |<span data-ttu-id="c4aa9-136">2</span><span class="sxs-lookup"><span data-stu-id="c4aa9-136">2</span></span>  <br/> |<span data-ttu-id="c4aa9-137">normal</span><span class="sxs-lookup"><span data-stu-id="c4aa9-137">normal</span></span>  <br/> |
|<span data-ttu-id="c4aa9-138">5</span><span class="sxs-lookup"><span data-stu-id="c4aa9-138">5</span></span>  <br/> |<span data-ttu-id="c4aa9-139">2</span><span class="sxs-lookup"><span data-stu-id="c4aa9-139">2</span></span>  <br/> |<span data-ttu-id="c4aa9-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="c4aa9-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="c4aa9-141">6</span><span class="sxs-lookup"><span data-stu-id="c4aa9-141">6</span></span>  <br/> |<span data-ttu-id="c4aa9-142">1</span><span class="sxs-lookup"><span data-stu-id="c4aa9-142">1</span></span>  <br/> |<span data-ttu-id="c4aa9-143">Ouvrez</span><span class="sxs-lookup"><span data-stu-id="c4aa9-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c4aa9-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4aa9-144">See also</span></span>

[<span data-ttu-id="c4aa9-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="c4aa9-145">tblNode</span></span>](tblnode.md)
