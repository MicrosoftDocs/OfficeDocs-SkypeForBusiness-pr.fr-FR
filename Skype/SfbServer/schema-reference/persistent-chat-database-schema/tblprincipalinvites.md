---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814182"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|invID  <br/> |ent, non null  <br/> |Numéro séquentiel unique (par ID principal) généré à partir de la table tblLastInviteId.  <br/> |
|ID  <br/> |ent, non null  <br/> |ID de nœud (salle de conversation uniquement).  <br/> |
|Created  <br/> |DATEHEURE, pas null  <br/> |Heure de création  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
|ID  <br/> |Clé étrangère avec recherche dans la table tblNode. nodeID.  <br/> |
   

