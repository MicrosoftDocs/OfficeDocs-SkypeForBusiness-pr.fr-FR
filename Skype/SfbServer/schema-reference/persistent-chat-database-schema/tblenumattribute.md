---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est un tableau codé en dur qui contient les attributs de visibilité et le comportement qui sont utilisés dans la table des nœuds.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a><span data-ttu-id="8c672-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="8c672-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="8c672-104">tblEnumAttribute est un tableau codé en dur qui contient les attributs de visibilité et le comportement qui sont utilisés dans la table des nœuds.</span><span class="sxs-lookup"><span data-stu-id="8c672-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="8c672-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8c672-105">**Columns**</span></span>

|<span data-ttu-id="8c672-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8c672-106">**Column**</span></span>|<span data-ttu-id="8c672-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="8c672-107">**Type**</span></span>|<span data-ttu-id="8c672-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="8c672-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c672-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="8c672-109">attributeID</span></span>  <br/> |<span data-ttu-id="8c672-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="8c672-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="8c672-111">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="8c672-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="8c672-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="8c672-112">attributeName</span></span>  <br/> |<span data-ttu-id="8c672-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="8c672-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="8c672-114">Nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="8c672-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="8c672-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="8c672-115">**Key**</span></span>

|<span data-ttu-id="8c672-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8c672-116">**Column**</span></span>|<span data-ttu-id="8c672-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="8c672-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c672-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="8c672-118">attributeID</span></span>  <br/> |<span data-ttu-id="8c672-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="8c672-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="8c672-120">**Valeurs de la table**</span><span class="sxs-lookup"><span data-stu-id="8c672-120">**Table Values**</span></span>

|<span data-ttu-id="8c672-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="8c672-121">**attributeID**</span></span>|<span data-ttu-id="8c672-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="8c672-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c672-123">1</span><span class="sxs-lookup"><span data-stu-id="8c672-123">1</span></span>  <br/> |<span data-ttu-id="8c672-124">Visibilité.</span><span class="sxs-lookup"><span data-stu-id="8c672-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="8c672-125">2</span><span class="sxs-lookup"><span data-stu-id="8c672-125">2</span></span>  <br/> |<span data-ttu-id="8c672-126">Comportement.</span><span class="sxs-lookup"><span data-stu-id="8c672-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8c672-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c672-127">See also</span></span>

#### 

[<span data-ttu-id="8c672-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="8c672-128">tblNode</span></span>](tblnode.md)

