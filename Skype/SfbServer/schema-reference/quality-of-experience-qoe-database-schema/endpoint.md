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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La table Endpoint est une table qui contient des informations sur les points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294991"
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
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicateur binaire indiquant si le système s’exécute dans un environnement virtualisé: <br/>  0x0000-aucun <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-PC virtuel <br/>  0x0008-Xen PC <br/> |
   

