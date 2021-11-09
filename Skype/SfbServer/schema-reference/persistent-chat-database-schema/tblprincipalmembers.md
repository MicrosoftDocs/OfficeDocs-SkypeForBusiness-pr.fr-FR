---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient les appartenances principales.
ms.openlocfilehash: 130ca3cc7f57435f95add202f6af13660bf71610
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842606"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contient les appartenances principales.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|memberADPath  <br/> |nvarchar (384), non null  <br/> |Nom d’un membre. Un membre n’a pas besoin d’être un principal (dans la table tblPrincipal).  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans tblPrincipal.prinID.  <br/> |
   

