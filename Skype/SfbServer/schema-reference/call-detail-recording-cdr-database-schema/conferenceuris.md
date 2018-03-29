---
title: Table ConferenceUris dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConfereneUris est un tableau de prise en charge qui stocke une liste de la conférence différents URI qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une conférence URI.
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Table ConferenceUris dans Skype pour Business Server 2015
 
La table ConfereneUris est un tableau de prise en charge qui stocke une liste de la conférence différents URI qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une conférence URI.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> |Principal  <br/> |Horodatage, interne utilisé.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette conférence URI.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||Conférence URI.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> ||Total de contrôle de ConferenceUri. Utilisé pour augmente la vitesse de recherche de la base de données.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type d’URI, telles que conf:chat pour la conférence par messagerie instantanée ou conf:audio-vidéo pour les conférences audio/vidéo. Consultez la table [UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

