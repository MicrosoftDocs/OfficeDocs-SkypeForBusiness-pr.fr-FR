---
title: Table Dialog
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809532"
---
# <a name="dialog-table"></a>Table Dialog
 
Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Temps pendant lequel l’agent de qualité d’excellence reçoit le premier rapport de l’appelant ou du destinataire. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Numéro séquentiel pour différencier les sessions lorsqu’elles ont la même ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||ID de boîte de dialogue globalement unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Checksum de l’ID de boîte de dialogue.  <br/> |
   

