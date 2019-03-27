---
title: Table ContentTypes dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894985"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Table ContentTypes dans Skype pour Business Server 2015
 
La table ContentTypes est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions d’égal à égal et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le type de contenu.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nom du type de contenu.  <br/> |
   

