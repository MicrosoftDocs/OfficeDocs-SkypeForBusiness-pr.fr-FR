---
title: Table CallPriorities dans Skype Entreprise Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ou « normal ».
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813434"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="20161-103">Table CallPriorities dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="20161-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20161-104">La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ou « normal ».</span><span class="sxs-lookup"><span data-stu-id="20161-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="20161-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="20161-105">**Column**</span></span>|<span data-ttu-id="20161-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="20161-106">**Data Type**</span></span>|<span data-ttu-id="20161-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="20161-107">**Key/Index**</span></span>|<span data-ttu-id="20161-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="20161-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="20161-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="20161-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="20161-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="20161-110">tinyint</span></span>  <br/> |<span data-ttu-id="20161-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="20161-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="20161-112">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="20161-112">**Priority**</span></span> <br/> |<span data-ttu-id="20161-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="20161-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="20161-114">Valeurs autorisées :</span><span class="sxs-lookup"><span data-stu-id="20161-114">Allowed values:</span></span> <br/>  <span data-ttu-id="20161-115">0 - Inconnu</span><span class="sxs-lookup"><span data-stu-id="20161-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="20161-116">1 - Non urgent</span><span class="sxs-lookup"><span data-stu-id="20161-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="20161-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="20161-117">2 - Normal</span></span> <br/>  <span data-ttu-id="20161-118">3 - Urgent</span><span class="sxs-lookup"><span data-stu-id="20161-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="20161-119">4 - Très urgent</span><span class="sxs-lookup"><span data-stu-id="20161-119">4 - Emergency</span></span> <br/> |
   

