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
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295005"
---
# <a name="device-table"></a>Table Device
 
La table Device est une table qui contient des informations sur les différents périphériques de capture ou de rendu. Chaque enregistrement de la table représente un appareil.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet appareil.  <br/> |
|**Périphérique** <br/> |nvarchar(256)  <br/> |Nom_unité + DeviceType est unique  <br/> |Nom de l’appareil.  <br/> |
|**DeviceType** <br/> |bit  <br/> |Nom_unité + DeviceType est unique  <br/> |Type d’appareil. 1 est un appareil de capture; 0 est un périphérique de rendu.  <br/> |
   

