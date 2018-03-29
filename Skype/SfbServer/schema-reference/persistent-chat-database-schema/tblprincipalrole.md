---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contient les rôles explicites attribuées à des nœuds.
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contient les rôles explicites attribuées à des nœuds.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, non null  <br/> |ID de nœud que le rôle s’applique à.  <br/> |
|prinRolePrinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|prinRoleTypeID  <br/> |int, non null  <br/> |ID de type de rôle (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, non null  <br/> |ID de l’entité de dernière mise à jour de cette entrée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clé primaire.  <br/> |
|prinRoleNodeID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Clé étrangère avec la recherche dans la table de tblRoleType.rtypeID.  <br/> |
   

