---
title: Table SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La table SessionCorrelation est un tableau de prise en charge. Chaque enregistrement représente un ID de corrélation qui est utilisé pour corréler plusieurs sessions.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>Table SessionCorrelation
 
La table SessionCorrelation est un tableau de prise en charge. Chaque enregistrement représente un ID de corrélation qui est utilisé pour corréler plusieurs sessions. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Somme de contrôle** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet A / V Conferencing Server.  <br/> |
|**ID de corrélation** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Les sessions qui sont corrélées ont le même ID de corrélation.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> | <br/> |À usage interne uniquement.  <br/> |
   

