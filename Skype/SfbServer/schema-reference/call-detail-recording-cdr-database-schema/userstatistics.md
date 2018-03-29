---
title: Table de UserStatistics
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est un tableau de prise en charge. Chaque enregistrement dans la table stocke les informations relatives à l’utilisation d’un utilisateur individuel du système. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>Table de UserStatistics
 
La table UserStatistics est un tableau de prise en charge. Chaque enregistrement dans la table stocke les informations relatives à l’utilisation d’un utilisateur individuel du système. Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID utilisateur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant l’utilisateur.  <br/> |
|**LastLogInTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur connecté.  <br/> |
|**LastConfOrganizedTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur organisé une conférence.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur a rencontré un échec d’appel.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |DateHeure  <br/> ||Dernière fois que l’utilisateur a rencontré une erreur appel en tant qu’organisateur de la conférence.  <br/> |
   

