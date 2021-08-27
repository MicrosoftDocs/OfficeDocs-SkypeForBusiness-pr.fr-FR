---
title: Table MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: a72a409e9cc50fb5c8a7b340674276299e0ac4e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596418"
---
# <a name="medialist-table"></a>Table MediaList
 
La table MediaList est une table statique qui stocke la liste de divers types de médias.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primaire  <br/> |Valeurs : 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Mappage statique des valeurs MediaID et Media : <br/>  1 – Messagerie instantanée <br/>  2 - Transfert de fichiers <br/>  3 - Assistance à distance <br/>  4 - Partage d’application <br/>  5 – Audio <br/>  6 – Vidéo <br/>  7 - Invitation d’application <br/> |
   
Si vous essayez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devez utiliser l’extrait de code join suivant : 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
