---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les identités qui doivent être actualisées à partir des Services de domaine Active Directory.
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contient les identités qui doivent être actualisées à partir des Services de domaine Active Directory.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|prinAffiliationsDirty  <br/> |bits, non null  <br/> |True si l’entité de sécurité affiliations doivent être actualisées.  <br/> |
|prinAttributesDirty  <br/> |bits, non null  <br/> |True si l’entité de sécurité attributs doivent être actualisées.  <br/> |
|prinDeleted  <br/> |bits, non null  <br/> |True si l’entité de sécurité a été supprimée.  <br/> |
|tryCount  <br/> |int  <br/> |Nombre de tentatives d’actualisation de l’entité de sécurité AD DS qui ont eu lieu jusqu'à présent.  <br/> |
|lastTry  <br/> |DateHeure  <br/> |Horodatage de la dernière tentative d’actualisation de l’entité de sécurité. Peut être null si aucune actualisation n’a été tentée encore.  <br/> |
|nextTry  <br/> |DateHeure  <br/> |Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation a été planifiée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
   

