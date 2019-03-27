---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885553"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contient le groupe d’appartenance modifications (à la fois membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation des Services de domaine Active Directory.
  
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
   

