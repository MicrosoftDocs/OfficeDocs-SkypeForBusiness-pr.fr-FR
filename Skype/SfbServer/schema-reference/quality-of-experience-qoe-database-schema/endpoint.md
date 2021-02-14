---
title: Table Endpoint
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823064"
---
# <a name="endpoint-table"></a>Table Endpoint
 
La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce point de terminaison.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du point de terminaison.  <br/> |
|**SYSTÈME D’EXPLOITATION** <br/> |nvarchar(128)  <br/> | <br/> |Système d’exploitation du point de terminaison.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nom du processeur du point de terminaison.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Nombre de cœurs d’UC du point de terminaison.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Vitesse du processeur processeur du point de terminaison.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur de bits qui indique si le système s’exécute dans un environnement virtualisé : <br/>  0x0000 - Aucun <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - Virtual PC <br/>  0x0008 - Xen PC <br/> |
   

