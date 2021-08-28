---
title: Table UserStatistics
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation du système par un utilisateur individuel. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c05277c5999866ea7ba63befeef9e1198436642c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609181"
---
# <a name="userstatistics-table"></a>Table UserStatistics
 
La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation du système par un utilisateur individuel. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**LastLogInTime** <br/> |DateHeure  <br/> ||Heure de la dernière connexion de l’utilisateur.  <br/> |
|**LastConfOrganizedTime** <br/> |DateHeure  <br/> ||Heure de la dernière organisation d’une conférence par l’utilisateur.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Heure du dernier échec d’appel de l’utilisateur.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.  <br/> |
   

