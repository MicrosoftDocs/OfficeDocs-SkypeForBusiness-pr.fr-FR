---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contient le dernier ID d’invitation qui a été généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId contient le dernier ID d’invitation qui a été généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|lastInviteID  <br/> |int, non null  <br/> |Dernier ID d’invitation utilisé.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

#### 

[tblPrincipalInvites](tblprincipalinvites.md)

