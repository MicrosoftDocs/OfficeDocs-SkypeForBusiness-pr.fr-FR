---
title: Table AudioClientEvent
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.
ms.openlocfilehash: e51146211567af3abfe68fdc415814d433e84884
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843647"
---
# <a name="audioclientevent-table"></a>Table AudioClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primaire  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**NetworkSendQualityEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement NetworkSendQuality a été déclenché pour l’état « Bad ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est grave et a un impact sur la qualité de l’audio envoyé.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement ReceiveSendQuality a été déclenché pour l’état « Bad ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est grave et a un impact sur la qualité de l’audio reçu.  <br/> |
|**NetworkDelayEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement Delay a été déclenché pour l’état « Bad ». La latence du réseau est grave et a un impact sur l’expérience en empêchant la communication interactive  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement LowBandwidth a été déclenché pour l’état « Bad ». La bande passante disponible est insuffisante pour une expérience vocale acceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement de processeur insuffisant a été déclenché pour l’état « Bad ». Il existe des cycles de processeur insuffisants pour le traitement avec les modalités et les applications actuelles en cours d’utilisation. Cela provoque des distorsions avec le canal audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceHalfDuplexAEC a été déclenché pour l’état « Bad ». Pour éviter l’écho, le système a entré le semi-duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceRenderNotFunctioning a été déclenché pour l’état « Bad ». Le périphérique de rendu actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens seul.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceCaptureNotFunctioning a été déclenché pour l’état « Bad ». L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens seul.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceGlitches a été déclenché pour l’état « Bad ». Il existe de graves problèmes de rendu de l’audio qui provoquent des distorsions. Ces problèmes peuvent être causés par des problèmes de pilote, des appels de procédure différée (DPC) et une utilisation élevée du processeur.  <br/> |
|**DeviceLowsNREventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceLowSNR a été déclenché pour l’état « Bad ». La qualité de capture est très médiocre, soit très bruyante, soit l’utilisateur parle trop loin du microphone. Cela provoquera des distorsions.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceLowSpeechLevel a été déclenché pour l’état « Bad ». Le niveau de voix de l’utilisateur est trop faible et le système ne peut plus l’augmenter. Cela peut entraîner des distorsions ou être perçue comme un son à sens seul.  <br/> |
|**DeviceClippingEventRatio** <br/> |Décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceClipping a été déclenché pour l’état « Bad ».  <br/> Lorsque la reconnaissance vocale proche extrait le microphone, l’extrémité de l’ordinateur entend une distorsion due à un découpage. Il est important d’éviter les coupures de microphones proches.  <br/> |
|**DeviceEchoEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceEchoEvent a été déclenché pour l’état « Bad ». L’appareil ou le programme d’installation provoque un écho au-delà de la capacité du système à compenser.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage de session où l’événement DeviceNearEndToEchoRatio a été déclenché pour l’état « Bad ». La voix de l’utilisateur est trop faible par rapport à l’écho capturé qui a un impact sur l’expérience utilisateur, car il limite la facilité d’interruption d’un utilisateur. Réduisez le volume du haut-parleur, rapprochez le microphone du talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Nombre de fois pendant la session que l’événement DeviceMultipleEndpoints a été déclenché pour l’état « Bad ». Plusieurs points de terminaison audio détectés dans la même session et le système a compenser en réduisant le volume de rendu.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Nombre de fois pendant la session que l’événement DeviceHowlingEvent a été déclenché pour l’état « Bad ». Boucle de retour audio détectée (causée par plusieurs points de terminaison partageant le chemin d’accès audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |décimal(5,2)  <br/> ||Pourcentage de session où l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état « Bad ». Le périphérique de rendu a été réglé sur zéro volume.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |décimal(5,2)  <br/> ||Pourcentage de session où l’événement DeviceRenderMute a été déclenché pour être dans l’état « Bad ». Le périphérique de rendu a été muté.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

