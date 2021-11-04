---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 7ab281b31869b4a761a6360978b57ec9591daaf0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741880"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
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
