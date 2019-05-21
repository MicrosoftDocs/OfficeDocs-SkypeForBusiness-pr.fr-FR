---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295558"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, pas null  <br/> |GUID principal de l’objet qui a changé.  <br/> |
|prinADPath  <br/> |nvarchar (384), pas null  <br/> |Nom unique de l’objet.  <br/> |
|prinAttributesChanged  <br/> |bit, pas null  <br/> |Vrai si au moins un attribut de l’objet a changé.  <br/> |
|prinMembersChanged  <br/> |bit, pas null  <br/> |True si l’appartenance a changé.  <br/> |
|prinAffiliationsChanged  <br/> |bit, pas null  <br/> |Non utilisé.  <br/> |
|prinDeleted  <br/> |bit, pas null  <br/> |True si l’objet a été supprimé.  <br/> |
|lastUpdated  <br/> |DATEHEURE, pas null  <br/> |Horodatage de la date d’insertion de la ligne.  <br/> |
   

