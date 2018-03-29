---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est un tableau codé en dur qui contient les valeurs de visibilité et le comportement des attributs qui sont utilisés dans la table des nœuds.
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a><span data-ttu-id="d4ae6-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d4ae6-103">tblEnumValue</span></span>
 
<span data-ttu-id="d4ae6-104">tblEnumValue est un tableau codé en dur qui contient les valeurs de visibilité et le comportement des attributs qui sont utilisés dans la table des nœuds.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d4ae6-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-105">**Columns**</span></span>

|<span data-ttu-id="d4ae6-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-106">**Column**</span></span>|<span data-ttu-id="d4ae6-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-107">**Type**</span></span>|<span data-ttu-id="d4ae6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4ae6-109">valueID</span><span class="sxs-lookup"><span data-stu-id="d4ae6-109">valueID</span></span>  <br/> |<span data-ttu-id="d4ae6-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="d4ae6-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d4ae6-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="d4ae6-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="d4ae6-112">attributeID</span></span>  <br/> |<span data-ttu-id="d4ae6-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="d4ae6-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="d4ae6-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d4ae6-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d4ae6-115">attributeValue</span></span>  <br/> |<span data-ttu-id="d4ae6-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="d4ae6-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d4ae6-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="d4ae6-118">**Clés**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-118">**Keys**</span></span>

|<span data-ttu-id="d4ae6-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-119">**Column**</span></span>|<span data-ttu-id="d4ae6-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ae6-121">valueID</span><span class="sxs-lookup"><span data-stu-id="d4ae6-121">valueID</span></span>  <br/> |<span data-ttu-id="d4ae6-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d4ae6-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="d4ae6-123">attributeID</span></span>  <br/> |<span data-ttu-id="d4ae6-124">Clé étrangère avec la recherche dans la table de tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="d4ae6-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="d4ae6-125">**Valeurs de la table**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-125">**Table Values**</span></span>

|<span data-ttu-id="d4ae6-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-126">**valueID**</span></span>|<span data-ttu-id="d4ae6-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-127">**attributeID**</span></span>|<span data-ttu-id="d4ae6-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="d4ae6-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4ae6-129">2</span><span class="sxs-lookup"><span data-stu-id="d4ae6-129">2</span></span>  <br/> |<span data-ttu-id="d4ae6-130">1</span><span class="sxs-lookup"><span data-stu-id="d4ae6-130">1</span></span>  <br/> |<span data-ttu-id="d4ae6-131">privé</span><span class="sxs-lookup"><span data-stu-id="d4ae6-131">private</span></span>  <br/> |
|<span data-ttu-id="d4ae6-132">3</span><span class="sxs-lookup"><span data-stu-id="d4ae6-132">3</span></span>  <br/> |<span data-ttu-id="d4ae6-133">1</span><span class="sxs-lookup"><span data-stu-id="d4ae6-133">1</span></span>  <br/> |<span data-ttu-id="d4ae6-134">champ d’application</span><span class="sxs-lookup"><span data-stu-id="d4ae6-134">scope</span></span>  <br/> |
|<span data-ttu-id="d4ae6-135">4</span><span class="sxs-lookup"><span data-stu-id="d4ae6-135">4</span></span>  <br/> |<span data-ttu-id="d4ae6-136">2</span><span class="sxs-lookup"><span data-stu-id="d4ae6-136">2</span></span>  <br/> |<span data-ttu-id="d4ae6-137">normal</span><span class="sxs-lookup"><span data-stu-id="d4ae6-137">normal</span></span>  <br/> |
|<span data-ttu-id="d4ae6-138">5</span><span class="sxs-lookup"><span data-stu-id="d4ae6-138">5</span></span>  <br/> |<span data-ttu-id="d4ae6-139">2</span><span class="sxs-lookup"><span data-stu-id="d4ae6-139">2</span></span>  <br/> |<span data-ttu-id="d4ae6-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="d4ae6-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="d4ae6-141">6</span><span class="sxs-lookup"><span data-stu-id="d4ae6-141">6</span></span>  <br/> |<span data-ttu-id="d4ae6-142">1</span><span class="sxs-lookup"><span data-stu-id="d4ae6-142">1</span></span>  <br/> |<span data-ttu-id="d4ae6-143">ouvrir</span><span class="sxs-lookup"><span data-stu-id="d4ae6-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d4ae6-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4ae6-144">See also</span></span>

#### 

[<span data-ttu-id="d4ae6-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="d4ae6-145">tblNode</span></span>](tblnode.md)

