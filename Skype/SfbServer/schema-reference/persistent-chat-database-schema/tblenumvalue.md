---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295425"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, pas null  <br/> |ID de la valeur.  <br/> |
|attributeID  <br/> |smallint, pas null  <br/> |ID de l’attribut.  <br/> |
|attributeValue  <br/> |nvarchar (256), pas null  <br/> |Nom de la valeur.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|valueID  <br/> |Clé primaire.  <br/> |
|attributeID  <br/> |Clé étrangère avec recherche dans la table tblEnumAttribute. attributeID.  <br/> |
   
**Valeurs de table**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privé  <br/> |
|3  <br/> |1  <br/> |hors  <br/> |
|4  <br/> |2  <br/> |normalement  <br/> |
|5  <br/> |2  <br/> |Conférence  <br/> |
|6  <br/> |1  <br/> |ouvre  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
