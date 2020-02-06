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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814602"
---
# <a name="tblenumvalue"></a><span data-ttu-id="cc107-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="cc107-103">tblEnumValue</span></span>
 
<span data-ttu-id="cc107-104">tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.</span><span class="sxs-lookup"><span data-stu-id="cc107-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="cc107-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="cc107-105">**Columns**</span></span>

|<span data-ttu-id="cc107-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cc107-106">**Column**</span></span>|<span data-ttu-id="cc107-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc107-107">**Type**</span></span>|<span data-ttu-id="cc107-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="cc107-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc107-109">valueID</span><span class="sxs-lookup"><span data-stu-id="cc107-109">valueID</span></span>  <br/> |<span data-ttu-id="cc107-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="cc107-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="cc107-111">ID de la valeur.</span><span class="sxs-lookup"><span data-stu-id="cc107-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="cc107-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="cc107-112">attributeID</span></span>  <br/> |<span data-ttu-id="cc107-113">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="cc107-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="cc107-114">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="cc107-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="cc107-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="cc107-115">attributeValue</span></span>  <br/> |<span data-ttu-id="cc107-116">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="cc107-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="cc107-117">Nom de la valeur.</span><span class="sxs-lookup"><span data-stu-id="cc107-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="cc107-118">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="cc107-118">**Keys**</span></span>

|<span data-ttu-id="cc107-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cc107-119">**Column**</span></span>|<span data-ttu-id="cc107-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="cc107-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc107-121">valueID</span><span class="sxs-lookup"><span data-stu-id="cc107-121">valueID</span></span>  <br/> |<span data-ttu-id="cc107-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="cc107-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cc107-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="cc107-123">attributeID</span></span>  <br/> |<span data-ttu-id="cc107-124">Clé étrangère avec recherche dans la table tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="cc107-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="cc107-125">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="cc107-125">**Table Values**</span></span>

|<span data-ttu-id="cc107-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="cc107-126">**valueID**</span></span>|<span data-ttu-id="cc107-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="cc107-127">**attributeID**</span></span>|<span data-ttu-id="cc107-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="cc107-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc107-129">deuxième</span><span class="sxs-lookup"><span data-stu-id="cc107-129">2</span></span>  <br/> |<span data-ttu-id="cc107-130">1</span><span class="sxs-lookup"><span data-stu-id="cc107-130">1</span></span>  <br/> |<span data-ttu-id="cc107-131">privé</span><span class="sxs-lookup"><span data-stu-id="cc107-131">private</span></span>  <br/> |
|<span data-ttu-id="cc107-132">3</span><span class="sxs-lookup"><span data-stu-id="cc107-132">3</span></span>  <br/> |<span data-ttu-id="cc107-133">1</span><span class="sxs-lookup"><span data-stu-id="cc107-133">1</span></span>  <br/> |<span data-ttu-id="cc107-134">hors</span><span class="sxs-lookup"><span data-stu-id="cc107-134">scope</span></span>  <br/> |
|<span data-ttu-id="cc107-135">4</span><span class="sxs-lookup"><span data-stu-id="cc107-135">4</span></span>  <br/> |<span data-ttu-id="cc107-136">deuxième</span><span class="sxs-lookup"><span data-stu-id="cc107-136">2</span></span>  <br/> |<span data-ttu-id="cc107-137">normalement</span><span class="sxs-lookup"><span data-stu-id="cc107-137">normal</span></span>  <br/> |
|<span data-ttu-id="cc107-138">5</span><span class="sxs-lookup"><span data-stu-id="cc107-138">5</span></span>  <br/> |<span data-ttu-id="cc107-139">deuxième</span><span class="sxs-lookup"><span data-stu-id="cc107-139">2</span></span>  <br/> |<span data-ttu-id="cc107-140">Conférence</span><span class="sxs-lookup"><span data-stu-id="cc107-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="cc107-141">6</span><span class="sxs-lookup"><span data-stu-id="cc107-141">6</span></span>  <br/> |<span data-ttu-id="cc107-142">1</span><span class="sxs-lookup"><span data-stu-id="cc107-142">1</span></span>  <br/> |<span data-ttu-id="cc107-143">ouvre</span><span class="sxs-lookup"><span data-stu-id="cc107-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cc107-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc107-144">See also</span></span>

[<span data-ttu-id="cc107-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="cc107-145">tblNode</span></span>](tblnode.md)
