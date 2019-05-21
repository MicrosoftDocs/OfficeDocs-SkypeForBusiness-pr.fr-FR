---
title: Table ConferenceUris dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente un URI de conférence.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296391"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Table ConferenceUris dans Skype entreprise Server 2015
 
La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente un URI de conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure d’utilisation internes.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet URI de conférence.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI de conférence.  <br/> |
|**1018** <br/> |int  <br/> ||Checksum de ConferenceUri. Permet d’augmenter la vitesse de recherche de la base de données.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externes  <br/> |Type d’URI (par exemple, conf: chat pour une conférence par messagerie instantanée, ou conf: audio-vidéo pour les conférences audio/vidéo). Pour plus d’informations, voir la table [UriTypes table](uritypes.md) . <br/> |
   

