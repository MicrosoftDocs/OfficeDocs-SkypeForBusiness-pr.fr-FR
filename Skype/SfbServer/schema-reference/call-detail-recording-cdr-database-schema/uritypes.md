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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype Entreprise Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831684"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype Entreprise Server 2015.

Lors de la création de la base de données d’enregistrement des appels, deux enregistrements représentant PhoneUri et UserUri sont créés, et les enregistrements créés par la suite sont affectés dynamiquement à UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont pré-affectées : <br/>  1 - Uri de téléphone <br/>  0 - Uri de l’utilisateur <br/> <br/>  Les autres types possibles sont les suivants : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
