---
title: Table SessionCorrelation
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: 706bd5c47d1a709712c7178562e535612f61332c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834902"
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Somme de contrôle** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce serveur de conférence A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Les sessions corrélées auront le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |À usage interne uniquement.  <br/> |
   

