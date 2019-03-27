---
title: Table Device
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885511"
---
# <a name="device-table"></a>Table Device
 
Le tableau de périphérique est une table de prise en charge qui stocke des informations sur la capture différents ou les appareils de rendu. Chaque enregistrement de la table représente un périphérique.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique qui identifie ce périphérique.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType est unique  <br/> |Nom du périphérique.  <br/> |
|**Type d’appareil** <br/> |bit  <br/> |DeviceName + DeviceType est unique  <br/> |Type d’appareil. 1 est un périphérique de capture, 0 correspond à un périphérique de rendu.  <br/> |
   

