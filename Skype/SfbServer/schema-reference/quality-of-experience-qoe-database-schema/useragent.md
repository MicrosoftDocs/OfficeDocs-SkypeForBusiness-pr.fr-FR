---
title: Table UserAgent
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: 128d1c397376da7667b244e73efa2f1b77b56d37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834812"
---
# <a name="useragent-table"></a>Table UserAgent
 
La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique qui identifie cet agent utilisateur.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Chaîne de l’agent utilisateur.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 est serveur de médiation.  <br/> 2 est un serveur de conférence A/V.  <br/> 4 est Skype Entreprise.  <br/> 8 est une adresse IP Téléphone.  <br/> 16 est Live Meeting Console.  <br/> 32 est l’outil de validation de déploiement (DVT).  <br/> 64 est Skype Entreprise Server sur les ordinateurs Macintosh.  <br/> 128 est Skype Entreprise Server Attendant.  <br/> 256 est Annonce de conférence service.  <br/> 512 est l’Standard automatique.  <br/> 1024 est l’application Response Group.  <br/> 2048 est hors contrôle vocal.  <br/> |
   

