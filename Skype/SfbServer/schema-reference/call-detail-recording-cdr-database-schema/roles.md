---
title: Table Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
ms.openlocfilehash: 38999dd3d90dc39ac2afea9c667224f73da7208c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394866"
---
# <a name="roles-table"></a>Table Roles
 
La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primaire  <br/> ||
|**Role** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Présentateur <br/>  2 - Participant <br/> |
   

