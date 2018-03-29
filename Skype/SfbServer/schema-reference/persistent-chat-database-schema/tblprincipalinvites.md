---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs mis en service pour tous les nœuds avec auto-invitation sur.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contient des invitations pour tous les utilisateurs mis en service pour tous les nœuds avec auto-invitation sur.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|invID  <br/> |int, non null  <br/> |Numéro séquentiel unique (par ID de l’entité de sécurité) généré à partir de la table de tblLastInviteId.  <br/> |
|nodeID  <br/> |int, non null  <br/> |ID de nœud (conversation).  <br/> |
|createdOn  <br/> |DateTime, non null  <br/> |Heure de création.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeID.  <br/> |
   

