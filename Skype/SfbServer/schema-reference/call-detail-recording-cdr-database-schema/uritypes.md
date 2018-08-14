---
title: Table UriTypes
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
ms.openlocfilehash: d1a796367ae068dcd814b13b1b0ec6ce9ae453f1
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649604"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.

Lorsque la CDR DB est créée, deux enregistrements pour représenter PhoneUri et UserUri sont créés et enregistrements créés après que qui sont attribuées dynamiquement UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 et 255. |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont affectées par défaut : <br/>  1 - Uri du téléphone <br/>  0 - Uri utilisateur <br/> <br/>  Autres types possibles sont les suivantes : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   MRAS<br/>
