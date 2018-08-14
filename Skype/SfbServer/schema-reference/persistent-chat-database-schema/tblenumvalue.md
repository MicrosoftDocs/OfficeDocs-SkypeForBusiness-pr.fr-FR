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
description: tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505075"
---
# <a name="tblenumvalue"></a><span data-ttu-id="69616-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="69616-103">tblEnumValue</span></span>
 
<span data-ttu-id="69616-104">tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="69616-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="69616-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="69616-105">**Columns**</span></span>

|<span data-ttu-id="69616-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="69616-106">**Column**</span></span>|<span data-ttu-id="69616-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="69616-107">**Type**</span></span>|<span data-ttu-id="69616-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="69616-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69616-109">valueID</span><span class="sxs-lookup"><span data-stu-id="69616-109">valueID</span></span>  <br/> |<span data-ttu-id="69616-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="69616-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="69616-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="69616-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="69616-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="69616-112">attributeID</span></span>  <br/> |<span data-ttu-id="69616-113">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="69616-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="69616-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="69616-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="69616-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="69616-115">attributeValue</span></span>  <br/> |<span data-ttu-id="69616-116">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="69616-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="69616-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="69616-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="69616-118">**Clés**</span><span class="sxs-lookup"><span data-stu-id="69616-118">**Keys**</span></span>

|<span data-ttu-id="69616-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="69616-119">**Column**</span></span>|<span data-ttu-id="69616-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="69616-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="69616-121">valueID</span><span class="sxs-lookup"><span data-stu-id="69616-121">valueID</span></span>  <br/> |<span data-ttu-id="69616-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="69616-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="69616-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="69616-123">attributeID</span></span>  <br/> |<span data-ttu-id="69616-124">Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="69616-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="69616-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="69616-125">**Table Values**</span></span>

|<span data-ttu-id="69616-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="69616-126">**valueID**</span></span>|<span data-ttu-id="69616-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="69616-127">**attributeID**</span></span>|<span data-ttu-id="69616-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="69616-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69616-129">2</span><span class="sxs-lookup"><span data-stu-id="69616-129">2</span></span>  <br/> |<span data-ttu-id="69616-130">1</span><span class="sxs-lookup"><span data-stu-id="69616-130">1</span></span>  <br/> |<span data-ttu-id="69616-131">privé</span><span class="sxs-lookup"><span data-stu-id="69616-131">private</span></span>  <br/> |
|<span data-ttu-id="69616-132">3</span><span class="sxs-lookup"><span data-stu-id="69616-132">3</span></span>  <br/> |<span data-ttu-id="69616-133">1</span><span class="sxs-lookup"><span data-stu-id="69616-133">1</span></span>  <br/> |<span data-ttu-id="69616-134">étendue</span><span class="sxs-lookup"><span data-stu-id="69616-134">scope</span></span>  <br/> |
|<span data-ttu-id="69616-135">4</span><span class="sxs-lookup"><span data-stu-id="69616-135">4</span></span>  <br/> |<span data-ttu-id="69616-136">2</span><span class="sxs-lookup"><span data-stu-id="69616-136">2</span></span>  <br/> |<span data-ttu-id="69616-137">normal</span><span class="sxs-lookup"><span data-stu-id="69616-137">normal</span></span>  <br/> |
|<span data-ttu-id="69616-138">5</span><span class="sxs-lookup"><span data-stu-id="69616-138">5</span></span>  <br/> |<span data-ttu-id="69616-139">2</span><span class="sxs-lookup"><span data-stu-id="69616-139">2</span></span>  <br/> |<span data-ttu-id="69616-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="69616-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="69616-141">6</span><span class="sxs-lookup"><span data-stu-id="69616-141">6</span></span>  <br/> |<span data-ttu-id="69616-142">1</span><span class="sxs-lookup"><span data-stu-id="69616-142">1</span></span>  <br/> |<span data-ttu-id="69616-143">Ouvrez</span><span class="sxs-lookup"><span data-stu-id="69616-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="69616-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69616-144">See also</span></span>

[<span data-ttu-id="69616-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="69616-145">tblNode</span></span>](tblnode.md)