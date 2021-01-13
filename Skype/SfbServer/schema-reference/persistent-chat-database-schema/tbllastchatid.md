---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816004"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (type de salle de conversation seulement).  <br/> |
|lastChatID  <br/> |bigint, non null  <br/> |ID de conversation le plus récemment utilisé.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clé principale (nodeID est suffisant pour le traitement).  <br/> |
|nodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblChat](tblchat.md)
