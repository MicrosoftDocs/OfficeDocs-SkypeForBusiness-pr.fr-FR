---
title: Table UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation d’un utilisateur individuel du système. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213038"
---
# <a name="userstatistics-table"></a>Table UserStatistics
 
La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation d’un utilisateur individuel du système. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Nom d’utilisateur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**LastLogInTime** <br/> |DateHeure  <br/> ||Heure de la dernière connecté de l’utilisateur.  <br/> |
|**LastConfOrganizedTime** <br/> |DateHeure  <br/> ||Heure de la dernière l’utilisateur organisé une conférence.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Heure de la dernière l’utilisateur a rencontré un échec d’appel.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Heure de la dernière l’utilisateur a rencontré un échec d’appel en tant qu’organisateur de la conférence.  <br/> |
   

