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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814582"
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
