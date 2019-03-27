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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881168"
---
# <a name="tblenumvalue"></a><span data-ttu-id="07555-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="07555-103">tblEnumValue</span></span>
 
<span data-ttu-id="07555-104">tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="07555-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="07555-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="07555-105">**Columns**</span></span>

|<span data-ttu-id="07555-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07555-106">**Column**</span></span>|<span data-ttu-id="07555-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="07555-107">**Type**</span></span>|<span data-ttu-id="07555-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="07555-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07555-109">valueID</span><span class="sxs-lookup"><span data-stu-id="07555-109">valueID</span></span>  <br/> |<span data-ttu-id="07555-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="07555-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="07555-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="07555-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="07555-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="07555-112">attributeID</span></span>  <br/> |<span data-ttu-id="07555-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="07555-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="07555-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="07555-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="07555-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="07555-115">attributeValue</span></span>  <br/> |<span data-ttu-id="07555-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="07555-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="07555-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="07555-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="07555-118">**Clés**</span><span class="sxs-lookup"><span data-stu-id="07555-118">**Keys**</span></span>

|<span data-ttu-id="07555-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="07555-119">**Column**</span></span>|<span data-ttu-id="07555-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="07555-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07555-121">valueID</span><span class="sxs-lookup"><span data-stu-id="07555-121">valueID</span></span>  <br/> |<span data-ttu-id="07555-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="07555-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="07555-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="07555-123">attributeID</span></span>  <br/> |<span data-ttu-id="07555-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="07555-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="07555-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="07555-125">**Table Values**</span></span>

|<span data-ttu-id="07555-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="07555-126">**valueID**</span></span>|<span data-ttu-id="07555-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="07555-127">**attributeID**</span></span>|<span data-ttu-id="07555-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="07555-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07555-129">2</span><span class="sxs-lookup"><span data-stu-id="07555-129">2</span></span>  <br/> |<span data-ttu-id="07555-130">1</span><span class="sxs-lookup"><span data-stu-id="07555-130">1</span></span>  <br/> |<span data-ttu-id="07555-131">privé</span><span class="sxs-lookup"><span data-stu-id="07555-131">private</span></span>  <br/> |
|<span data-ttu-id="07555-132">3</span><span class="sxs-lookup"><span data-stu-id="07555-132">3</span></span>  <br/> |<span data-ttu-id="07555-133">1</span><span class="sxs-lookup"><span data-stu-id="07555-133">1</span></span>  <br/> |<span data-ttu-id="07555-134">étendue</span><span class="sxs-lookup"><span data-stu-id="07555-134">scope</span></span>  <br/> |
|<span data-ttu-id="07555-135">4</span><span class="sxs-lookup"><span data-stu-id="07555-135">4</span></span>  <br/> |<span data-ttu-id="07555-136">2</span><span class="sxs-lookup"><span data-stu-id="07555-136">2</span></span>  <br/> |<span data-ttu-id="07555-137">normal</span><span class="sxs-lookup"><span data-stu-id="07555-137">normal</span></span>  <br/> |
|<span data-ttu-id="07555-138">5</span><span class="sxs-lookup"><span data-stu-id="07555-138">5</span></span>  <br/> |<span data-ttu-id="07555-139">2</span><span class="sxs-lookup"><span data-stu-id="07555-139">2</span></span>  <br/> |<span data-ttu-id="07555-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="07555-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="07555-141">6</span><span class="sxs-lookup"><span data-stu-id="07555-141">6</span></span>  <br/> |<span data-ttu-id="07555-142">1</span><span class="sxs-lookup"><span data-stu-id="07555-142">1</span></span>  <br/> |<span data-ttu-id="07555-143">Ouvrez</span><span class="sxs-lookup"><span data-stu-id="07555-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07555-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07555-144">See also</span></span>

[<span data-ttu-id="07555-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="07555-145">tblNode</span></span>](tblnode.md)
