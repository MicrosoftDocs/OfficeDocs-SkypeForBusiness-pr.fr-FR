---
title: Table PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE. Notez que les informations relatives au purge peuvent également être obtenues à partir de l’Skype Entreprise Server Management Shell en exécutant la commande suivante :'
ms.openlocfilehash: 2c6eada1b64d5ba4ac1ee34185d89c31abcbd3c0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763112"
---
# <a name="purgesettings-table-qoe"></a>Table PurgeSettings (QoE)
 
La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE. Notez que les informations relatives au purge peuvent également être obtenues à partir de l’Skype Entreprise Server Management Shell en exécutant la commande suivante :
  
```PowerShell
Get-CsQoEConfiguration
```

Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique pour la collecte des paramètres de vidage QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsque la valeur est True (1), Microsoft Lync Server 2013 purge régulièrement les enregistrements obsolètes de la base de données QoE. LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour. Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données. La valeur par défaut est True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si le vidage est activé, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).  <br/> |
   

