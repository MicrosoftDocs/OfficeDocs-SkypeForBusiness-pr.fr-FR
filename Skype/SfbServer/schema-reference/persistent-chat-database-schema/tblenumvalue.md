---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929867"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue est une table codée en dur qui contient les valeurs visibilité et le comportement des attributs qui sont utilisés dans la table Node.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, non null  <br/> |ID de la valeur.  <br/> |
|attributeID  <br/> |smallint, non null  <br/> |ID de l’attribut.  <br/> |
|attributeValue  <br/> |nvarchar (256), non null  <br/> |Nom de la valeur.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|valueID  <br/> |Clé primaire.  <br/> |
|attributeID  <br/> |Clé étrangère avec recherche dans la table tblEnumAttribute.attributeID.  <br/> |
   
**Valeurs de table**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privé  <br/> |
|3  <br/> |1  <br/> |étendue  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |Ouvrez  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
