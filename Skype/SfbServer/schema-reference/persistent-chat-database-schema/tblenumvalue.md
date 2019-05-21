---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295425"
---
# <a name="tblenumvalue"></a><span data-ttu-id="efba4-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="efba4-103">tblEnumValue</span></span>
 
<span data-ttu-id="efba4-104">tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.</span><span class="sxs-lookup"><span data-stu-id="efba4-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="efba4-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="efba4-105">**Columns**</span></span>

|<span data-ttu-id="efba4-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="efba4-106">**Column**</span></span>|<span data-ttu-id="efba4-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="efba4-107">**Type**</span></span>|<span data-ttu-id="efba4-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="efba4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="efba4-109">valueID</span><span class="sxs-lookup"><span data-stu-id="efba4-109">valueID</span></span>  <br/> |<span data-ttu-id="efba4-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="efba4-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="efba4-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="efba4-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="efba4-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="efba4-112">attributeID</span></span>  <br/> |<span data-ttu-id="efba4-113">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="efba4-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="efba4-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="efba4-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="efba4-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="efba4-115">attributeValue</span></span>  <br/> |<span data-ttu-id="efba4-116">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="efba4-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="efba4-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="efba4-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="efba4-118">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="efba4-118">**Keys**</span></span>

|<span data-ttu-id="efba4-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="efba4-119">**Column**</span></span>|<span data-ttu-id="efba4-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="efba4-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="efba4-121">valueID</span><span class="sxs-lookup"><span data-stu-id="efba4-121">valueID</span></span>  <br/> |<span data-ttu-id="efba4-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="efba4-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="efba4-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="efba4-123">attributeID</span></span>  <br/> |<span data-ttu-id="efba4-124">Clé étrangère avec recherche dans la table tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="efba4-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="efba4-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="efba4-125">**Table Values**</span></span>

|<span data-ttu-id="efba4-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="efba4-126">**valueID**</span></span>|<span data-ttu-id="efba4-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="efba4-127">**attributeID**</span></span>|<span data-ttu-id="efba4-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="efba4-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="efba4-129">2</span><span class="sxs-lookup"><span data-stu-id="efba4-129">2</span></span>  <br/> |<span data-ttu-id="efba4-130">1</span><span class="sxs-lookup"><span data-stu-id="efba4-130">1</span></span>  <br/> |<span data-ttu-id="efba4-131">privé</span><span class="sxs-lookup"><span data-stu-id="efba4-131">private</span></span>  <br/> |
|<span data-ttu-id="efba4-132">3</span><span class="sxs-lookup"><span data-stu-id="efba4-132">3</span></span>  <br/> |<span data-ttu-id="efba4-133">1</span><span class="sxs-lookup"><span data-stu-id="efba4-133">1</span></span>  <br/> |<span data-ttu-id="efba4-134">hors</span><span class="sxs-lookup"><span data-stu-id="efba4-134">scope</span></span>  <br/> |
|<span data-ttu-id="efba4-135">4</span><span class="sxs-lookup"><span data-stu-id="efba4-135">4</span></span>  <br/> |<span data-ttu-id="efba4-136">2</span><span class="sxs-lookup"><span data-stu-id="efba4-136">2</span></span>  <br/> |<span data-ttu-id="efba4-137">normalement</span><span class="sxs-lookup"><span data-stu-id="efba4-137">normal</span></span>  <br/> |
|<span data-ttu-id="efba4-138">5</span><span class="sxs-lookup"><span data-stu-id="efba4-138">5</span></span>  <br/> |<span data-ttu-id="efba4-139">2</span><span class="sxs-lookup"><span data-stu-id="efba4-139">2</span></span>  <br/> |<span data-ttu-id="efba4-140">Conférence</span><span class="sxs-lookup"><span data-stu-id="efba4-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="efba4-141">6</span><span class="sxs-lookup"><span data-stu-id="efba4-141">6</span></span>  <br/> |<span data-ttu-id="efba4-142">1</span><span class="sxs-lookup"><span data-stu-id="efba4-142">1</span></span>  <br/> |<span data-ttu-id="efba4-143">ouvre</span><span class="sxs-lookup"><span data-stu-id="efba4-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="efba4-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efba4-144">See also</span></span>

[<span data-ttu-id="efba4-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="efba4-145">tblNode</span></span>](tblnode.md)
