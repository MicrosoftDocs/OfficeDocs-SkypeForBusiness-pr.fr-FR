---
title: Table CallPriorities dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ( urgence), « urgent » ou « normal ».
ms.openlocfilehash: ed31d55852f0b685429bd7fbf70cff1bf81d63ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845137"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Table CallPriorities dans Skype Entreprise Server 2015
 
La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ( urgence), « urgent » ou « normal ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primaire  <br/> ||
|**Priorité** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Non urgent <br/>  2 - Normal <br/>  3 - Urgent <br/>  4 - Très urgent <br/> |
   

