---
title: Table de périphériques dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La table des périphériques est une table de prise en charge. Chaque enregistrement contient des informations sur un périphérique (téléphone de bureau).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Table de périphériques dans Skype pour Business Server 2015
 
La table des périphériques est une table de prise en charge. Chaque enregistrement contient des informations sur un périphérique (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID de périphérique** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant la version de ce matériel.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Étrangère  <br/> |Fabricant de ce périphérique. Consultez le [tableau des fabricants dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du matériel de ce périphérique. Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations. <br/> |
|**Adresse MAC** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

