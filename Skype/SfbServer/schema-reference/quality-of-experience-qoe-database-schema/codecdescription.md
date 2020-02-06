---
title: Table CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Le tableau CodecDescription mappe des identificateurs de codec uniques au codec correspondant. Les codecs permettent de coder les signaux numériques pour la transmission et la diffusion, puis de décoder ces signaux pour la lecture. Ce tableau a été présenté dans Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810362"
---
# <a name="codecdescription-table"></a><span data-ttu-id="9722a-105">Table CodecDescription</span><span class="sxs-lookup"><span data-stu-id="9722a-105">CodecDescription table</span></span>
 
<span data-ttu-id="9722a-106">Le tableau CodecDescription mappe des identificateurs de codec uniques au codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="9722a-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="9722a-107">Les codecs permettent de coder les signaux numériques pour la transmission et la diffusion, puis de décoder ces signaux pour la lecture.</span><span class="sxs-lookup"><span data-stu-id="9722a-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="9722a-108">Ce tableau a été présenté dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722a-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="9722a-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9722a-109">**Column**</span></span>|<span data-ttu-id="9722a-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="9722a-110">**Data Type**</span></span>|<span data-ttu-id="9722a-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="9722a-111">**Key/Index**</span></span>|<span data-ttu-id="9722a-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="9722a-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9722a-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="9722a-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="9722a-114">type</span><span class="sxs-lookup"><span data-stu-id="9722a-114">smallint</span></span>  <br/> |<span data-ttu-id="9722a-115">Principal</span><span class="sxs-lookup"><span data-stu-id="9722a-115">Primary</span></span>  <br/> |<span data-ttu-id="9722a-116">Identificateur unique attribué au codec.</span><span class="sxs-lookup"><span data-stu-id="9722a-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="9722a-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="9722a-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="9722a-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9722a-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="9722a-119">Différent</span><span class="sxs-lookup"><span data-stu-id="9722a-119">Unique</span></span>  <br/> |<span data-ttu-id="9722a-120">Description unique du codec correspondant au CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="9722a-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

