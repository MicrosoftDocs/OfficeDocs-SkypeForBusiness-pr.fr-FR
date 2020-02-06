---
title: Table ErrorCategory dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015. Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes :'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815252"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9384e-104">Table ErrorCategory dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9384e-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9384e-105">La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9384e-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="9384e-106">Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="9384e-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="9384e-107">0--succès</span><span class="sxs-lookup"><span data-stu-id="9384e-107">0 -- Success</span></span>
    
- <span data-ttu-id="9384e-108">1-échec imprévu</span><span class="sxs-lookup"><span data-stu-id="9384e-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="9384e-109">2-échec inattendu</span><span class="sxs-lookup"><span data-stu-id="9384e-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="9384e-110">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9384e-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9384e-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9384e-111">**Column**</span></span>|<span data-ttu-id="9384e-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="9384e-112">**Data Type**</span></span>|<span data-ttu-id="9384e-113">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="9384e-113">**Key/Index**</span></span>|<span data-ttu-id="9384e-114">**Détails**</span><span class="sxs-lookup"><span data-stu-id="9384e-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9384e-115">**RéfCatégorie**</span><span class="sxs-lookup"><span data-stu-id="9384e-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="9384e-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="9384e-116">tinyint</span></span>  <br/> |<span data-ttu-id="9384e-117">Principal</span><span class="sxs-lookup"><span data-stu-id="9384e-117">Primary</span></span>  <br/> |<span data-ttu-id="9384e-118">Identificateur unique de la classification.</span><span class="sxs-lookup"><span data-stu-id="9384e-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="9384e-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="9384e-119">**Name**</span></span> <br/> |<span data-ttu-id="9384e-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9384e-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9384e-121">Valeur et nom convivial attribués à la classification.</span><span class="sxs-lookup"><span data-stu-id="9384e-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="9384e-122">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9384e-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="9384e-123">0--succès</span><span class="sxs-lookup"><span data-stu-id="9384e-123">0 -- Success</span></span> <br/>  <span data-ttu-id="9384e-124">1-échec imprévu</span><span class="sxs-lookup"><span data-stu-id="9384e-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="9384e-125">2-échec inattendu</span><span class="sxs-lookup"><span data-stu-id="9384e-125">2 - Unexpected failure</span></span> <br/> |
   

