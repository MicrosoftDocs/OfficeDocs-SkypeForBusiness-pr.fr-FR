---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816024"
---
# <a name="tblenumvalue"></a><span data-ttu-id="2a3ce-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="2a3ce-103">tblEnumValue</span></span>
 
<span data-ttu-id="2a3ce-104">tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="2a3ce-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="2a3ce-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-105">**Columns**</span></span>

|<span data-ttu-id="2a3ce-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-106">**Column**</span></span>|<span data-ttu-id="2a3ce-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-107">**Type**</span></span>|<span data-ttu-id="2a3ce-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a3ce-109">valueID</span><span class="sxs-lookup"><span data-stu-id="2a3ce-109">valueID</span></span>  <br/> |<span data-ttu-id="2a3ce-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="2a3ce-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="2a3ce-111">ID de la valeur</span><span class="sxs-lookup"><span data-stu-id="2a3ce-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="2a3ce-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="2a3ce-112">attributeID</span></span>  <br/> |<span data-ttu-id="2a3ce-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="2a3ce-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="2a3ce-114">ID de l’attribut</span><span class="sxs-lookup"><span data-stu-id="2a3ce-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="2a3ce-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="2a3ce-115">attributeValue</span></span>  <br/> |<span data-ttu-id="2a3ce-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="2a3ce-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2a3ce-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="2a3ce-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="2a3ce-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-118">**Keys**</span></span>

|<span data-ttu-id="2a3ce-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-119">**Column**</span></span>|<span data-ttu-id="2a3ce-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a3ce-121">valueID</span><span class="sxs-lookup"><span data-stu-id="2a3ce-121">valueID</span></span>  <br/> |<span data-ttu-id="2a3ce-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="2a3ce-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2a3ce-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="2a3ce-123">attributeID</span></span>  <br/> |<span data-ttu-id="2a3ce-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="2a3ce-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="2a3ce-125">**Valeurs de la table**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-125">**Table Values**</span></span>

|<span data-ttu-id="2a3ce-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-126">**valueID**</span></span>|<span data-ttu-id="2a3ce-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-127">**attributeID**</span></span>|<span data-ttu-id="2a3ce-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="2a3ce-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a3ce-129">2 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-129">2</span></span>  <br/> |<span data-ttu-id="2a3ce-130">1 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-130">1</span></span>  <br/> |<span data-ttu-id="2a3ce-131">private</span><span class="sxs-lookup"><span data-stu-id="2a3ce-131">private</span></span>  <br/> |
|<span data-ttu-id="2a3ce-132">3 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-132">3</span></span>  <br/> |<span data-ttu-id="2a3ce-133">1 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-133">1</span></span>  <br/> |<span data-ttu-id="2a3ce-134">portée</span><span class="sxs-lookup"><span data-stu-id="2a3ce-134">scope</span></span>  <br/> |
|<span data-ttu-id="2a3ce-135">4 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-135">4</span></span>  <br/> |<span data-ttu-id="2a3ce-136">2 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-136">2</span></span>  <br/> |<span data-ttu-id="2a3ce-137">normal</span><span class="sxs-lookup"><span data-stu-id="2a3ce-137">normal</span></span>  <br/> |
|<span data-ttu-id="2a3ce-138">5 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-138">5</span></span>  <br/> |<span data-ttu-id="2a3ce-139">2 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-139">2</span></span>  <br/> |<span data-ttu-id="2a3ce-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="2a3ce-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="2a3ce-141">6 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-141">6</span></span>  <br/> |<span data-ttu-id="2a3ce-142">1 </span><span class="sxs-lookup"><span data-stu-id="2a3ce-142">1</span></span>  <br/> |<span data-ttu-id="2a3ce-143">open</span><span class="sxs-lookup"><span data-stu-id="2a3ce-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2a3ce-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a3ce-144">See also</span></span>

[<span data-ttu-id="2a3ce-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="2a3ce-145">tblNode</span></span>](tblnode.md)
