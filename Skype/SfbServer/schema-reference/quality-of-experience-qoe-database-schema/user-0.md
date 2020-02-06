---
title: Table User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805092"
---
# <a name="user-table"></a>Table User
 
La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**SPAMMEUR** <br/> |nvarchar (450)  <br/> |Différent  <br/> |Chaîne d’URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 est un type d’URI inconnu.  <br/> 2 est l’URI de l’utilisateur.  <br/> 4 est un URI de conférence.  <br/> 8 est un URI de téléphone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Externes  <br/> |Client de l’utilisateur, référencé dans la table locataire.  <br/> |
|**LastPoorCallTime** <br/> |DateHeure  <br/> ||Horodatage le plus récent lorsque l’utilisateur avait un appel audio médiocre.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Pour un usage interne uniquement.  <br/> |
   

