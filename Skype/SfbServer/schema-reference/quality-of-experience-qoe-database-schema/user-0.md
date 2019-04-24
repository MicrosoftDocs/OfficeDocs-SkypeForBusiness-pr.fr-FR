---
title: Table User
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212080"
---
# <a name="user-table"></a>Table User
 
La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Unique  <br/> |Chaîne d’URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 est type URI inconnu.  <br/> 2 est URI de l’utilisateur.  <br/> 4 est URI de conférence.  <br/> 8 est URI de téléphone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Étrangère  <br/> |Client de l’utilisateur, référencé à partir de la table clients.  <br/> |
|**LastPoorCallTime** <br/> |DateHeure  <br/> ||Dernières date et l’heure où l’utilisateur avait un appel audio médiocre.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

