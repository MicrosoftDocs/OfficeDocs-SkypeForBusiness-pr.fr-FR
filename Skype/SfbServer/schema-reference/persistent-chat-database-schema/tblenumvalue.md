---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est un tableau codé en dur qui contient les valeurs de visibilité et le comportement des attributs qui sont utilisés dans la table des nœuds.
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue est un tableau codé en dur qui contient les valeurs de visibilité et le comportement des attributs qui sont utilisés dans la table des nœuds.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, non null  <br/> |ID de la valeur.  <br/> |
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut.  <br/> |
|attributeValue  <br/> |nvarchar (256), non null  <br/> |Nom de la valeur.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|valueID  <br/> |Clé primaire.  <br/> |
|attributeID  <br/> |Clé étrangère avec la recherche dans la table de tblEnumAttribute.attributeID.  <br/> |
   
**Valeurs de la table**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privé  <br/> |
|3  <br/> |1  <br/> |champ d’application  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |ouvrir  <br/> |
   
## <a name="see-also"></a>Voir aussi

#### 

[tblNode](tblnode.md)

