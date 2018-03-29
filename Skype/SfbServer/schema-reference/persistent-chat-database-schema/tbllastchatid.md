---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contient le dernier ID de conversation qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (salle de conversation de type uniquement).  <br/> |
|lastChatID  <br/> |bigint, non null  <br/> |Dernier ID de conversation d’utilisés.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clé primaire (nodeID uniquement est suffisant pour le traitement).  <br/> |
|nodeID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

#### 

[tblChat](tblchat.md)

