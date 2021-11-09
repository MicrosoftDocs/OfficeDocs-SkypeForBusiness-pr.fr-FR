---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.
ms.openlocfilehash: d7993cba89474fe5d7343cd25f39c3363b8be866
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864581"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|invID  <br/> |int, non null  <br/> |Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.  <br/> |
|nodeID  <br/> |int, non null  <br/> |ID de nœud (salle de conversation uniquement).  <br/> |
|createdOn  <br/> |datetime, non null  <br/> |Heure de création.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
   

