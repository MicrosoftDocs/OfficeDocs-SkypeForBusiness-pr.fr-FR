---
title: tblADUpdates
ms.reviewer: ''
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
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899602"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contient les modifications de Services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de la synchronisation Active Directory.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal de l’objet qui a été modifié.  <br/> |
|prinADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique de l’objet.  <br/> |
|prinAttributesChanged  <br/> |bit, non null  <br/> |True si au moins un attribut de l’objet a changé.  <br/> |
|prinMembersChanged  <br/> |bit, non null  <br/> |True si l’appartenance a changé.  <br/> |
|prinAffiliationsChanged  <br/> |bit, non null  <br/> |Non utilisé.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True si l’objet a été supprimé.  <br/> |
|lastUpdated  <br/> |DateTime, non null  <br/> |Horodatage de lors de l’insertion de la ligne.  <br/> |
   

