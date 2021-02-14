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
# <a name="tblenumvalue"></a><span data-ttu-id="56859-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="56859-103">tblEnumValue</span></span>
 
<span data-ttu-id="56859-104">tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="56859-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="56859-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="56859-105">**Columns**</span></span>

|<span data-ttu-id="56859-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="56859-106">**Column**</span></span>|<span data-ttu-id="56859-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="56859-107">**Type**</span></span>|<span data-ttu-id="56859-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="56859-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56859-109">valueID</span><span class="sxs-lookup"><span data-stu-id="56859-109">valueID</span></span>  <br/> |<span data-ttu-id="56859-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="56859-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="56859-111">ID de la valeur</span><span class="sxs-lookup"><span data-stu-id="56859-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="56859-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="56859-112">attributeID</span></span>  <br/> |<span data-ttu-id="56859-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="56859-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="56859-114">ID de l’attribut</span><span class="sxs-lookup"><span data-stu-id="56859-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="56859-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="56859-115">attributeValue</span></span>  <br/> |<span data-ttu-id="56859-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="56859-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="56859-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="56859-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="56859-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="56859-118">**Keys**</span></span>

|<span data-ttu-id="56859-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="56859-119">**Column**</span></span>|<span data-ttu-id="56859-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="56859-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56859-121">valueID</span><span class="sxs-lookup"><span data-stu-id="56859-121">valueID</span></span>  <br/> |<span data-ttu-id="56859-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="56859-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="56859-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="56859-123">attributeID</span></span>  <br/> |<span data-ttu-id="56859-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="56859-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="56859-125">**Valeurs de la table**</span><span class="sxs-lookup"><span data-stu-id="56859-125">**Table Values**</span></span>

|<span data-ttu-id="56859-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="56859-126">**valueID**</span></span>|<span data-ttu-id="56859-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="56859-127">**attributeID**</span></span>|<span data-ttu-id="56859-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="56859-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56859-129">2 </span><span class="sxs-lookup"><span data-stu-id="56859-129">2</span></span>  <br/> |<span data-ttu-id="56859-130">1 </span><span class="sxs-lookup"><span data-stu-id="56859-130">1</span></span>  <br/> |<span data-ttu-id="56859-131">private</span><span class="sxs-lookup"><span data-stu-id="56859-131">private</span></span>  <br/> |
|<span data-ttu-id="56859-132">3 </span><span class="sxs-lookup"><span data-stu-id="56859-132">3</span></span>  <br/> |<span data-ttu-id="56859-133">1 </span><span class="sxs-lookup"><span data-stu-id="56859-133">1</span></span>  <br/> |<span data-ttu-id="56859-134">portée</span><span class="sxs-lookup"><span data-stu-id="56859-134">scope</span></span>  <br/> |
|<span data-ttu-id="56859-135">4 </span><span class="sxs-lookup"><span data-stu-id="56859-135">4</span></span>  <br/> |<span data-ttu-id="56859-136">2 </span><span class="sxs-lookup"><span data-stu-id="56859-136">2</span></span>  <br/> |<span data-ttu-id="56859-137">normal</span><span class="sxs-lookup"><span data-stu-id="56859-137">normal</span></span>  <br/> |
|<span data-ttu-id="56859-138">5 </span><span class="sxs-lookup"><span data-stu-id="56859-138">5</span></span>  <br/> |<span data-ttu-id="56859-139">2 </span><span class="sxs-lookup"><span data-stu-id="56859-139">2</span></span>  <br/> |<span data-ttu-id="56859-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="56859-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="56859-141">6 </span><span class="sxs-lookup"><span data-stu-id="56859-141">6</span></span>  <br/> |<span data-ttu-id="56859-142">1 </span><span class="sxs-lookup"><span data-stu-id="56859-142">1</span></span>  <br/> |<span data-ttu-id="56859-143">open</span><span class="sxs-lookup"><span data-stu-id="56859-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="56859-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56859-144">See also</span></span>

[<span data-ttu-id="56859-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="56859-145">tblNode</span></span>](tblnode.md)
