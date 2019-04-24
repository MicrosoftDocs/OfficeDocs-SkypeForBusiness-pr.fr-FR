---
title: Table CallPriorities dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213332"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e6769-103">Table CallPriorities dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6769-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e6769-104">La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».</span><span class="sxs-lookup"><span data-stu-id="e6769-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="e6769-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6769-105">**Column**</span></span>|<span data-ttu-id="e6769-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e6769-106">**Data Type**</span></span>|<span data-ttu-id="e6769-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e6769-107">**Key/Index**</span></span>|<span data-ttu-id="e6769-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e6769-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6769-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="e6769-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="e6769-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6769-110">tinyint</span></span>  <br/> |<span data-ttu-id="e6769-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e6769-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e6769-112">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="e6769-112">**Priority**</span></span> <br/> |<span data-ttu-id="e6769-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6769-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e6769-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="e6769-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e6769-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="e6769-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="e6769-116">1 – non Urgent</span><span class="sxs-lookup"><span data-stu-id="e6769-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="e6769-117">2 - normale</span><span class="sxs-lookup"><span data-stu-id="e6769-117">2 - Normal</span></span> <br/>  <span data-ttu-id="e6769-118">3 - urgent</span><span class="sxs-lookup"><span data-stu-id="e6769-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="e6769-119">4 - très urgent</span><span class="sxs-lookup"><span data-stu-id="e6769-119">4 - Emergency</span></span> <br/> |
   

