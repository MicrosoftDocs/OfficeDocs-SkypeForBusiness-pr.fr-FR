---
title: tblPrincipalMemberDifference
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
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.
ms.openlocfilehash: c59e99ce43b6e0dfa5a41f4bfc515aa8a95ed958
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601279"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal du groupe qui a été modifié.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nom unique du membre.  <br/> |
|memberRemoved  <br/> |bit, non null  <br/> |False si le membre a été ajouté. True si le membre a été supprimé.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Clé primaire.  <br/> |
   

