---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour tous les nœuds d’invitation automatique activée.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924422"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour tous les nœuds d’invitation automatique activée.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|invID  <br/> |int, non null  <br/> |Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.  <br/> |
|nodeID  <br/> |int, non null  <br/> |ID de nœud (salle de conversation uniquement).  <br/> |
|Créé  <br/> |DateTime, non null  <br/> |Heure de création.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clé étrangère avec recherche dans la table tblNode.nodeID.  <br/> |
   

