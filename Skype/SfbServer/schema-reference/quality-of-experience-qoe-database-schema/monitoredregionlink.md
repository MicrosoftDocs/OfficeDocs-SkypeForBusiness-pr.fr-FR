---
title: Table MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920151"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="29375-104">Table MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="29375-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="29375-105">La table MonitoredRegionLink est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="29375-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="29375-106">Chaque enregistrement représente un lien entre deux pays/régions.</span><span class="sxs-lookup"><span data-stu-id="29375-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="29375-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="29375-107">**Column**</span></span>|<span data-ttu-id="29375-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="29375-108">**Data Type**</span></span>|<span data-ttu-id="29375-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="29375-109">**Key/Index**</span></span>|<span data-ttu-id="29375-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="29375-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="29375-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="29375-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="29375-112">int</span><span class="sxs-lookup"><span data-stu-id="29375-112">int</span></span>  <br/> |<span data-ttu-id="29375-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="29375-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="29375-114">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="29375-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="29375-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="29375-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="29375-116">int</span><span class="sxs-lookup"><span data-stu-id="29375-116">int</span></span>  <br/> |<span data-ttu-id="29375-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="29375-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="29375-118">Référencé depuis la [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="29375-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

