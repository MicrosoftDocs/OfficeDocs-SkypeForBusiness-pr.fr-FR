---
title: Table ErrorCategory dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise les catégories suivantes :'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213115"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c7c85-104">Table ErrorCategory dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c7c85-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7c85-105">La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c7c85-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="c7c85-106">Par défaut, Skype pour Business Server 2015 utilise les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7c85-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="c7c85-107">0 - Réussite</span><span class="sxs-lookup"><span data-stu-id="c7c85-107">0 -- Success</span></span>
    
- <span data-ttu-id="c7c85-108">1 : échec attendu</span><span class="sxs-lookup"><span data-stu-id="c7c85-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="c7c85-109">2 - Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="c7c85-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="c7c85-110">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7c85-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c7c85-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c7c85-111">**Column**</span></span>|<span data-ttu-id="c7c85-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c7c85-112">**Data Type**</span></span>|<span data-ttu-id="c7c85-113">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c7c85-113">**Key/Index**</span></span>|<span data-ttu-id="c7c85-114">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c7c85-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7c85-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="c7c85-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="c7c85-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="c7c85-116">tinyint</span></span>  <br/> |<span data-ttu-id="c7c85-117">Principal</span><span class="sxs-lookup"><span data-stu-id="c7c85-117">Primary</span></span>  <br/> |<span data-ttu-id="c7c85-118">Identificateur unique pour la classification.</span><span class="sxs-lookup"><span data-stu-id="c7c85-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="c7c85-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="c7c85-119">**Name**</span></span> <br/> |<span data-ttu-id="c7c85-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c7c85-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c7c85-121">Valeur et le nom convivial attribué à la classification.</span><span class="sxs-lookup"><span data-stu-id="c7c85-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="c7c85-122">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7c85-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="c7c85-123">0 - Réussite</span><span class="sxs-lookup"><span data-stu-id="c7c85-123">0 -- Success</span></span> <br/>  <span data-ttu-id="c7c85-124">1 : échec attendu</span><span class="sxs-lookup"><span data-stu-id="c7c85-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="c7c85-125">2 - Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="c7c85-125">2 - Unexpected failure</span></span> <br/> |
   

