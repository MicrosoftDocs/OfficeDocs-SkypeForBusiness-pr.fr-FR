---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient des membres principaux.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contient des membres principaux.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|memberADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique d’un membre. Un membre n’a pas à être une entité (dans la table de tblPrincipal).  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec la recherche dans tblPrincipal.prinID.  <br/> |
   

