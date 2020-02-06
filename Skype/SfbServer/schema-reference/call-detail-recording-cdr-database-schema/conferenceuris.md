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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente un URI de conférence.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815312"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Table ConferenceUris dans Skype entreprise Server 2015
 
La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente un URI de conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure d’utilisation internes.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet URI de conférence.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI de conférence.  <br/> |
|**1018** <br/> |int  <br/> ||Checksum de ConferenceUri. Permet d’augmenter la vitesse de recherche de la base de données.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externes  <br/> |Type d’URI (par exemple, conf : chat pour une conférence par messagerie instantanée, ou conf : audio-vidéo pour les conférences audio/vidéo). Pour plus d’informations, voir la table [UriTypes table](uritypes.md) . <br/> |
   

