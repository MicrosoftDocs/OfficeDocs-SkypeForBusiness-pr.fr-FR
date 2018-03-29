---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, pas null  <br/> |Entité de GUID de l’objet modifié.  <br/> |
|prinADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique de l’objet.  <br/> |
|prinAttributesChanged  <br/> |bits, non null  <br/> |True si au moins un attribut de l’objet modifié.  <br/> |
|prinMembersChanged  <br/> |bits, non null  <br/> |True si l’appartenance est modifiée.  <br/> |
|prinAffiliationsChanged  <br/> |bits, non null  <br/> |Non utilisé.  <br/> |
|prinDeleted  <br/> |bits, non null  <br/> |True si l’objet a été supprimé.  <br/> |
|lastUpdated  <br/> |DateTime, non null  <br/> |Date et heure du lorsque la ligne a été insérée.  <br/> |
   

