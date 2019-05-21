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
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Le tableau CodecDescription mappe des identificateurs de codec uniques au codec correspondant. Les codecs permettent de coder les signaux numériques pour la transmission et la diffusion, puis de décoder ces signaux pour la lecture. Ce tableau a été présenté dans Microsoft Lync Server 2013
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295040"
---
# <a name="codecdescription-table"></a><span data-ttu-id="bf3de-105">Table CodecDescription</span><span class="sxs-lookup"><span data-stu-id="bf3de-105">CodecDescription table</span></span>
 
<span data-ttu-id="bf3de-106">Le tableau CodecDescription mappe des identificateurs de codec uniques au codec correspondant.</span><span class="sxs-lookup"><span data-stu-id="bf3de-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="bf3de-107">Les codecs permettent de coder les signaux numériques pour la transmission et la diffusion, puis de décoder ces signaux pour la lecture.</span><span class="sxs-lookup"><span data-stu-id="bf3de-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="bf3de-108">Ce tableau a été présenté dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf3de-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="bf3de-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bf3de-109">**Column**</span></span>|<span data-ttu-id="bf3de-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="bf3de-110">**Data Type**</span></span>|<span data-ttu-id="bf3de-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="bf3de-111">**Key/Index**</span></span>|<span data-ttu-id="bf3de-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="bf3de-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf3de-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="bf3de-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="bf3de-114">type</span><span class="sxs-lookup"><span data-stu-id="bf3de-114">smallint</span></span>  <br/> |<span data-ttu-id="bf3de-115">Principal</span><span class="sxs-lookup"><span data-stu-id="bf3de-115">Primary</span></span>  <br/> |<span data-ttu-id="bf3de-116">Identificateur unique attribué au codec.</span><span class="sxs-lookup"><span data-stu-id="bf3de-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="bf3de-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="bf3de-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="bf3de-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bf3de-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="bf3de-119">Différent</span><span class="sxs-lookup"><span data-stu-id="bf3de-119">Unique</span></span>  <br/> |<span data-ttu-id="bf3de-120">Description unique du codec correspondant au CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="bf3de-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

