---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809714"
---
# <a name="tblenumattribute"></a><span data-ttu-id="d7da8-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="d7da8-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="d7da8-104">tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.</span><span class="sxs-lookup"><span data-stu-id="d7da8-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d7da8-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d7da8-105">**Columns**</span></span>

|<span data-ttu-id="d7da8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7da8-106">**Column**</span></span>|<span data-ttu-id="d7da8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d7da8-107">**Type**</span></span>|<span data-ttu-id="d7da8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7da8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7da8-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="d7da8-109">attributeID</span></span>  <br/> |<span data-ttu-id="d7da8-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="d7da8-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d7da8-111">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="d7da8-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d7da8-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="d7da8-112">attributeName</span></span>  <br/> |<span data-ttu-id="d7da8-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="d7da8-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d7da8-114">Nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="d7da8-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="d7da8-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="d7da8-115">**Key**</span></span>

|<span data-ttu-id="d7da8-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d7da8-116">**Column**</span></span>|<span data-ttu-id="d7da8-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d7da8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7da8-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="d7da8-118">attributeID</span></span>  <br/> |<span data-ttu-id="d7da8-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="d7da8-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="d7da8-120">**Valeurs du tableau**</span><span class="sxs-lookup"><span data-stu-id="d7da8-120">**Table Values**</span></span>

|<span data-ttu-id="d7da8-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="d7da8-121">**attributeID**</span></span>|<span data-ttu-id="d7da8-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="d7da8-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7da8-123">1 </span><span class="sxs-lookup"><span data-stu-id="d7da8-123">1</span></span>  <br/> |<span data-ttu-id="d7da8-124">Visibilité.</span><span class="sxs-lookup"><span data-stu-id="d7da8-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="d7da8-125">2 </span><span class="sxs-lookup"><span data-stu-id="d7da8-125">2</span></span>  <br/> |<span data-ttu-id="d7da8-126">Comportement.</span><span class="sxs-lookup"><span data-stu-id="d7da8-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d7da8-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7da8-127">See also</span></span>

[<span data-ttu-id="d7da8-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="d7da8-128">tblNode</span></span>](tblnode.md)
