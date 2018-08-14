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
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505088"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, non null  <br/> |ID de nœud (salle de conversation de type uniquement).  <br/> |
|lastChatID  <br/> |bigint, non null  <br/> |Dernier ID de conversation utilisé.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clé primaire (nodeID est suffisant pour le traitement).  <br/> |
|nodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblChat](tblchat.md)