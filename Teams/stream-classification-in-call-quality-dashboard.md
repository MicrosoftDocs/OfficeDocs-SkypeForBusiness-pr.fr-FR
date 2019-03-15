---
title: Classification des flux dans le tableau de bord de qualité des appels
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Découvrez comment la qualité des flux est classée dans le tableau de bord de qualité des appels pour Microsoft Teams et Skype Entreprise Online.
ms.openlocfilehash: b3b63ff8ac89ed0ad1d88893913fa89af769e078
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641033"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classification des flux dans le tableau de bord de qualité des appels

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Définitions du classificateur

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Classificateur audio

Un flux audio est marqué comme médiocre si une ou plusieurs des anomalies suivantes sont relevées :

|**Mesure**|**Condition**|**Explication**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|> 500|Durée moyenne de l'aller-retour de propagation sur le réseau calculée selon les spécifications du document RFC3550 en millisecondes.|
|Packet Loss Rate|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|> 30|Gigue moyenne pour le flux, en millisecondes.|
|Ratio Concealed Samples Avg|> 0,07|Taux moyen d’un nombre de trames audio avec échantillons masqués générés par la perte de paquets correcteur et le nombre total d’images audio.|

### <a name="video-classifier"></a>Classificateur vidéo

Un flux vidéo est marqué comme bon ou médiocre selon la valeur de la première métrique disponible dans l'ordre suivant :

|**N° d’étape**|**Mesure**|**Condition**|**Classification si la condition est vraie**|**Classification si la condition est fausse**|**Classification si la métrique n'est pas disponible**|**Explication**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Passez à l’étape 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taux de pertes de paquets après avoir appliqué FEC regroupées sur tous les flux vidéo et les codecs.|

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS est marqué comme bon ou médiocre selon la valeur de la première métrique disponible dans l'ordre suivant :

|**N° d’étape**|**Mesure**|**Condition**|**Classification si la condition est vraie**|**Classification si la condition est fausse**|**Classification si la métrique n'est pas disponible**|**Explication**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Passez à l’étape 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taux de pertes de paquets après avoir appliqué FEC regroupées sur tous les flux vidéo et les codecs.|

### <a name="application-sharing-classifier"></a>Classificateur de partage d'applications

Un flux de partage d’applications est marqué comme médiocre si une ou plusieurs des anomalies suivantes sont rencontrées :


| **Mesure**                                     | **Condition** | **Explication**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Latence moyenne en millisecondes du traitement des vignettes sur la pile RDP du serveur de téléconférence.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Délai moyen des relative à sens unique entre les points de terminaison en secondes pour le flux de partage d’application.                                                                                                                       |

## <a name="unclassified-streams"></a>Flux non classifiés

Dans le TBQA, un flux est marqué comme non classifié lorsque la connectivité ICE échoue ou lorsque toutes les métriques requises pour calculer la classification de flux ne sont pas rapportées.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> La dimension « Utilisation des paquets » et la mesure « Utilisation moyenne des paquets » peuvent être utilisées pour déterminer l’activité des paquets d’un flux.


## <a name="related-topics"></a>Rubriques connexes
[Activation et à l’aide du tableau de bord de la qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)
