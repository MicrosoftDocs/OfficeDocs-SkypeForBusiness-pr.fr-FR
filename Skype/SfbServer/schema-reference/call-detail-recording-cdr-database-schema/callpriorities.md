---
title: Table CallPriorities dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901528"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9c987-103">Table CallPriorities dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c987-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9c987-104">La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».</span><span class="sxs-lookup"><span data-stu-id="9c987-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="9c987-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9c987-105">**Column**</span></span>|<span data-ttu-id="9c987-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="9c987-106">**Data Type**</span></span>|<span data-ttu-id="9c987-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="9c987-107">**Key/Index**</span></span>|<span data-ttu-id="9c987-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="9c987-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c987-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="9c987-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="9c987-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9c987-110">tinyint</span></span>  <br/> |<span data-ttu-id="9c987-111">Principal</span><span class="sxs-lookup"><span data-stu-id="9c987-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9c987-112">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="9c987-112">**Priority**</span></span> <br/> |<span data-ttu-id="9c987-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c987-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9c987-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="9c987-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9c987-115">0 - inconnu</span><span class="sxs-lookup"><span data-stu-id="9c987-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="9c987-116">1 – non Urgent</span><span class="sxs-lookup"><span data-stu-id="9c987-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="9c987-117">2 - normale</span><span class="sxs-lookup"><span data-stu-id="9c987-117">2 - Normal</span></span> <br/>  <span data-ttu-id="9c987-118">3 - urgent</span><span class="sxs-lookup"><span data-stu-id="9c987-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="9c987-119">4 - très urgent</span><span class="sxs-lookup"><span data-stu-id="9c987-119">4 - Emergency</span></span> <br/> |
   

