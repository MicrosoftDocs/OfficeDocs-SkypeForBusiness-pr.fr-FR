---
title: Table de PurgeSettings (QoE)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La table PurgeSettings contient des informations indiquant si (et quand) des enregistrements de qualité obsolètes seront automatiquement supprimés de la base de données QoE. Notez que liés à la purge des informations peuvent également être obtenues dans le Skype pour Business Server Management Shell en exécutant la commande suivante :'
ms.openlocfilehash: 1acccbd796e20f099df895260cb34f9597718cdd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table-qoe"></a>Table de PurgeSettings (QoE)
 
La table PurgeSettings contient des informations indiquant si (et quand) des enregistrements de qualité obsolètes seront automatiquement supprimés de la base de données QoE. Notez que liés à la purge des informations peuvent également être obtenues dans le Skype pour Business Server Management Shell en exécutant la commande suivante :
  
```
Get-CsQoEConfiguration
```

Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la collection de QoE purger les paramètres.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsque la valeur True (1) Microsoft Lync Server 2013 sera purger périodiquement les enregistrements obsolètes à partir de la base de données QoE. Purge aura lieu chaque jour au tome spécifié par le paramètre PurgeHour. Si la valeur False (0) enregistrement puis ne sera pas purgée automatiquement à partir de la base de données. La valeur par défaut est True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Spécifie la durée de vie des enregistrements QoE (en jours) qui doivent être supprimés à partir de la base de données : si le vidage est activé, les enregistrements QoE antérieures à cette valeur seront supprimés à partir de la base de données. La valeur par défaut est de 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale de la journée lorsque la purge de la base de données aura lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous ne pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais une valeur de 10:30 de 10.5 (indiquant de 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale de la journée lorsque la purge de la base de données aura lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous ne pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais une valeur de 10:30 de 10.5 (indiquant de 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).  <br/> |
   

