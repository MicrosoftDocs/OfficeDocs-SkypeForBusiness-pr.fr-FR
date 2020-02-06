---
title: Table CallPriorities dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que « urgence », « urgent » ou « normale ».
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815442"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Table CallPriorities dans Skype entreprise Server 2015
 
La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que « urgence », « urgent » ou « normale ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Priorité** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0-Inconnu <br/>  1-non urgent <br/>  2-normal <br/>  3-urgent <br/>  4-urgence <br/> |
   

