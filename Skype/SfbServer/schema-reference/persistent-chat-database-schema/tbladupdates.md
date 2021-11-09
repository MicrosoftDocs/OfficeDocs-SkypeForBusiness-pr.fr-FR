---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.
ms.openlocfilehash: 00c3cce25b3e69372813721192677956ec8a15d4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839826"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes de synchronisation Active Directory ultérieures.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID de principal de l’objet qui a changé.  <br/> |
|prinADPath  <br/> |nvarchar (384), non null  <br/> |Nom unique de l’objet.  <br/> |
|prinAttributesChanged  <br/> |bit, non null  <br/> |True si au moins un attribut de l’objet a changé.  <br/> |
|prinMembersChanged  <br/> |bit, non null  <br/> |True si l’appartenance a changé.  <br/> |
|prinAffiliationsChanged  <br/> |bit, non null  <br/> |Inutilisé.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True si l’objet a été supprimé.  <br/> |
|lastUpdated  <br/> |datetime, non null  <br/> |Horodatage de l’insertion de la ligne.  <br/> |
   

