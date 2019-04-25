---
title: Table AudioClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212319"
---
# <a name="audioclientevent-table"></a>Table AudioClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un seul appel a deux enregistrements, l’autre pour l’appelant et l’autre pour l’appelé.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**NetworkSendQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de session de que l’événement NetworkSendQuality a été déclenché pour l’état « Incorrect ».  <br/> Qualité du réseau en termes de perte de gigue ou de paquets est lourde et impact sur la qualité de l’audio envoyé.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de session de que l’événement ReceiveSendQuality a été déclenché pour l’état « Incorrect ».  <br/> Qualité du réseau en termes de perte de gigue ou de paquets est lourde et impact sur la qualité de l’audio reçu.  <br/> |
|**NetworkDelayEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement de délai d’attente pour l’état « Incorrect ». Latence du réseau est lourde et impact sur l’expérience en empêchant de communication interactive  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement LowBandwidth pour l’état « Incorrect ». La bande passante disponible est insuffisante pour une expérience vocale acceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de session de que l’événement du processeur insuffisante a été déclenché pour l’état « Incorrect ». Il existe des cycles de processeur suffisantes pour le traitement avec les applications en cours d’utilisation et les modalités en cours. Alors distorsions avec le canal audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceHalfDuplexAEC pour l’état « Incorrect ». Afin d’éviter l’écho, le système a Entrez semi-duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceRenderNotFunctioning pour l’état « Incorrect ». Le périphérique de rendu en cours d’utilisation pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes d’audio à sens unique.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceCaptureNotFunctioning pour l’état « Incorrect ». Le périphérique de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes d’audio à sens unique.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceGlitches pour l’état « Incorrect ». Il existe des graves problèmes dans le rendu des données audio qui est à l’origine de distorsions. Ces problèmes peuvent être dû à des problèmes de pilote, vague d’appels (DPC) procédure différés (pilotes) et d’utilisation intensive du processeur.  <br/> |
|**DeviceLowSNREventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceLowSNR pour l’état « Incorrect ». La qualité de capture est médiocre, soit très bruit ou de l’utilisateur est en train de parler trop éloignée du microphone. Cela entraîne des distorsions.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceLowSpeechLevel pour l’état « Incorrect ». Niveau de voix de l’utilisateur est trop faible et le système ne peut pas augmenter il davantage. Cela peut provoquer des distorsions ou perçue comme l’audio à sens unique.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceClipping pour l’état « Incorrect ».  <br/> Lorsque l’extrémité proche vocale clips du microphone,-extrémité entend déformation en raison de découpage. Il est important éviter l’écrêtage du microphone près de fin.  <br/> |
|**DeviceEchoEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceEchoEvent pour l’état « Incorrect ». Périphérique ou le programme d’installation est à l’origine de l’écho au-delà de la capacité du système pour compenser.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session qu'a été déclenché l’événement DeviceNearEndToEchoRatio pour l’état « Incorrect ». Vocale de l’utilisateur est trop faible par rapport à l’écho capturé en cours qui a un impact sur l’expérience des utilisateurs, car il limite combien il est facile d’interrompre un utilisateur. Réduire le volume des haut-parleurs, placez le plus proche du microphone pour le participant.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Nombre de fois au cours de la session qu'a été déclenché l’événement DeviceMultipleEndpoints pour l’état « Incorrect ». Plusieurs points de terminaison audio dans la même session détecté et le système a compensation en réduisant le volume de rendu.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Nombre de fois au cours de la session qu'a été déclenché l’événement DeviceHowlingEvent pour l’état « Incorrect ». Boucle de réaction acoustique détectée (due à plusieurs points de terminaison partage chemin audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |Decimal(5,2)  <br/> ||Pourcentage de session a été déclenché l’événement DeviceRenderZeroVolume pour en cours dans le « incorrecte ' état. Le périphérique de rendu sans volume a été défini.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |Decimal(5,2)  <br/> ||Pourcentage de session a été déclenché l’événement DeviceRenderMute pour en cours dans le « incorrecte ' état. Le périphérique de rendu a été désactivé.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

