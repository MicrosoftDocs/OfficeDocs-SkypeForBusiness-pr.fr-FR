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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295747"
---
# <a name="uritypes-table"></a>Table UriTypes
 
La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.

Lors de la création de la base de données de CDR, deux enregistrements permettant de représenter PhoneUri et UserUri sont créés, et les enregistrements créés après leur attribution dynamique UriTypeId. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique attribué à un type d’URI.  <br/> Valeurs possibles: 0 à 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descriptions des différents types d’URI. Les valeurs suivantes sont préaffectées: <br/>  1-URI de téléphone <br/>  0-URI de l’utilisateur <br/> <br/>  Voici d’autres types possibles: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: chat<br/>    conf:focus<br/>   mras<br/>
