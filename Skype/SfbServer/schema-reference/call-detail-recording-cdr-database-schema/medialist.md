---
title: Table MediaList
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 643c373eb7e6a73cf8755f14ea0f5497efee6fed
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849627"
---
# <a name="medialist-table"></a>Table MediaList
 
La table MediaList est une table statique qui stocke la liste de divers types de médias.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primaire  <br/> |Valeurs : 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Mappage statique des valeurs MediaID et Media : <br/>  1 – Messagerie instantanée <br/>  2 - Transfert de fichiers <br/>  3 - Assistance à distance <br/>  4 - Partage d’application <br/>  5 – Audio <br/>  6 – Vidéo <br/>  7 - Invitation d’application <br/> |
   
Si vous essayez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devez utiliser l’extrait de code join suivant : 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
