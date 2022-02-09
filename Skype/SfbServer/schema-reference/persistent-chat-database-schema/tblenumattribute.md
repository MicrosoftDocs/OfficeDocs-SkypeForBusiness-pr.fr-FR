---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 9e169ed908abc4e3184f2ea26b25b9d5554df06f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403638"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
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
