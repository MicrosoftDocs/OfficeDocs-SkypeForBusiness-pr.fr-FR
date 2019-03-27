---
title: Table CallPriorities dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882989"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Table CallPriorities dans Skype pour Business Server 2015
 
La table CallPriorities est une table statique qui stocke la liste des priorités d’appel possibles, telles que « d’urgence », « urgent » ou « normal ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Priorité** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - inconnu <br/>  1 – non Urgent <br/>  2 - normale <br/>  3 - urgent <br/>  4 - très urgent <br/> |
   

