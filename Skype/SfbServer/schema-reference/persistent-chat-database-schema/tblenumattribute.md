---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814612"
---
# <a name="tblenumattribute"></a><span data-ttu-id="f43ff-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="f43ff-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="f43ff-104">tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.</span><span class="sxs-lookup"><span data-stu-id="f43ff-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f43ff-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="f43ff-105">**Columns**</span></span>

|<span data-ttu-id="f43ff-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f43ff-106">**Column**</span></span>|<span data-ttu-id="f43ff-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="f43ff-107">**Type**</span></span>|<span data-ttu-id="f43ff-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="f43ff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f43ff-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="f43ff-109">attributeID</span></span>  <br/> |<span data-ttu-id="f43ff-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="f43ff-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f43ff-111">ID de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="f43ff-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f43ff-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="f43ff-112">attributeName</span></span>  <br/> |<span data-ttu-id="f43ff-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="f43ff-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f43ff-114">Nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="f43ff-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="f43ff-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="f43ff-115">**Key**</span></span>

|<span data-ttu-id="f43ff-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f43ff-116">**Column**</span></span>|<span data-ttu-id="f43ff-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="f43ff-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f43ff-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="f43ff-118">attributeID</span></span>  <br/> |<span data-ttu-id="f43ff-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f43ff-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f43ff-120">**Valeurs de table**</span><span class="sxs-lookup"><span data-stu-id="f43ff-120">**Table Values**</span></span>

|<span data-ttu-id="f43ff-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f43ff-121">**attributeID**</span></span>|<span data-ttu-id="f43ff-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="f43ff-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f43ff-123">1</span><span class="sxs-lookup"><span data-stu-id="f43ff-123">1</span></span>  <br/> |<span data-ttu-id="f43ff-124">Notoriété.</span><span class="sxs-lookup"><span data-stu-id="f43ff-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="f43ff-125">deuxième</span><span class="sxs-lookup"><span data-stu-id="f43ff-125">2</span></span>  <br/> |<span data-ttu-id="f43ff-126">Fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="f43ff-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f43ff-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f43ff-127">See also</span></span>

[<span data-ttu-id="f43ff-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="f43ff-128">tblNode</span></span>](tblnode.md)
