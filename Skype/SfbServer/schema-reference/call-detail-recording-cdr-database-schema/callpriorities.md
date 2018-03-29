---
title: Table CallPriorities dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, comme « secours », « urgent » ou « normal ».
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1b1e3-103">Table CallPriorities dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1b1e3-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1b1e3-104">La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, comme « secours », « urgent » ou « normal ».</span><span class="sxs-lookup"><span data-stu-id="1b1e3-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="1b1e3-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-105">**Column**</span></span>|<span data-ttu-id="1b1e3-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-106">**Data Type**</span></span>|<span data-ttu-id="1b1e3-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-107">**Key/Index**</span></span>|<span data-ttu-id="1b1e3-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b1e3-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="1b1e3-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1b1e3-110">tinyint</span></span>  <br/> |<span data-ttu-id="1b1e3-111">Principal</span><span class="sxs-lookup"><span data-stu-id="1b1e3-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1b1e3-112">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="1b1e3-112">**Priority**</span></span> <br/> |<span data-ttu-id="1b1e3-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1b1e3-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1b1e3-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="1b1e3-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1b1e3-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="1b1e3-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="1b1e3-116">1 - non Urgent</span><span class="sxs-lookup"><span data-stu-id="1b1e3-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="1b1e3-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="1b1e3-117">2 - Normal</span></span> <br/>  <span data-ttu-id="1b1e3-118">3 - urgent</span><span class="sxs-lookup"><span data-stu-id="1b1e3-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="1b1e3-119">4 - urgence</span><span class="sxs-lookup"><span data-stu-id="1b1e3-119">4 - Emergency</span></span> <br/> |
   

