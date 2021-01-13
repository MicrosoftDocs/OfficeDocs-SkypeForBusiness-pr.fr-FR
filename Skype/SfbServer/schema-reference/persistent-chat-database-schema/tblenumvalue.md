---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816024"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue est une table codée en dur qui contient les valeurs Visibilité et Comportement des attributs utilisés dans la table Node.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, non null  <br/> |ID de la valeur  <br/> |
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut  <br/> |
|attributeValue  <br/> |nvarchar (256), non null  <br/> |Nom de la valeur.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|valueID  <br/> |Clé primaire.  <br/> |
|attributeID  <br/> |Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.  <br/> |
   
**Valeurs de la table**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |portée  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |auditorium  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
