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
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription mappe les identificateurs de codec uniques à leur codec correspondant. Codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder les signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principal  <br/> |Identificateur unique affecté au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Unique  <br/> |Description unique du codec correspondant à CodecDescriptionKey.  <br/> |
   

