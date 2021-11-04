---
title: Table User
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: b8a2fc4775fe36f710cb54c937261a806eef2054
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776004"
---
# <a name="user-table"></a>Table User
 
La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primaire  <br/> |Nombre unique identifiant cet utilisateur.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Uniques  <br/> |Chaîne URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 est type URI inconnu.  <br/> 2 est URI d’utilisateur.  <br/> 4 est URI de conférence.  <br/> 8 est URI de téléphone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Étranger  <br/> |Locataire de l’utilisateur, référencé depuis la table de locataires.  <br/> |
|**LastPoorCallTime** <br/> |DateHeure  <br/> ||Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

