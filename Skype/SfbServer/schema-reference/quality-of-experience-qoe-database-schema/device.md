---
title: Table Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table des périphériques est une table de prise en charge qui stocke des informations sur la capture différents ou restitue des périphériques. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Table Device
 
La table des périphériques est une table de prise en charge qui stocke des informations sur la capture différents ou restitue des périphériques. Chaque enregistrement de la table représente un périphérique.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce périphérique.  <br/> |
|**Nom de périphérique** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType est unique  <br/> |Nom du périphérique.  <br/> |
|**Type d’appareil** <br/> |bit  <br/> |DeviceName + DeviceType est unique  <br/> |Type de périphérique. 1 est un périphérique de capture, 0 est un périphérique de rendu.  <br/> |
   

