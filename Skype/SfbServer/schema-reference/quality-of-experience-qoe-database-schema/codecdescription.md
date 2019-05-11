---
title: Table CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La table CodecDescription mappe les identificateurs de codec uniques à leur codec correspondant. Codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder les signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920102"
---
# <a name="codecdescription-table"></a><span data-ttu-id="0c5a8-105">Table CodecDescription</span><span class="sxs-lookup"><span data-stu-id="0c5a8-105">CodecDescription table</span></span>
 
<span data-ttu-id="0c5a8-106">La table CodecDescription mappe les identificateurs de codec uniques à leur codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="0c5a8-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="0c5a8-107">Codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder les signaux pour la lecture.</span><span class="sxs-lookup"><span data-stu-id="0c5a8-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="0c5a8-108">Ce tableau a été introduit dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c5a8-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="0c5a8-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-109">**Column**</span></span>|<span data-ttu-id="0c5a8-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-110">**Data Type**</span></span>|<span data-ttu-id="0c5a8-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-111">**Key/Index**</span></span>|<span data-ttu-id="0c5a8-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c5a8-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="0c5a8-114">smallint</span><span class="sxs-lookup"><span data-stu-id="0c5a8-114">smallint</span></span>  <br/> |<span data-ttu-id="0c5a8-115">Principal</span><span class="sxs-lookup"><span data-stu-id="0c5a8-115">Primary</span></span>  <br/> |<span data-ttu-id="0c5a8-116">Identificateur unique affecté au codec.</span><span class="sxs-lookup"><span data-stu-id="0c5a8-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="0c5a8-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="0c5a8-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="0c5a8-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c5a8-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="0c5a8-119">Unique</span><span class="sxs-lookup"><span data-stu-id="0c5a8-119">Unique</span></span>  <br/> |<span data-ttu-id="0c5a8-120">Description unique du codec correspondant à CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="0c5a8-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

