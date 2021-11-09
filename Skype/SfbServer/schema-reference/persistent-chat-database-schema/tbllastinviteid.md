---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
ms.openlocfilehash: 56df4cf4002a67b665dfc33f1364493b07ac9ea7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855208"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
La table tblLastInviteId contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|lastInviteID  <br/> |int, non null  <br/> |ID d’invitation le plus récemment utilisé.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblPrincipalInvites](tblprincipalinvites.md)
