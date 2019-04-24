---
title: Table UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212058"
---
# <a name="useragent-table"></a>Table UserAgent
 
La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet agent utilisateur.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Chaîne d’Agent utilisateur.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 est le serveur de médiation.  <br/> 2 a / V Conferencing Server.  <br/> 4 est Skype pour les entreprises.  <br/> 8 est un téléphone IP.  <br/> 16 correspond à la Console Live Meeting.  <br/> 32 est un outil de Validation de déploiement (configurations).  <br/> 64 est Skype pour Business Server sur les ordinateurs Macintosh.  <br/> 128 est Skype pour Business Server Attendant.  <br/> 256 est un service d’annonce de conférence.  <br/> 512 correspond au standard automatique de conférence.  <br/> 1024 correspond à l’application Response Group.  <br/> 2048 correspond au contrôle vocal extérieur.  <br/> |
   

