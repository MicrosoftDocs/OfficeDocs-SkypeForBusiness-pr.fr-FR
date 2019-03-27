---
title: Table MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884413"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="9260e-104">Table MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="9260e-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="9260e-105">La table MonitoredRegionLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9260e-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="9260e-106">Chaque enregistrement représente un lien entre deux pays/régions.</span><span class="sxs-lookup"><span data-stu-id="9260e-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="9260e-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9260e-107">**Column**</span></span>|<span data-ttu-id="9260e-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="9260e-108">**Data Type**</span></span>|<span data-ttu-id="9260e-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="9260e-109">**Key/Index**</span></span>|<span data-ttu-id="9260e-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="9260e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9260e-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="9260e-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="9260e-112">int</span><span class="sxs-lookup"><span data-stu-id="9260e-112">int</span></span>  <br/> |<span data-ttu-id="9260e-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="9260e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9260e-114">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="9260e-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="9260e-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="9260e-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="9260e-116">int</span><span class="sxs-lookup"><span data-stu-id="9260e-116">int</span></span>  <br/> |<span data-ttu-id="9260e-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="9260e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9260e-118">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="9260e-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

