---
title: Table SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314420"
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Somme de contrôle** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce serveur de conférence A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Les sessions corrélées auront le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |À usage interne uniquement.  <br/> |
   

