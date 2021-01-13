---
title: Table CodecDescription
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder des signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831344"
---
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder des signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primaire  <br/> |Identificateur unique attribué au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Uniques  <br/> |Description unique du codec correspondant à codecDescriptionKey.  <br/> |
   

