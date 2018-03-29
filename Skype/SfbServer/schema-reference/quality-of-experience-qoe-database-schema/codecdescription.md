---
title: Table de CodecDescription
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La table CodecDescription mappe les identificateurs uniques de codec à leur codec correspondant. Codecs sont utilisés pour des signaux numériques pour la transmission et la diffusion, de coder et de décoder les signaux pour la lecture. Cette table a été introduite dans Microsoft Lync Server 2013
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="e8e3b-105">Table de CodecDescription</span><span class="sxs-lookup"><span data-stu-id="e8e3b-105">CodecDescription table</span></span>
 
<span data-ttu-id="e8e3b-106">La table CodecDescription mappe les identificateurs uniques de codec à leur codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="e8e3b-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="e8e3b-107">Codecs sont utilisés pour des signaux numériques pour la transmission et la diffusion, de coder et de décoder les signaux pour la lecture.</span><span class="sxs-lookup"><span data-stu-id="e8e3b-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="e8e3b-108">Cette table a été introduite dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e3b-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="e8e3b-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-109">**Column**</span></span>|<span data-ttu-id="e8e3b-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-110">**Data Type**</span></span>|<span data-ttu-id="e8e3b-111">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-111">**Key/Index**</span></span>|<span data-ttu-id="e8e3b-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8e3b-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="e8e3b-114">smallint</span><span class="sxs-lookup"><span data-stu-id="e8e3b-114">smallint</span></span>  <br/> |<span data-ttu-id="e8e3b-115">Principal</span><span class="sxs-lookup"><span data-stu-id="e8e3b-115">Primary</span></span>  <br/> |<span data-ttu-id="e8e3b-116">Identificateur unique assigné au codec.</span><span class="sxs-lookup"><span data-stu-id="e8e3b-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="e8e3b-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="e8e3b-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="e8e3b-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8e3b-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="e8e3b-119">Unique</span><span class="sxs-lookup"><span data-stu-id="e8e3b-119">Unique</span></span>  <br/> |<span data-ttu-id="e8e3b-120">Description unique du codec correspondant à le CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="e8e3b-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

