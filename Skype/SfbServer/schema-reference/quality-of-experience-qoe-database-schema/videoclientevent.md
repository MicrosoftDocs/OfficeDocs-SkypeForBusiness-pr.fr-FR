---
title: Table VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804992"
---
# <a name="videoclientevent-table"></a>Table VideoClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : données du destinataire  <br/> 1 : données de l’appelant  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état « incorrect ». La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état « incorrect ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son reçu.  <br/> |
   

