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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: 9242f20b3c2192fb1f5cd48c84784a3e8d283f6e91587aee408a9286d291add7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326270"
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
