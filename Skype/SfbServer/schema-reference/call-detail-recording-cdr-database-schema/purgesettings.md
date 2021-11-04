---
title: Table PurgeSettings
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes sont supprimés automatiquement de la base de données d’enregistrement des détails des appels. Notez que les informations relatives au purge peuvent également être obtenues à partir du Skype Entreprise Server 2015 en exécutant la commande suivante :'
ms.openlocfilehash: a2b5bc874f6145a121cfb8a43702ab55ab0a5e1d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763312"
---
# <a name="purgesettings-table"></a>Table PurgeSettings
 
La table PurgeSettings contient des informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes sont supprimés automatiquement de la base de données d’enregistrement des détails des appels. Notez que les informations relatives au purge peuvent également être obtenues à partir du Skype Entreprise Server 2015 en exécutant la commande suivante :
  
```PowerShell
Get-CsCdrConfiguration
```

Les administrateurs doivent traiter la table PurgeSettings comme étant en lecture seule : les modifications apportées aux paramètres de purge des détails des appels doivent uniquement être apportées à l’aide des cmdlets [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique de la collection des paramètres de suppression des enregistrements des détails des appels.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Si la valeur est True (1), Skype Entreprise Server 2015 purge régulièrement les enregistrements obsolètes de la base de données d’enregistrement des enregistrements des documents. LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour. Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données. La valeur par défaut est True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Indique l’âge des enregistrements des détails des appels (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements des détails des appels dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Indique l’âge des enregistrements de rapport d’erreurs (en jours) qui seront supprimés de la base de données : si la suppression est activée, les enregistrements de rapport d’erreurs dont l’antériorité est supérieure à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Indique l’heure locale de la journée à laquelle la suppression de la base de données a lieu. L’heure de la journée est spécifiée à l’aide de l’horloge 24 heures, avec 0 qui représente minuit (00h00) et 23 qui représente 23h00. Notez que vous ne pouvez spécifier que l’heure de la journée : la valeur 10 (indiquant 10h00) est autorisée, mais la valeur 10,5 (indiquant 10h30) est interdite. La valeur par défaut est 2 (02h00).  <br/> |
