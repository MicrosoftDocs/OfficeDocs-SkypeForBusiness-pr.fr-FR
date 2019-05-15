---
title: Table UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation d’un utilisateur individuel du système. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929979"
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
   

