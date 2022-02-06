---
title: tblPrincipalInvites
ms.reviewer: null
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.
---

# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
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
   

