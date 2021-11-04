---
title: Table MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.
ms.openlocfilehash: 39add4c7ba3fc67c68645498772b06715967aa39
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763122"
---
# <a name="monitoredregionlink-table"></a>Table MonitoredRegionLink
 
La table MonitoredRegionLink est une table de prise en charge. Chaque enregistrement représente une liaison entre deux pays/régions.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir de [la table Region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir de [la table Region](region.md).  <br/> |
   

