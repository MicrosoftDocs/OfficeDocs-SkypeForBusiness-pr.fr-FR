---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890768"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
la table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, non null  <br/> |ID du nœud auquel le rôle s’applique à.  <br/> |
|prinRolePrinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|prinRoleTypeID  <br/> |int, non null  <br/> |ID de type de rôle (d’après tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, non null  <br/> |ID du principal dernière mise à jour cette entrée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clé primaire.  <br/> |
|prinRoleNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Clé étrangère avec recherche dans la table tblRoleType.rtypeID.  <br/> |
   

