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
description: tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et comportement qui sont utilisés dans la table Node.
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504865"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et comportement qui sont utilisés dans la table Node.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut.  <br/> |
|attributeName  <br/> |nvarchar (256), non null  <br/> |Nom de l’attribut.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|attributeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs de table**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilité.  <br/> |
|2  <br/> |Comportement.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)