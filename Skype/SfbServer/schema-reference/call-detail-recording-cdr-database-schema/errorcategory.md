---
title: Table ErrorCategory dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise des classifications suivantes :'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1c1bf-104">Table ErrorCategory dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c1bf-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1c1bf-105">La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1c1bf-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="1c1bf-106">Par défaut, Skype pour Business Server 2015 utilise des classifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c1bf-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="1c1bf-107">0 - Réussite</span><span class="sxs-lookup"><span data-stu-id="1c1bf-107">0 -- Success</span></span>
    
- <span data-ttu-id="1c1bf-108">1--échec attendu</span><span class="sxs-lookup"><span data-stu-id="1c1bf-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="1c1bf-109">2 - arrêt</span><span class="sxs-lookup"><span data-stu-id="1c1bf-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="1c1bf-110">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c1bf-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1c1bf-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-111">**Column**</span></span>|<span data-ttu-id="1c1bf-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-112">**Data Type**</span></span>|<span data-ttu-id="1c1bf-113">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-113">**Key/Index**</span></span>|<span data-ttu-id="1c1bf-114">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c1bf-115">**Code catégorie**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="1c1bf-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="1c1bf-116">tinyint</span></span>  <br/> |<span data-ttu-id="1c1bf-117">Principal</span><span class="sxs-lookup"><span data-stu-id="1c1bf-117">Primary</span></span>  <br/> |<span data-ttu-id="1c1bf-118">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="1c1bf-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="1c1bf-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="1c1bf-119">**Name**</span></span> <br/> |<span data-ttu-id="1c1bf-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1c1bf-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1c1bf-121">Valeur et le nom convivial attribué à la classification.</span><span class="sxs-lookup"><span data-stu-id="1c1bf-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="1c1bf-122">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c1bf-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="1c1bf-123">0 - Réussite</span><span class="sxs-lookup"><span data-stu-id="1c1bf-123">0 -- Success</span></span> <br/>  <span data-ttu-id="1c1bf-124">1--échec attendu</span><span class="sxs-lookup"><span data-stu-id="1c1bf-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="1c1bf-125">2 - arrêt</span><span class="sxs-lookup"><span data-stu-id="1c1bf-125">2 - Unexpected failure</span></span> <br/> |
   

