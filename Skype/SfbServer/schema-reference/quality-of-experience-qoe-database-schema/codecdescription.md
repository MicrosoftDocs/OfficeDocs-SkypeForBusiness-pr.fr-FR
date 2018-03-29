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
# <a name="codecdescription-table"></a>Table de CodecDescription
 
La table CodecDescription mappe les identificateurs uniques de codec à leur codec correspondant. Codecs sont utilisés pour des signaux numériques pour la transmission et la diffusion, de coder et de décoder les signaux pour la lecture. Cette table a été introduite dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principal  <br/> |Identificateur unique assigné au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |Description unique du codec correspondant à le CodecDescriptionKey.  <br/> |
   

