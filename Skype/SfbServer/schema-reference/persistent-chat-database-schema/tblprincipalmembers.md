---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contient les appartenances des principaux.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904159"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contient les appartenances des principaux.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|memberADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique de membre. Un membre n’a pas à une entité (dans la table tblPrincipal).  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans tblPrincipal.prinID.  <br/> |
   

