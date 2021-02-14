---
title: Table User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800074"
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
   

