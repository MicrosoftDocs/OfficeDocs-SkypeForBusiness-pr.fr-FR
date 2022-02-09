---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 3c4af0f5022afc25212c50b44ff19c28946df97d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399568"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |entier, non null  <br/> |ID du nœud auquel le rôle s’applique.  <br/> |
|prinRolePrinID  <br/> |entier, non null  <br/> |ID du principal.  <br/> |
|prinRoleTypeID  <br/> |entier, non null  <br/> |ID du type de rôle (d’après tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |entier, non null  <br/> |ID du principal qui a mis à jour cette entrée en dernier.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clé primaire.  <br/> |
|prinRoleNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Clé étrangère avec recherche dans la table tblRoleType.rtypeID.  <br/> |
   

