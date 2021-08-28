---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés Skype Entreprise Server 2015.
ms.openlocfilehash: e6be4abb02fc29fb5becd9da8a1b45c4d8c6271f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583768"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés Skype Entreprise Server 2015.

Lors de la création de la base de données d’enregistrement des appels, deux enregistrements représentant PhoneUri et UserUri sont créés, et les enregistrements créés par la suite sont affectés dynamiquement à UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont pré-affectées : <br/>  1 - Téléphone URI <br/>  0 - Uri de l’utilisateur <br/> <br/>  Les autres types possibles sont les suivants : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
