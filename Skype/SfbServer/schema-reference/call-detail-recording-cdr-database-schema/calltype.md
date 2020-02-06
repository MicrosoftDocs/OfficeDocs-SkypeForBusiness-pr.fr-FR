---
title: CallType table dans Skype entreprise Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui contient la liste des types d’appels possibles.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815432"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType table dans Skype entreprise Server 2015
 
La table CallType est une table statique qui contient la liste des types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées : <br/>  0--Inconnu <br/>  1-messagerie instantanée <br/>  2-partage d’application <br/>  3-audio <br/>  4-audio et vidéo <br/>  5-transfert de fichiers <br/> |
   

