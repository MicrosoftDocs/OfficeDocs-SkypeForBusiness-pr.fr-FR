---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et comportement qui sont utilisés dans la table Node.
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929951"
---
# <a name="tblenumattribute"></a><span data-ttu-id="11688-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="11688-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="11688-104">tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et comportement qui sont utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="11688-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="11688-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="11688-105">**Columns**</span></span>

|<span data-ttu-id="11688-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="11688-106">**Column**</span></span>|<span data-ttu-id="11688-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="11688-107">**Type**</span></span>|<span data-ttu-id="11688-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="11688-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="11688-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="11688-109">attributeID</span></span>  <br/> |<span data-ttu-id="11688-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="11688-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="11688-111">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="11688-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="11688-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="11688-112">attributeName</span></span>  <br/> |<span data-ttu-id="11688-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="11688-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="11688-114">Nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="11688-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="11688-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="11688-115">**Key**</span></span>

|<span data-ttu-id="11688-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="11688-116">**Column**</span></span>|<span data-ttu-id="11688-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="11688-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11688-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="11688-118">attributeID</span></span>  <br/> |<span data-ttu-id="11688-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="11688-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="11688-120">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="11688-120">**Table Values**</span></span>

|<span data-ttu-id="11688-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="11688-121">**attributeID**</span></span>|<span data-ttu-id="11688-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="11688-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11688-123">1</span><span class="sxs-lookup"><span data-stu-id="11688-123">1</span></span>  <br/> |<span data-ttu-id="11688-124">Visibilité.</span><span class="sxs-lookup"><span data-stu-id="11688-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="11688-125">2</span><span class="sxs-lookup"><span data-stu-id="11688-125">2</span></span>  <br/> |<span data-ttu-id="11688-126">Comportement.</span><span class="sxs-lookup"><span data-stu-id="11688-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="11688-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11688-127">See also</span></span>

[<span data-ttu-id="11688-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="11688-128">tblNode</span></span>](tblnode.md)
