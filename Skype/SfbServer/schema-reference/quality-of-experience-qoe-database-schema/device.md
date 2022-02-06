---
title: Table Device
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.
---

# <a name="device-table"></a>Table Device
 
La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique qui identifie ce périphérique.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType est unique  <br/> |Nom du périphérique.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType est unique  <br/> |Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.  <br/> |
   

