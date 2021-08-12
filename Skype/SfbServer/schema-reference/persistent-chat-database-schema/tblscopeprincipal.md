---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contient les étendues assignées aux nœuds.
ms.openlocfilehash: e86b259126ee58c26246e78e1afd44a5e5122cbdbaaabb7f0967bb2bba7e5d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337592"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contient les étendues assignées aux nœuds.
  
**Columns**

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
   

