---
title: Table UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table qui contient une liste des différents agents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294585"
---
# <a name="useragent-table"></a>Table UserAgent
 
La table UserAgent est une table qui contient une liste des différents agents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet agent utilisateur.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Différent  <br/> |Chaîne de l’agent utilisateur.  <br/> |
|**UAType** <br/> |type  <br/> | <br/> |1 est un serveur de médiation.  <br/> 2 est un serveur de conférence A/V.  <br/> 4 est Skype entreprise.  <br/> 8 est le téléphone IP.  <br/> 16 est la console Live Meeting.  <br/> 32 est l’outil de validation du déploiement (DVT).  <br/> 64 est Skype entreprise Server sur les ordinateurs Macintosh.  <br/> 128 est Skype entreprise Server attendant.  <br/> 256 est le service d’annonce de conférence.  <br/> 512 est le standard automatique de conférence.  <br/> 1024 est une application de Response Group.  <br/> 2048 est hors du contrôle vocal.  <br/> |
   

