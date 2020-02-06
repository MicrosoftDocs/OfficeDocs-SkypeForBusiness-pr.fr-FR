---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814072"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, pas null  <br/> |GUID principal du groupe qui a changé.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nom unique du membre.  <br/> |
|memberRemoved  <br/> |bit, pas null  <br/> |False si le membre a été ajouté. True si le membre a été supprimé.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Clé primaire.  <br/> |
   

