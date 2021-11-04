---
title: Table dialog
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: bccc053855ae88bc453aeef27d13732166cc6760
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765042"
---
# <a name="dialog-table"></a>Table dialog
 
La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure à laquelle l’agent QoE (Quality of Excellence) reçoit le premier rapport de l’appelant ou de l’appelé. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID du dialogue qui est unique à l’échelle globale.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Somme de contrôle de l’ID du dialogue.  <br/> |
   

