---
title: Table MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.
ms.openlocfilehash: 0efac1d496889645ffb52db5c419397337ebf9f2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858101"
---
# <a name="monitoredregionlink-table"></a>Table MonitoredRegionLink
 
La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir de [la table Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir de [la table Region](region.md).  <br/> |
   

