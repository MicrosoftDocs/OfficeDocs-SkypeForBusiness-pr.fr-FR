---
title: Table de PurgeSettings
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La table PurgeSettings contient des informations indiquant si (et quand) des enregistrements de détail des appels obsolètes seront automatiquement supprimés de la base de données de CD-r. Notez que liés à la purge des informations peuvent également être obtenues dans le Skype pour Business Server 2015 en exécutant la commande suivante :'
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a>Table de PurgeSettings
 
La table PurgeSettings contient des informations indiquant si (et quand) des enregistrements de détail des appels obsolètes seront automatiquement supprimés de la base de données de CD-r. Notez que liés à la purge des informations peuvent également être obtenues dans le Skype pour Business Server 2015 en exécutant la commande suivante :
  
```
Get-CsCdrConfiguration
```

Les administrateurs doivent traiter la table PurgeSettings en lecture seule : les paramètres de purge de détail appel doit uniquement être modifiées à l’aide des applets de commande [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [CsCdrConfiguration de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la collection de CD-r purger les paramètres.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsqu’elle est définie sur True (1) Skype pour Business Server 2015 va purger périodiquement obsolètes des enregistrements à partir de la base de données de CD-r. Purge aura lieu chaque jour au tome spécifié par le paramètre PurgeHour. Si la valeur False (0) enregistrement puis ne sera pas purgée automatiquement à partir de la base de données. La valeur par défaut est True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Spécifie la durée de vie des enregistrements de CD-r (en jours) qui doivent être supprimés à partir de la base de données : si le vidage est activé, les enregistrements CDR antérieures à cette valeur seront supprimés à partir de la base de données. La valeur par défaut est de 60 jours.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Spécifie la durée de vie rapport des enregistrements d’erreur (en jours) qui doivent être supprimés à partir de la base de données : si le vidage est activé, enregistrements de rapport d’erreurs plus anciennes que cette valeur seront supprimés à partir de la base de données. La valeur par défaut est de 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale de la journée lorsque la purge de la base de données aura lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous ne pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais une valeur de 10:30 de 10.5 (indiquant de 10:30 AM) n’est pas autorisée. La valeur par défaut est 2 (2:00 AM).  <br/> |
   

