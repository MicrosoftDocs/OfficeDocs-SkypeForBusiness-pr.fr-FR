---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831554"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
  
**Columns**

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
   

