---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues attribuées aux nœuds.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812442"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues attribuées aux nœuds.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |ent, non null  <br/> |ID du nœud auquel s’applique l’étendue.  <br/> |
|scopePrinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|scopeIsDenied  <br/> |bit, pas null  <br/> |True si le type d’étendue est Deny ; False si Allow.  <br/> |
|scopeUpdatedBy  <br/> |ent, non null  <br/> |ID de l’élément principal qui a mis à jour cette entrée.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clé primaire.  <br/> |
|scopeNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeID.  <br/> |
|scopePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
   

