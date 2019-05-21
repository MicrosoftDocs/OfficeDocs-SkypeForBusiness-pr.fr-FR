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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294956"
---
# <a name="dialog-table"></a>Table Dialog
 
Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Temps pendant lequel l’agent de qualité d’excellence reçoit le premier rapport de l’appelant ou du destinataire. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Numéro séquentiel pour différencier les sessions lorsqu’elles ont la même ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||ID de boîte de dialogue globalement unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Checksum de l’ID de boîte de dialogue.  <br/> |
   

