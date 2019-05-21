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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que «urgence», «urgent» ou «normale».
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296566"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Table CallPriorities dans Skype entreprise Server 2015
 
La table CallPriorities est une table statique qui contient la liste des différentes priorités d’appel, telles que «urgence», «urgent» ou «normale».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Priorité** <br/> |nvarchar(256)  <br/> || Valeurs autorisées: <br/>  0-Inconnu <br/>  1-non urgent <br/>  2-normal <br/>  3-urgent <br/>  4-urgence <br/> |
   

