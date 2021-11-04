---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: ee7a2d79458640eff2695ce253792e154d36dee4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767442"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés Skype Entreprise Server 2015.

Lors de la création de la base de données d’enregistrement des appels, deux enregistrements représentant PhoneUri et UserUri sont créés, et les enregistrements créés par la suite sont affectés dynamiquement à UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont pré-affectées : <br/>  1 - Téléphone URI <br/>  0 - Uri de l’utilisateur <br/> <br/>  Les autres types possibles sont les suivants : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
