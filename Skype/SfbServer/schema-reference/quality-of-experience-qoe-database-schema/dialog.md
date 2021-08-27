---
title: Table de dialogue
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).
ms.openlocfilehash: 0310845ada3b86346ccc6b410a5c7539b16689f3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603723"
---
# <a name="dialog-table"></a>Table de dialogue
 
La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure à laquelle l’agent QoE (Quality of Excellence) reçoit le premier rapport de l’appelant ou de l’appelé. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID du dialogue qui est unique à l’échelle globale.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Somme de contrôle de l’ID du dialogue.  <br/> |
   

