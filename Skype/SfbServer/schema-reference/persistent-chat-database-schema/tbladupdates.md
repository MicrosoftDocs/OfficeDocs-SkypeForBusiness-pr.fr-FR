---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329428"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID de principal de l’objet qui a changé.  <br/> |
|prinADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique de l’objet.  <br/> |
|prinAttributesChanged  <br/> |bit, non null  <br/> |True si au moins un attribut de l’objet a changé.  <br/> |
|prinMembersChanged  <br/> |bit, non null  <br/> |True si l’appartenance a changé.  <br/> |
|prinAffiliationsChanged  <br/> |bit, non null  <br/> |Inutilisé.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True si l’objet a été supprimé.  <br/> |
|lastUpdated  <br/> |datetime, non null  <br/> |Horodatage de l’insertion de la ligne.  <br/> |
   

