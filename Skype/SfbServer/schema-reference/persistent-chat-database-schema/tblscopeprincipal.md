---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues assignées aux nœuds.
ms.openlocfilehash: 5805356a882b659c864bf8b071198bfe695f342d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394796"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues assignées aux nœuds.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, non null  <br/> |ID du nœud auquel s’applique l’étendue.  <br/> |
|scopePrinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|scopeIsDenied  <br/> |bit, non null  <br/> |Valeur True si le type d’étendue est Refuser ; False pour Autoriser.  <br/> |
|scopeUpdatedBy  <br/> |int, non null  <br/> |ID du principal qui a mis à jour cette entrée en dernier.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clé primaire.  <br/> |
|scopeNodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

