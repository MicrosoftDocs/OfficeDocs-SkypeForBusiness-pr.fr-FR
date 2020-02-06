---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814842"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.

Lors de la création de la base de données de CDR, deux enregistrements permettant de représenter PhoneUri et UserUri sont créés, et les enregistrements créés après leur attribution dynamique UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles : 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont préaffectées : <br/>  1-URI de téléphone <br/>  0-URI de l’utilisateur <br/> <br/>  Voici d’autres types possibles : <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf : chat<br/>    conf:focus<br/>   mras<br/>
