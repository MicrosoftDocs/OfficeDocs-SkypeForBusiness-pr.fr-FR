---
title: Table CallPriorities dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ou « normal ».
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813434"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Table CallPriorities dans Skype Entreprise Server 2015
 
La table CallPriorities est une table statique qui stocke la liste des priorités d’appels possibles, telles que « urgence » ou « normal ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primaire  <br/> ||
|**Priorité** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Non urgent <br/>  2 - Normal <br/>  3 - Urgent <br/>  4 - Très urgent <br/> |
   

