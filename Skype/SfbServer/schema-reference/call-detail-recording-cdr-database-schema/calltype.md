---
title: Table CallType dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui stocke la liste des types d’appels possibles.
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883178"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Table CallType dans Skype pour Business Server 2015
 
La table CallType est une table statique qui stocke la liste des types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées : <br/>  0 : inconnu <br/>  1 - pic <br/>  2 : Partage d’application <br/>  3--audio <br/>  4 - audio et vidéo <br/>  5 - transfert de fichiers <br/> |
   

