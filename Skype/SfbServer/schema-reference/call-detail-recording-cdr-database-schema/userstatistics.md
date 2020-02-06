---
title: Table UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation individuelle du système par un utilisateur. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814792"
---
# <a name="userstatistics-table"></a>Table UserStatistics
 
La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation individuelle du système par un utilisateur. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**LastLogInTime** <br/> |DateHeure  <br/> ||Dernière connexion de l’utilisateur.  <br/> |
|**LastConfOrganizedTime** <br/> |DateHeure  <br/> ||Dernière organisation d’une conférence.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur a rencontré un échec de l’appel.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur a rencontré un appel d’organisateur en tant qu’organisateur de la Conférence.  <br/> |
   

