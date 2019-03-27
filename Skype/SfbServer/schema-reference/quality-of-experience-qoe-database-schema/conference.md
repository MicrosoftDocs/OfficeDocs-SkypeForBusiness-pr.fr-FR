---
title: Table Conference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table de conférence est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874038"
---
# <a name="conference-table"></a>Table Conference
 
La table de conférence est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet enregistrement de conférence.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |Conférence URI s’il s’agit une conférence, ou DialogID s’il est une session d’égal à égal.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> |index  <br/> |Somme de contrôle de l’URI de conférence. Il est utilisé en interne.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

