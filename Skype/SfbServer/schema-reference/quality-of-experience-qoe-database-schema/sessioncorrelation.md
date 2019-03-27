---
title: Table SessionCorrelation
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un ID de corrélation qui sert à corréler plusieurs sessions.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884662"
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un ID de corrélation qui sert à corréler plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Somme de contrôle** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet A / V Conferencing Server.  <br/> |
|**ID de corrélation** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Sessions qui sont corrélées auront le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |À usage interne uniquement.  <br/> |
   

