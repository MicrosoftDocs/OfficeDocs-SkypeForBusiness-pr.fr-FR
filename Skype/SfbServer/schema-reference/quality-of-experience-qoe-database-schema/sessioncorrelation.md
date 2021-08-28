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
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: a0ec0a2e1435aab02ba1733530271b2ad648869e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634118"
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente un CorrelationID qui est utilisé pour corréler plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Somme de contrôle** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce serveur de conférence A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Les sessions corrélées auront le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |À usage interne uniquement.  <br/> |
   

