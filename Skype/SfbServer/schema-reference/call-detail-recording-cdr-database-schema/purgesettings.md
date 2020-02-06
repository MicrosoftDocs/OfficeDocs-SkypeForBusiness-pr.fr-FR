---
title: Table PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La table PurgeSettings contient des informations qui spécifient si les enregistrements de détails des appels obsolètes seront automatiquement supprimés de la base de données CDR. Notez que les informations relatives à la purge peuvent également être obtenues dans Skype entreprise Server 2015 en exécutant la commande suivante :'
ms.openlocfilehash: 81e702a4d62b4c85fb849a768c97428719ddc391
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814962"
---
# <a name="purgesettings-table"></a>Table PurgeSettings
 
La table PurgeSettings contient des informations qui spécifient si les enregistrements de détails des appels obsolètes seront automatiquement supprimés de la base de données CDR. Notez que les informations relatives à la purge peuvent également être obtenues dans Skype entreprise Server 2015 en exécutant la commande suivante :
  
```PowerShell
Get-CsCdrConfiguration
```

Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : les modifications apportées aux paramètres de purge des détails des appels doivent uniquement être effectuées à l’aide des applets [de nouvelle-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la collection de paramètres de purge de CDR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Lorsque cette propriété est définie sur true (1) Skype entreprise Server 2015 supprime périodiquement les enregistrements obsolètes de la base de données CDR. La purge doit avoir lieu tous les jours sur le tome indiqué par le paramètre PurgeHour. Si elle a la valeur false (0), les enregistrements ne seront pas automatiquement supprimés de la base de données. La valeur par défaut est « True ».  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements CDR (en jours) qui seront supprimés de la base de données : si la suppression définitive est activée, les enregistrements CDR antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Spécifie l’âge des enregistrements de rapport d’erreur (en jours) qui seront supprimés de la base de données : si la purge est activée, les enregistrements de rapport d’erreur antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Spécifie l’heure locale du jour où le vidage de la base de données doit avoir lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (24 h) et 23 qui représente 23 h. Notez que vous pouvez seulement spécifier l’heure du jour : une valeur de 10 (indiquant 10:00 AM) est autorisée, mais une valeur de 10:30 de 10,5 (indiquant 10:30 AM) n’est pas autorisée. La valeur par défaut est 2 (2:00 AM).  <br/> |
   

