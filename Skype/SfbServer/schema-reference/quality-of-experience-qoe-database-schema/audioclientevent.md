---
title: Table AudioClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Chaque enregistrement contient un événement client pour un point de terminaison lors d’un appel audio. En règle générale, un seul appel a deux enregistrements, celui de l’appelant et celui de l’appelant.
ms.openlocfilehash: dd910c9abf5cbd8d95a7448f72b49641148a2c64
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="audioclientevent-table"></a>Table AudioClientEvent
 
Chaque enregistrement contient un événement client pour un point de terminaison lors d’un appel audio. En règle générale, un seul appel a deux enregistrements, celui de l’appelant et celui de l’appelant.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : les données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**NetworkSendQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement NetworkSendQuality pour l’état 'Bad'.  <br/> Qualité du réseau en termes de perte de paquet ou instabilité est grave et l’impact sur la qualité audio en cours d’envoi.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement ReceiveSendQuality pour l’état 'Bad'.  <br/> Qualité du réseau en termes de perte de paquet ou instabilité est grave et l’impact sur la qualité audio en cours de réception.  <br/> |
|**NetworkDelayEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement de délai pour l’état 'Bad'. Latence du réseau est grave et impact sur l’expérience en empêchant de communication interactive  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement LowBandwidth pour l’état 'Bad'. La bande passante disponible est insuffisante pour une expérience vocale acceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement du processeur insuffisante pour état 'Bad'. Il existe des cycles processeur insuffisantes pour le traitement avec les modalités en cours et les applications en cours d’utilisation. Cela entraîne des distorsions avec le canal audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceHalfDuplexAEC pour l’état 'Bad'. Afin d’éviter l’écho, le système a entrer en mode half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceRenderNotFunctioning pour l’état 'Bad'. Le périphérique de rendu en cours d’utilisation pour la session ne fonctionne pas correctement. Cela peut provoquer des problèmes audio à sens unique.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceCaptureNotFunctioning pour l’état 'Bad'. Le périphérique de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut provoquer des problèmes audio à sens unique.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceGlitches pour l’état 'Bad'. Il existe des problèmes graves dans le rendu des données audio qui est à l’origine de distorsions. Ces problèmes peuvent provenir de problèmes de pilotes de procédures différés (DPC) les appels storm (pilotes) et une utilisation élevée de l’UC.  <br/> |
|**DeviceLowSNREventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceLowSNR pour l’état 'Bad'. La qualité de capture est très faible, soit très bruyant ou utilisateur parle trop éloigné du microphone. Cela entraîne des distorsions.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceLowSpeechLevel pour l’état 'Bad'. Niveau de reconnaissance vocale de l’utilisateur est trop faible et que le système ne peut pas augmenter il davantage. Cela peut provoquer des distorsions ou perçu comme audio à sens unique.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceClipping pour l’état 'Bad'.  <br/> Lorsque les éléments vocale d’extrémité proche du microphone,-extrémité entend la distorsion en raison du découpage. Il est important éviter l’écrêtage du microphone de proximité de fin.  <br/> |
|**DeviceEchoEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceEchoEvent pour l’état 'Bad'. Périphérique ou le programme d’installation est à l’origine écho au-delà de la capacité du système à compenser.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Pourcentage de la session de que déclenchement de l’événement DeviceNearEndToEchoRatio pour l’état 'Bad'. Reconnaissance vocale de l’utilisateur est trop faible par rapport à l’écho en cours de capture, qui a une incidence sur l’expérience de l’utilisateur car il limite combien il est facile d’interruption d’un utilisateur. Réduire le volume des haut-parleurs, placez le micro plus près du participant.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Nombre de fois au cours de la session de que déclenchement de l’événement DeviceMultipleEndpoints pour l’état 'Bad'. Plusieurs points de terminaison audio dans la même session détecté et le système a compensation en réduisant le volume de rendu.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Nombre de fois au cours de la session de que déclenchement de l’événement DeviceHowlingEvent pour l’état 'Bad'. Boucle de rétroaction sonore détectée (due à plusieurs points de terminaison audio chemin de partage).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |Decimal(5,2)  <br/> ||Pourcentage de la session a été déclenché l’événement DeviceRenderZeroVolume d’être dans le « incorrect ' état. Le périphérique de rendu a été défini à aucun volume.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |Decimal(5,2)  <br/> ||Pourcentage de la session a été déclenché l’événement DeviceRenderMute d’être dans le « incorrect ' état. Le périphérique de rendu a été désactivé.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

