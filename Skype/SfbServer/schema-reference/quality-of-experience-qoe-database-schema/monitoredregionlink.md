---
title: Table MonitoredRegionLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806344"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="e6463-104">Table MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="e6463-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="e6463-p102">La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.</span><span class="sxs-lookup"><span data-stu-id="e6463-p102">The MonitoredRegionLink table is a supporting table. Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="e6463-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6463-107">**Column**</span></span>|<span data-ttu-id="e6463-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e6463-108">**Data Type**</span></span>|<span data-ttu-id="e6463-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e6463-109">**Key/Index**</span></span>|<span data-ttu-id="e6463-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e6463-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6463-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="e6463-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="e6463-112">int</span><span class="sxs-lookup"><span data-stu-id="e6463-112">int</span></span>  <br/> |<span data-ttu-id="e6463-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="e6463-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e6463-114">Référencé à partir de [la table Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="e6463-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="e6463-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="e6463-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="e6463-116">int</span><span class="sxs-lookup"><span data-stu-id="e6463-116">int</span></span>  <br/> |<span data-ttu-id="e6463-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="e6463-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e6463-118">Référencé à partir de [la table Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="e6463-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

