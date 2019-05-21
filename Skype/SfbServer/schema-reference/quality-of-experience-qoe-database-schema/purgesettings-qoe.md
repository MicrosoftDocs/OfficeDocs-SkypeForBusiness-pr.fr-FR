---
title: Table PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La table PurgeSettings contient des informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE. Notez que les informations relatives à la purge peuvent également être obtenues dans Skype entreprise Server Management Shell en exécutant la commande suivante:'
ms.openlocfilehash: ec957a445c59020e8909beeb8cb3dcd12f662d68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294774"
---
# <a name="purgesettings-table-qoe"></a>Table PurgeSettings
 
La table PurgeSettings contient des informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE. Notez que les informations relatives à la purge peuvent également être obtenues dans Skype entreprise Server Management Shell en exécutant la commande suivante:
  
```
Get-CsQoEConfiguration
```

Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la collection de paramètres de purge QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsque cette propriété est définie sur true (1) Microsoft Lync Server 2013 supprime périodiquement les enregistrements obsolètes de la base de données QoE. La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour. Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données. La valeur par défaut est « True ».  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données: si la purge est activée, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour: une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour: une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).  <br/> |
   

