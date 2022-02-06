---
title: Table VideoClientEvent
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.'
---

# <a name="videoclientevent-table"></a>Table VideoClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel vidéo. En règle générale, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primaire  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Pourcentage de session où l’événement LowBandwidth a été déclenché pour l’état « Bad ». La bande passante disponible est insuffisante pour une expérience vocale acceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Pourcentage de session où l’événement ReceiveSendQuality a été déclenché pour l’état « Bad ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est grave et a une incidence sur la qualité de l’audio reçu.  <br/> |
   

