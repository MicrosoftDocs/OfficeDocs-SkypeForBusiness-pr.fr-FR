---
title: Table CodecDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
ms.openlocfilehash: 0f5601847458f7ce59e0cd691b573ec77605b667
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763242"
---
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primaire  <br/> |Identificateur unique attribué au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Uniques  <br/> |Description unique du codec correspondant à codecDescriptionKey.  <br/> |
   

