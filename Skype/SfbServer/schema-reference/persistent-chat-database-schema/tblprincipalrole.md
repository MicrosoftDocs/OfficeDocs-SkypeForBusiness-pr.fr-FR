---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
ms.openlocfilehash: 6c9960c4eafc2d28a4710a8e4dded6bea19c841a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828527"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
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
   

