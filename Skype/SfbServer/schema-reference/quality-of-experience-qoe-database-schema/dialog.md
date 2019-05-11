---
title: Table Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920088"
---
# <a name="dialog-table"></a>Table Dialog
 
La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Temps lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé. Utilisé conjointement avec SessionSeq pour identifier de manière unique une session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID du dialogue qui est globalement unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Somme de contrôle de l’ID de la boîte de dialogue.  <br/> |
   

