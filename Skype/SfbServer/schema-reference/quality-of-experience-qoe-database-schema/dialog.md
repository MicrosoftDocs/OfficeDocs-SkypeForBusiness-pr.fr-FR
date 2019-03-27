---
title: Table Dialog
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876626"
---
# <a name="dialog-table"></a>Table Dialog
 
La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Temps lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé. Utilisé conjointement avec SessionSeq pour identifier de manière unique une session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID du dialogue qui est globalement unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Somme de contrôle de l’ID de la boîte de dialogue.  <br/> |
   

