---
title: Table Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930303"
---
# <a name="roles-table"></a>Table Roles
 
La table Roles est une table statique qui stocke la liste des rôles possibles pour les conférences, tels que participant et présentateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rôle** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 - inconnu <br/>  1 - présentateur <br/>  2 - participant <br/> |
   

