---
title: Table AudioClientEvent
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
ms.openlocfilehash: 713804875f9cd2a1fc37a2255697c4ffda47a3c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811082"
---
# <a name="audioclientevent-table"></a>Table AudioClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : données du destinataire  <br/> 1 : données de l’appelant  <br/> |
|**NetworkSendQualityEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement NetworkSendQuality pour l’état « incorrect ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son envoyé.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état « incorrect ».  <br/> La qualité du réseau en termes de gigue ou de perte de paquets est sérieuse et a un impact sur la qualité du son reçu.  <br/> |
|**NetworkDelayEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session le déclenchement de l’événement de temporisation a été déclenché pour l’état « incorrect ». La latence du réseau est sérieuse et a un impact sur l’interface en empêchant les communications interactives  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état « incorrect ». La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de l’événement UC insuffisant déclenché pour l’état « incorrect ». Il n’y a pas assez de cycles d’UC pour le traitement avec les modalités et applications en cours d’utilisation. Cela entraîne une distorsion du canal audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceHalfDuplexAEC pour l’état « incorrect ». Afin d’éviter l’écho, le système a entré Half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceRenderNotFunctioning pour l’état « incorrect ». L’appareil de rendu actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceCaptureNotFunctioning pour l’état « incorrect ». L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceGlitches pour l’état « incorrect ». Il y a des problèmes importants dans le rendu du son qui engendre des distorsions. Ces problèmes peuvent être causés par des problèmes de pilotes, des appels de procédures différées (DPC) Storm (pilotes) et une utilisation élevée de l’UC.  <br/> |
|**DeviceLowSNREventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceLowSNR pour l’état « incorrect ». La qualité de la capture est très médiocre, qu’elle soit très bruyante ou que l’utilisateur parle trop loin du microphone. Cela entraînera une distorsion.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceLowSpeechLevel pour l’état « incorrect ». Le niveau de voix de l’utilisateur est trop faible et le système ne peut plus l’augmenter. Cela peut entraîner des distorsions ou une perception perçue comme un son à sens unique.  <br/> |
|**DeviceClippingEventRatio** <br/> |Décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceClipping pour l’état « incorrect ».  <br/> Lorsque le son du microphone est proche de l’extrémité de la parole, la distorsion est audible en raison de l’écrêtage. Il est important d’éviter une capture du microphone proche de la fin.  <br/> |
|**DeviceEchoEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceEchoEvent pour l’état « incorrect ». L’appareil ou la configuration entraîne un écho au-delà de la capacité du système à compenser.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |décimale (5 ; 2)  <br/> | <br/> |Pourcentage de session de déclenchement de l’événement DeviceNearEndToEchoRatio pour l’état « incorrect ». La parole de l’utilisateur est trop faible par rapport à l’écho capturé qui a un impact sur l’interface utilisateur, car il limite le niveau d’interruption d’un utilisateur. Réduire le volume des haut-parleurs, rapprochez le micro du contact.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Nombre de fois que l’événement DeviceMultipleEndpoints a été déclenché pour l’état « incorrect ». Plusieurs points de terminaison audio au sein de la même session détectés et le système a compensé en réduisant le volume de rendu.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Nombre de fois que l’événement DeviceHowlingEvent a été déclenché pour l’état « incorrect ». Boucle de commentaires audio détectée (provoquée par plusieurs points de terminaison partageant le chemin audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |décimale (5 ; 2)  <br/> ||Pourcentage de session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état « incorrect ». L’appareil de rendu a été défini sur le volume zéro.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |décimale (5 ; 2)  <br/> ||Pourcentage de session l’événement DeviceRenderMute a été déclenché pour être dans l’état « incorrect ». L’appareil de rendu a été coupé.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

