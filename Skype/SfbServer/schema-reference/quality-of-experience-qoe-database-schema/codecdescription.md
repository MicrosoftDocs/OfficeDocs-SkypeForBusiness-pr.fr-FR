---
title: Table CodecDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La table CodecDescription mappe les identificateurs de codec uniques à leur codec correspondant. Codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder les signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212269"
---
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription mappe les identificateurs de codec uniques à leur codec correspondant. Codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder les signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principal  <br/> |Identificateur unique affecté au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |Description unique du codec correspondant à CodecDescriptionKey.  <br/> |
   

