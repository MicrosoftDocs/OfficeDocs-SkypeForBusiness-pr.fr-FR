---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est un tableau codé en dur qui contient les attributs de visibilité et le comportement qui sont utilisés dans la table des nœuds.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute est un tableau codé en dur qui contient les attributs de visibilité et le comportement qui sont utilisés dans la table des nœuds.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut.  <br/> |
|attributeName  <br/> |nvarchar (256), non null  <br/> |Nom de l’attribut.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|attributeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs de la table**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilité.  <br/> |
|2  <br/> |Comportement.  <br/> |
   
## <a name="see-also"></a>Voir aussi

#### 

[tblNode](tblnode.md)

