---
title: Table MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920151"
---
# <a name="monitoredregionlink-table"></a>Table MonitoredRegionLink
 
La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux pays/régions.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé depuis la [Region table](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé depuis la [Region table](region.md).  <br/> |
   

