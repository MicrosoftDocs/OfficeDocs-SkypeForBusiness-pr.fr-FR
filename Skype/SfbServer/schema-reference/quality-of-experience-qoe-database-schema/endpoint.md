---
title: Table Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 4085b8e22aea565054dbb03de10808712c54361e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399558"
---
# <a name="endpoint-table"></a>Table Endpoint
 
La table Endpoint est une table de prise en charge qui stocke des informations sur les points de terminaison qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce point de terminaison.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du point de terminaison.  <br/> |
|**Système d’exploitation** <br/> |nvarchar(128)  <br/> | <br/> |Système d’exploitation du point de terminaison.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nom du processeur du point de terminaison.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Nombre de cœurs d’UC du point de terminaison.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Vitesse du processeur processeur du point de terminaison.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur de bits qui indique si le système s’exécute dans un environnement virtualisé : <br/>  0x0000 - Aucun <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - Virtual PC <br/>  0x0008 - Xen PC <br/> |
   

