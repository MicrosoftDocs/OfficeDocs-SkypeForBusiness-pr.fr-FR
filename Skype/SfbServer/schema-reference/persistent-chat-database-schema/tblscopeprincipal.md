---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues assignées aux nœuds.
ms.openlocfilehash: 84fa792a6698a474e41c0e623b826fb0b8c48d65
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844027"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues assignées aux nœuds.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
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
   

