---
title: Table Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814932"
---
# <a name="roles-table"></a>Table Roles
 
La table rôles est une table statique qui contient la liste des rôles de conférence possibles, tels que participant et présentateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rôle** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0-Inconnu <br/>  1-présentateur <br/>  2 participants <br/> |
   

