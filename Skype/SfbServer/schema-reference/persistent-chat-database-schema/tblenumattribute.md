---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814612"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute est une table codée en dur qui contient les attributs de visibilité et de comportement qui sont utilisés dans la table de nœud.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, pas null  <br/> |ID de l’attribut.  <br/> |
|attributeName  <br/> |nvarchar (256), pas null  <br/> |Nom de l’attribut.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|attributeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs de table**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Notoriété.  <br/> |
|deuxième  <br/> |Fonctionnement.  <br/> |
   
## <a name="see-also"></a>Voir aussi

[tblNode](tblnode.md)
