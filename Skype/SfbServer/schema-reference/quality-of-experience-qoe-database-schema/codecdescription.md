---
title: Table CodecDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 8ef16503e1e28f3de478ef5593c990c4ce2e45dd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827357"
---
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder les signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primaire  <br/> |Identificateur unique attribué au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Uniques  <br/> |Description unique du codec correspondant à codecDescriptionKey.  <br/> |
   

