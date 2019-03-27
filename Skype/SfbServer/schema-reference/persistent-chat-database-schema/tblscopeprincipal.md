---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885623"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues affectées aux nœuds.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, non null  <br/> |ID du nœud auquel s’applique à l’étendue.  <br/> |
|scopePrinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|scopeIsDenied  <br/> |bit, non null  <br/> |True si le type d’étendue est Refuser ; False pour autoriser.  <br/> |
|scopeUpdatedBy  <br/> |int, non null  <br/> |ID du principal dernière mise à jour cette entrée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clé primaire.  <br/> |
|scopeNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

