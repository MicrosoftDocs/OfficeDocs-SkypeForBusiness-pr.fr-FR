---
title: Table UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899644"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.

Lorsque la CDR DB est créée, deux enregistrements pour représenter PhoneUri et UserUri sont créés et enregistrements créés après que qui sont attribuées dynamiquement UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 et 255. |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont affectées par défaut : <br/>  1 - Uri du téléphone <br/>  0 - Uri utilisateur <br/> <br/>  Autres types possibles sont les suivantes : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   MRAS<br/>
