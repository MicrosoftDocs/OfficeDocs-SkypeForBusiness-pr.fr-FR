---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929867"
---
# <a name="tblenumvalue"></a><span data-ttu-id="0402d-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="0402d-103">tblEnumValue</span></span>
 
<span data-ttu-id="0402d-104">tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="0402d-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="0402d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0402d-105">**Columns**</span></span>

|<span data-ttu-id="0402d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0402d-106">**Column**</span></span>|<span data-ttu-id="0402d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0402d-107">**Type**</span></span>|<span data-ttu-id="0402d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0402d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0402d-109">valueID</span><span class="sxs-lookup"><span data-stu-id="0402d-109">valueID</span></span>  <br/> |<span data-ttu-id="0402d-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="0402d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="0402d-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="0402d-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="0402d-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="0402d-112">attributeID</span></span>  <br/> |<span data-ttu-id="0402d-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="0402d-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="0402d-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="0402d-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="0402d-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0402d-115">attributeValue</span></span>  <br/> |<span data-ttu-id="0402d-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="0402d-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0402d-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="0402d-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="0402d-118">**Clés**</span><span class="sxs-lookup"><span data-stu-id="0402d-118">**Keys**</span></span>

|<span data-ttu-id="0402d-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0402d-119">**Column**</span></span>|<span data-ttu-id="0402d-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="0402d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0402d-121">valueID</span><span class="sxs-lookup"><span data-stu-id="0402d-121">valueID</span></span>  <br/> |<span data-ttu-id="0402d-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0402d-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0402d-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="0402d-123">attributeID</span></span>  <br/> |<span data-ttu-id="0402d-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="0402d-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="0402d-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="0402d-125">**Table Values**</span></span>

|<span data-ttu-id="0402d-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="0402d-126">**valueID**</span></span>|<span data-ttu-id="0402d-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="0402d-127">**attributeID**</span></span>|<span data-ttu-id="0402d-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="0402d-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0402d-129">2</span><span class="sxs-lookup"><span data-stu-id="0402d-129">2</span></span>  <br/> |<span data-ttu-id="0402d-130">1</span><span class="sxs-lookup"><span data-stu-id="0402d-130">1</span></span>  <br/> |<span data-ttu-id="0402d-131">privé</span><span class="sxs-lookup"><span data-stu-id="0402d-131">private</span></span>  <br/> |
|<span data-ttu-id="0402d-132">3</span><span class="sxs-lookup"><span data-stu-id="0402d-132">3</span></span>  <br/> |<span data-ttu-id="0402d-133">1</span><span class="sxs-lookup"><span data-stu-id="0402d-133">1</span></span>  <br/> |<span data-ttu-id="0402d-134">étendue</span><span class="sxs-lookup"><span data-stu-id="0402d-134">scope</span></span>  <br/> |
|<span data-ttu-id="0402d-135">4</span><span class="sxs-lookup"><span data-stu-id="0402d-135">4</span></span>  <br/> |<span data-ttu-id="0402d-136">2</span><span class="sxs-lookup"><span data-stu-id="0402d-136">2</span></span>  <br/> |<span data-ttu-id="0402d-137">normal</span><span class="sxs-lookup"><span data-stu-id="0402d-137">normal</span></span>  <br/> |
|<span data-ttu-id="0402d-138">5</span><span class="sxs-lookup"><span data-stu-id="0402d-138">5</span></span>  <br/> |<span data-ttu-id="0402d-139">2</span><span class="sxs-lookup"><span data-stu-id="0402d-139">2</span></span>  <br/> |<span data-ttu-id="0402d-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="0402d-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="0402d-141">6</span><span class="sxs-lookup"><span data-stu-id="0402d-141">6</span></span>  <br/> |<span data-ttu-id="0402d-142">1</span><span class="sxs-lookup"><span data-stu-id="0402d-142">1</span></span>  <br/> |<span data-ttu-id="0402d-143">Ouvrez</span><span class="sxs-lookup"><span data-stu-id="0402d-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0402d-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0402d-144">See also</span></span>

[<span data-ttu-id="0402d-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="0402d-145">tblNode</span></span>](tblnode.md)
