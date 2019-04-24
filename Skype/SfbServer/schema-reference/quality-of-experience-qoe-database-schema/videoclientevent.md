---
title: Table VideoClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212038"
---
# <a name="videoclientevent-table"></a>Table VideoClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Pourcentage de la session qu'a été déclenché l’événement LowBandwidth pour l’état « Incorrect ». La bande passante disponible est insuffisante pour une expérience vocale acceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Pourcentage de session de que l’événement ReceiveSendQuality a été déclenché pour l’état « Incorrect ».  <br/> Qualité du réseau en termes de perte de gigue ou de paquets est lourde et a un impact sur la qualité de l’audio reçu.  <br/> |
   

