---
title: Table Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a>Table Endpoint
 
Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce point de terminaison.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nom du point de terminaison.  <br/> |
|**SYSTÈME D’EXPLOITATION** <br/> |nvarchar (128)  <br/> | <br/> |Système d’exploitation (OS) du point de terminaison.  <br/> |
|**NOMUC** <br/> |nvarchar (128)  <br/> ||Nom du processeur du point de terminaison.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Nombre de coeurs de processeur du point de terminaison.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Vitesse de processeur du processeur du point de terminaison.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur binaire qui indique si le système est en cours d’exécution dans un environnement virtualisé : <br/>  0 x 0000 - aucun <br/>  0 x 0001 - HyperV <br/>  0 x 0002 - VMWare <br/>  0 x 0004 - virtual PC <br/>  0 x 0008 - Xen PC <br/> |
   

