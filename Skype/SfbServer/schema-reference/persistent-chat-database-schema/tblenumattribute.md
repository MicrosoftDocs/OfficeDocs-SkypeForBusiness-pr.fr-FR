---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.
ms.openlocfilehash: 7e96b953cd7d53756dd184ae9b0e9190e9a529e0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763262"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut.  <br/> |
|attributeName  <br/> |nvarchar (256), non null  <br/> |Nom de l’attribut.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|attributeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs du tableau**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilité.  <br/> |
|2  <br/> |Comportement.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
