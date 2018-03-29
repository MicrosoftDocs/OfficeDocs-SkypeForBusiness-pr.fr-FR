---
title: Table User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table est une table de prise en charge qui stocke une liste des différents utilisateurs qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>Table User
 
La table est une table de prise en charge qui stocke une liste des différents utilisateurs qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant l’utilisateur.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Unique  <br/> |Chaîne d’URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 est inconnu type d’URI.  <br/> 2 est utilisateur URI.  <br/> 4 est la conférence URI.  <br/> 8 est un URI de téléphone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Étrangère  <br/> |Clients de l’utilisateur, référencé à partir de la table des clients.  <br/> |
|**LastPoorCallTime** <br/> |DateHeure  <br/> ||Dernier horodatage lorsque l’utilisateur a un appel audio médiocre.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

