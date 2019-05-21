---
title: Table CallPriorities dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que «urgence», «urgent» ou «normale».
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296566"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1cc10-103">Table CallPriorities dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1cc10-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1cc10-104">La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que «urgence», «urgent» ou «normale».</span><span class="sxs-lookup"><span data-stu-id="1cc10-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="1cc10-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1cc10-105">**Column**</span></span>|<span data-ttu-id="1cc10-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1cc10-106">**Data Type**</span></span>|<span data-ttu-id="1cc10-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="1cc10-107">**Key/Index**</span></span>|<span data-ttu-id="1cc10-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1cc10-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cc10-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="1cc10-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="1cc10-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1cc10-110">tinyint</span></span>  <br/> |<span data-ttu-id="1cc10-111">Principal</span><span class="sxs-lookup"><span data-stu-id="1cc10-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1cc10-112">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="1cc10-112">**Priority**</span></span> <br/> |<span data-ttu-id="1cc10-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1cc10-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1cc10-114">Valeurs autorisées:</span><span class="sxs-lookup"><span data-stu-id="1cc10-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1cc10-115">0-Inconnu</span><span class="sxs-lookup"><span data-stu-id="1cc10-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="1cc10-116">1-non urgent</span><span class="sxs-lookup"><span data-stu-id="1cc10-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="1cc10-117">2-normal</span><span class="sxs-lookup"><span data-stu-id="1cc10-117">2 - Normal</span></span> <br/>  <span data-ttu-id="1cc10-118">3-urgent</span><span class="sxs-lookup"><span data-stu-id="1cc10-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="1cc10-119">4-urgence</span><span class="sxs-lookup"><span data-stu-id="1cc10-119">4 - Emergency</span></span> <br/> |
   

