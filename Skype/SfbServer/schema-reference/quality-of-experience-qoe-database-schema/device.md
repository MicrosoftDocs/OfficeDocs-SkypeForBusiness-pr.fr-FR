---
title: Table Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810152"
---
# <a name="device-table"></a>Table Device
 
La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet appareil.  <br/> |
|**Périphérique** <br/> |nvarchar(256)  <br/> |Nom_unité + DeviceType est unique  <br/> |Nom de l’appareil.  <br/> |
|**DeviceType** <br/> |bit  <br/> |Nom_unité + DeviceType est unique  <br/> |Type d’appareil. 1 est un appareil de capture ; 0 est un périphérique de rendu.  <br/> |
   

