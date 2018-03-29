---
title: Table Roles
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Le tableau rôles est une table statique qui stocke la liste des rôles de conférence possible, par exemple du présentateur ou du participant.
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a>Table Roles
 
Le tableau rôles est une table statique qui stocke la liste des rôles de conférence possible, par exemple du présentateur ou du participant.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rôle** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - inconnu <br/>  1 - présentateur <br/>  2 - participant <br/> |
   

