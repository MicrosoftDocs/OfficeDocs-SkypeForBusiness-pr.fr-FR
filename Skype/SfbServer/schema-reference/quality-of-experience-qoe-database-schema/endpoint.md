---
title: Table Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809552"
---
# <a name="endpoint-table"></a>Table Endpoint
 
La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce point de terminaison.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> |Différent  <br/> |Nom du point de terminaison.  <br/> |
|**OS** <br/> |nvarchar(128  <br/> | <br/> |Système d’exploitation (se) du point de terminaison.  <br/> |
|**CPUName** <br/> |nvarchar(128  <br/> ||Nom de l’UC du point de terminaison.  <br/> |
|**CPUNumberOfCores** <br/> |type  <br/> ||Nombre de cœurs d’UC du point de terminaison.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Vitesse de processeur de l’UC du point de terminaison.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé : <br/>  0x0000-aucun <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-PC virtuel <br/>  0x0008-Xen PC <br/> |
   

