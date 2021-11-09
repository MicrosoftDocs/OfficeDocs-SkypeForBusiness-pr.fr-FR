---
title: Table Device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.
ms.openlocfilehash: e999cf493cce69ee05d8a342e346cf8277d8d5d8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827417"
---
# <a name="device-table"></a>Table Device
 
La table Device est une table de prise en charge qui stocke des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un périphérique.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique qui identifie ce périphérique.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType est unique  <br/> |Nom du périphérique.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType est unique  <br/> |Type de périphérique. 1 correspond à un périphérique de capture, 0 à un périphérique de rendu.  <br/> |
   

