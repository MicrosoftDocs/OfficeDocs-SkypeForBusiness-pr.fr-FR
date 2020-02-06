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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs de visibilité et de comportement des attributs qui sont utilisés dans la table de nœud.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814602"
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
|deuxième  <br/> |1  <br/> |privé  <br/> |
|3  <br/> |1  <br/> |hors  <br/> |
|4  <br/> |deuxième  <br/> |normalement  <br/> |
|5  <br/> |deuxième  <br/> |Conférence  <br/> |
|6  <br/> |1  <br/> |ouvre  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
