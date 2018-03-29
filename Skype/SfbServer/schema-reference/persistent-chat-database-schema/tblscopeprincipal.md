---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues affectées aux nœuds.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues affectées aux nœuds.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, non null  <br/> |ID de nœud que l’étendue s’applique à.  <br/> |
|scopePrinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|scopeIsDenied  <br/> |bits, non null  <br/> |True si le type d’étendue est Refuser ; False si autoriser.  <br/> |
|scopeUpdatedBy  <br/> |int, non null  <br/> |ID de l’entité de dernière mise à jour de cette entrée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clé primaire.  <br/> |
|scopeNodeID  <br/> |Clé étrangère avec la recherche dans la table de tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
   

