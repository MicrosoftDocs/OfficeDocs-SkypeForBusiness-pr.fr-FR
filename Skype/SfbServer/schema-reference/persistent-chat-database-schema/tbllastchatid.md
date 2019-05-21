---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295397"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|ID  <br/> |ent, non null  <br/> |ID de nœud (salle de conversation-type uniquement).  <br/> |
|lastChatID  <br/> |bigint, pas null  <br/> |Dernier ID de conversation utilisé.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clé primaire (uniquement nodeID est suffisante pour le traitement).  <br/> |
|ID  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblChat](tblchat.md)
