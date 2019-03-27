---
title: Table MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884413"
---
# <a name="monitoredregionlink-table"></a>Table MonitoredRegionLink
 
La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé depuis la [Region table](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé depuis la [Region table](region.md).  <br/> |
   

