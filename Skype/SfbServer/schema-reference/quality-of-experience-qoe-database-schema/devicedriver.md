---
title: Table DeviceDriver
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.
ms.openlocfilehash: 49bf941de3c0639552bd01e5066c9b823953ca7d4c01acc1b77a973045d89985
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276569"
---
# <a name="devicedriver-table"></a>Table DeviceDriver
 
La table DeviceDriver est une table de prise en charge. Chaque enregistrement représente un pilote utilisé par un périphérique de capture ou par un périphérique de rendu.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de cet enregistrement de pilote de périphérique.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |Nom du pilote de périphérique.  <br/> |
   

