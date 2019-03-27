---
title: Table Devices dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau des périphériques est une table de prise en charge. Chaque enregistrement stocke des informations sur un périphérique (téléphone de bureau).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881701"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Table Devices dans Skype pour Business Server 2015
 
Le tableau des périphériques est une table de prise en charge. Chaque enregistrement stocke des informations sur un périphérique (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID de périphérique** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette version matérielle.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Étrangère  <br/> |Fabricant du périphérique. Voir la [table Manufacturers dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du matériel de ce périphérique. Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

