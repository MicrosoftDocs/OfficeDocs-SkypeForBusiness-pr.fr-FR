---
title: Table MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La table MediaList est une table statique qui stocke la liste de divers types de médias.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930650"
---
# <a name="medialist-table"></a>Table MediaList
 
La table MediaList est une table statique qui stocke la liste de divers types de médias.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principal  <br/> |Valeur : 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Mappage statique de MediaID et des valeurs média : <br/>  1 – Messagerie instantanée <br/>  -2 transfert de fichiers <br/>  3 - Assistance à distance <br/>  -4 partage d’application <br/>  5 – Audio <br/>  6 – Vidéo <br/>  -7 invitation d’application <br/> |
   
Si vous tentez de déterminer le type de modalité pour les valeurs dans LcsCDR.SessionDetailsView.MediaTypes, vous devrez utiliser l’extrait de Joindre suivant :  
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
