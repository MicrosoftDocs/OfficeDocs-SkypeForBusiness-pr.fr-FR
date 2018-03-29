---
title: Table Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue Session Initiation Protocol (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Table Dialog
 
La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue Session Initiation Protocol (SIP).
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé. Utilisé en association avec SessionSeq pour identifier de manière unique une session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Numéro de séquence pour différencier les sessions lorsqu’ils ont le même ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID de boîte de dialogue qui est globalement unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Total de contrôle de l’ID de boîte de dialogue.  <br/> |
   

