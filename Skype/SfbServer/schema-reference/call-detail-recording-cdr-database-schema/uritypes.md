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
description: La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés Skype Entreprise Server 2015.
ms.openlocfilehash: 1e98bc879e7ddb6e2ca92d4f226284e604d22d312f9e2db8c0ff80cad89c33e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295361"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés Skype Entreprise Server 2015.

Lorsque la base de données d’enregistrement des appels est créée, deux enregistrements représentant PhoneUri et UserUri sont créés, et les enregistrements créés ensuite sont affectés dynamiquement à UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles - 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont pré-affectées : <br/>  1 - Téléphone URI <br/>  0 - Uri de l’utilisateur <br/> <br/>  Les autres types possibles sont les suivants : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
