---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.
ms.openlocfilehash: c52f1290eb0da442ffed9f8d8b645423b6f6c59c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410667"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes de synchronisation des services de domaine Active Directory ultérieures.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal du groupe qui a été modifié.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nom unique du membre.  <br/> |
|memberRemoved  <br/> |bit, non null  <br/> |False si le membre a été ajouté. True si le membre a été supprimé.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Clé primaire.  <br/> |
   

