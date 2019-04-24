---
title: Table PurgeSettings
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La table PurgeSettings contient des informations qui indiquent si (et quand) des détails des appels obsolètes seront automatiquement supprimés de la base de données CDR. Notez que le vidage-informations peuvent également être obtenues dans le Skype pour Business Server 2015 en exécutant la commande suivante :'
ms.openlocfilehash: 10dd9c6969f84453c880de130222b3b9d71db77a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212837"
---
# <a name="purgesettings-table"></a>Table PurgeSettings
 
La table PurgeSettings contient des informations qui indiquent si (et quand) des détails des appels obsolètes seront automatiquement supprimés de la base de données CDR. Notez que le vidage-informations peuvent également être obtenues dans le Skype pour Business Server 2015 en exécutant la commande suivante :
  
```
Get-CsCdrConfiguration
```

Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : modifications dans les paramètres de purge détail appel doivent être effectuées uniquement à l’aide des applets de commande [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la collection des détails des paramètres de suppression.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsqu’elle est définie sur True (1) Skype pour Business Server 2015 sera purger périodiquement obsolètes les enregistrements de la base de données CDR. Le vidage aura lieu chaque jour à la Tomé spécifiée par le paramètre PurgeHour. Si défini sur False (0) enregistrement puis ne système pas vidée automatiquement à partir de la base de données. La valeur par défaut est « True ».  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements des détails des appels (en jours) qui seront purgées à partir de la base de données : si le vidage est activé, les enregistrements des détails des appels antérieurs à cette valeur seront supprimées à partir de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Spécifie l’âge rapport des enregistrements d’erreur (en jours) qui seront purgées à partir de la base de données : si le vidage est activé, enregistrements de rapport d’erreurs plus anciens que cette valeur seront supprimées de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale du jour où le vidage de base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais la valeur 10:30 de 10.5 (indiquant 10:30:00) n’est pas autorisée. La valeur par défaut est 2 (2:00 AM).  <br/> |
   

