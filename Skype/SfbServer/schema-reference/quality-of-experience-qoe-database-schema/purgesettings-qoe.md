---
title: Table PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements de qualité de l’expérience obsolètes seront automatiquement supprimés de la base de données QoE. Notez que le vidage-informations peuvent également être obtenues dans le Skype pour Business Server Management Shell en exécutant la commande suivante :'
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924786"
---
# <a name="purgesettings-table-qoe"></a>Table PurgeSettings (QoE)
 
La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements de qualité de l’expérience obsolètes seront automatiquement supprimés de la base de données QoE. Notez que le vidage-informations peuvent également être obtenues dans le Skype pour Business Server Management Shell en exécutant la commande suivante :
  
```
Get-CsQoEConfiguration
```

Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Paramètres de suppression de l’identificateur unique de la collection de QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsque défini sur True (1) Microsoft Lync Server 2013 sera régulièrement purge des enregistrements obsolètes à partir de la base de données QoE. Le vidage aura lieu chaque jour à la Tomé spécifiée par le paramètre PurgeHour. Si défini sur False (0) enregistrement puis ne système pas vidée automatiquement à partir de la base de données. La valeur par défaut est « True ».  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements QoE (en jours) qui seront purgées à partir de la base de données : si le vidage est activé, les enregistrements QoE plus anciens que cette valeur seront supprimées à partir de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale du jour où le vidage de base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais la valeur 10:30 de 10.5 (indiquant 10:30:00) n’est pas autorisée. La valeur par défaut est 1 (1 h 00). Spécifie l’heure locale du jour où le vidage de base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez spécifier l’heure de la journée : une valeur de 10 (indiquant de 10:00:00) est autorisée, mais la valeur 10:30 de 10.5 (indiquant 10:30:00) n’est pas autorisée. La valeur par défaut est 1 (1 h 00).  <br/> |
   

