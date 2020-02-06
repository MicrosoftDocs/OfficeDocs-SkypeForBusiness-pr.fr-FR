---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contient des rôles explicites attribués aux nœuds.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813362"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contient des rôles explicites attribués aux nœuds.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |ent, non null  <br/> |ID du nœud auquel le rôle s’applique.  <br/> |
|prinRolePrinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|prinRoleTypeID  <br/> |ent, non null  <br/> |ID du type de rôle (de tblRoleType)  <br/> |
|prinRoleUpdatedBy  <br/> |ent, non null  <br/> |ID de l’élément principal qui a mis à jour cette entrée.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clé primaire.  <br/> |
|prinRoleNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeID.  <br/> |
|prinRolePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
|prinRoleTypeID  <br/> |Clé étrangère avec recherche dans la table tblRoleType. rtypeID.  <br/> |
   

