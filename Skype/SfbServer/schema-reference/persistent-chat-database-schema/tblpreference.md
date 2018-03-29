---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contient les préférences de l’utilisateur client. Elle est généralement utilisée par des clients antérieurs à Lync 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference contient les préférences de l’utilisateur client. Elle est généralement utilisée par des clients antérieurs à Lync 2013.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255), non null  <br/> |Étiquette avec un format tel que : \<utilisateur sip uri\>|nom d’utilisateur. \<préférences\>.  <br/> |
|prefSeqID  <br/> |int, non null  <br/> |Un numéro séquentiel (par étiquette) à des fins de contrôle de version.  <br/> |
|prefContent  <br/> |nvarchar (max)  <br/> |Contenu codé.  <br/> |
|lastModifiedBy  <br/> |int, non null  <br/> |ID de l’entité de la préférence de mise à jour.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clé primaire.  <br/> |
   

