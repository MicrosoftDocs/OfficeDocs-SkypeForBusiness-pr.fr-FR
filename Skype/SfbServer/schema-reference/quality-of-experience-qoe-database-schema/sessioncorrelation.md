---
title: Table SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805742"
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est une table de prise en charge. Chaque enregistrement représente une corrélation qui est utilisée pour mettre en corrélation plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**1018** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce serveur de conférence A/V.  <br/> |
|**Corrélation** <br/> |nvarchar(256)  <br/> |Différent  <br/> |Les sessions corrélées auront le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |Pour un usage interne uniquement.  <br/> |
   

