---
title: Table ConferenceUris dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Le tableau ConfereneUris est une table de prise en charge qui stocke une liste de la conférence différents URI qui ont participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une URI de conférence.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213213"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Table ConferenceUris dans Skype pour Business Server 2015
 
Le tableau ConfereneUris est une table de prise en charge qui stocke une liste de la conférence différents URI qui ont participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une URI de conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> |Principal  <br/> |Horodatage pour utilisation interne.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette URI de conférence.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI de conférence.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> ||Somme de contrôle de ConferenceUri. Utilisé pour augmenter la vitesse des recherches de base de données.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type d’URI, tel que conf:chat pour la conférence par messagerie instantanée ou conf:audio-vidéo pour la conférence audio/vidéo. Voir la table [UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

