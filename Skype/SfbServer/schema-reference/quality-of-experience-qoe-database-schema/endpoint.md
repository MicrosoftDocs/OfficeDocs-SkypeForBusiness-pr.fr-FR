---
title: Table Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882996"
---
# <a name="endpoint-table"></a>Table Endpoint
 
Le tableau du point de terminaison est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce point de terminaison.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nom du point de terminaison.  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |Système d’exploitation (OS) du point de terminaison.  <br/> |
|**NOMUC** <br/> |nvarchar (128)  <br/> ||Nom de l’UC du point de terminaison.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Nombre de cœurs d’UC du point de terminaison.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Vitesse du processeur du point de terminaison.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur binaire indiquant si le système est exécuté dans un environnement virtualisé : <br/>  0 x 0000 - aucun <br/>  0 x 0001 - HyperV <br/>  0 x 0002 - VMWare <br/>  0 x 0004 - virtual PC <br/>  0 x 0008 - PC Xen <br/> |
   

