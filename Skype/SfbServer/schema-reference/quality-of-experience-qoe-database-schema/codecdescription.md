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
ms.openlocfilehash: 9facaa9ddf29024a731f9e199b5cf749d91bc6671c320ded510d693755640f38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309173"
---
# <a name="codecdescription-table"></a>Table CodecDescription
 
La table CodecDescription permet de mettre en correspondance des identificateurs de codec uniques avec le codec correspondant. Les codecs sont utilisés pour coder des signaux numériques pour la transmission et la diffusion, puis pour décoder ces signaux pour la lecture. Ce tableau a été introduit dans Microsoft Lync Server 2013
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primaire  <br/> |Identificateur unique attribué au codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Uniques  <br/> |Description unique du codec correspondant à codecDescriptionKey.  <br/> |
   

