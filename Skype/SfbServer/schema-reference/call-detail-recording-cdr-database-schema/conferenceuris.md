---
title: Table ConferenceUris dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConferenceUris est une table de prise en charge qui stocke une liste des différentes URI de conférence qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement dans le tableau représente une URI de conférence.
ms.openlocfilehash: 7d7f0ea8504faa3e23d981a74e65062fdb6d5836
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744020"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Table ConferenceUris dans Skype Entreprise Server 2015
 
La table ConferenceUris est une table de prise en charge qui stocke une liste des différentes URI de conférence qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement dans le tableau représente une URI de conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> |Primaire  <br/> |Horodatage pour utilisation interne.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cette URI de conférence.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI de la conférence.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> ||Checksum de ConferenceUri. Sert à augmenter la vitesse des recherches dans les bases de données.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Étranger  <br/> |Type d’URI, tel que conf:chat pour une conférence de messagerie instantanée ou conf:audio-video pour une conférence audio/vidéo. Pour plus [d’informations, voir le tableau UriTypes.](uritypes.md) <br/> |
   

