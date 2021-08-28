---
title: tblEnumAttribute
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
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs Visibility et Behavior utilisés dans la table Node.
ms.openlocfilehash: 7f55d99a028a7af7979394321bb543db11bb1933
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628546"
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
|1   <br/> |Visibilité.  <br/> |
|2   <br/> |Comportement.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
