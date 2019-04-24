---
title: Table DeRegisterType dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213192"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Table DeRegisterType dans Skype pour Business Server 2015
 
La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 : inconnu <br/>  1--initiative du client désinscription <br/>  2--expiration de l’inscription <br/>  3 - client bloqué <br/>  4--modifié des attributs utilisateur <br/>  5 - serveurs d’inscriptions par défaut modifié <br/>  6--De Client hérité en Mode survie <br/> |
   

