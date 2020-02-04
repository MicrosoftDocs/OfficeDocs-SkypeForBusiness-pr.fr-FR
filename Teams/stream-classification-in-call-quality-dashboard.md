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
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Découvrez comment la qualité des flux est classée dans le tableau de bord de qualité des appels pour Microsoft Teams et Skype Entreprise Online.
ms.openlocfilehash: 49063ab0e957a0afee256fb0e5500d0f2b2a8ae6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680531"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classification des flux dans le tableau de bord de qualité des appels

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Définitions du classificateur

Dans bord, les flux sont classés comme _bon_, _médiocre_ou non _classés_ en fonction des valeurs des mesures de qualité clé disponibles. Les mesures et conditions utilisées pour classifier le flux sont indiquées dans les tableaux suivants. Les dimensions de type « médiocre à la suite de » d’bord peuvent être utilisées pour comprendre quelle mesure est responsable d’une _mauvaise_ classification. Pour plus d’informations sur ces dimensions, voir [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificateur audio

Si une ou plusieurs des conditions suivantes sont remplies, un flux audio est marqué comme _médiocre_:

|Mesure|Condition|Explication|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Dégradation moyenne d’avis du réseau pour le flux. Le niveau de perte et de scintillation du réseau a affecté la qualité audio de la réception.|
|Round Trip|> 500|Temps moyen de propagation du réseau en boucle arrondi, calculé en millisecondes. Détails disponibles dans [le document rfc3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|> 30|Gigue moyenne pour le flux, en millisecondes.|
|Ratio Concealed Samples Avg|> 0,07|Rapport moyen du nombre de trames audio et d’échantillons masqués générés par la correction de perte de paquets sur le nombre total de trames audio.|
||||

### <a name="video-classifier"></a>Classificateur vidéo

Un flux vidéo est marqué comme _bon_ ou _médiocre_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape|Mesure|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les trames récupérées à partir d’une perte du réseau.|
|deuxième|Video Frame Rate Avg|< 7|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets après FEC appliqué au regroupement de tous les flux vidéo et codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS est marqué comme _bon_ ou _médiocre_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape |Mesure |Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les trames récupérées à partir d’une perte du réseau.|
|deuxième|Video Frame Rate Avg|< 2|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets après FEC appliqué au regroupement de tous les flux vidéo et codecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificateur de partage d'applications

Un flux de partage d’application est marqué comme _médiocre_ si une ou plusieurs des conditions suivantes sont remplies :

| Mesure     | Condition | Explication |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Pourcentage de vignettes ignorées au lieu d’être envoyées à un homologue distant (par exemple, de la MCU vers une visionneuse). Les vignettes annulées (ou abîmées) peuvent être dues à des restrictions de bande passante entre le client et le serveur. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latence moyenne en millisecondes du traitement des vignettes sur la pile RDP du serveur de téléconférence. |
| AppSharing Relative OneWay Average | > 1,75 | Moyenne de retard relatif à sens unique entre les points de terminaison en secondes pour les flux de partage d’application. |
| | | |

## <a name="unclassified-streams"></a>Flux non classifiés

Dans bord, un flux est marqué comme n’étant pas _classé_ lorsque la connectivité de l’établissement de la connexion interactives échoue ou lorsque toutes les mesures requises pour calculer la classification du flux ne sont pas communiquées.

Pour vérifier les échecs de la connectivité ICE, examinez les dimensions « First Connectivity Ice » et « Second Connectivity Ice » pour une valeur « FAILED ». Si l’une des valeurs indique un échec, le flux est marqué comme non _classé_.

Si la connectivité ICE a réussi pour un flux non _classé_ , le flux est probablement considéré comme non _classé_ car les métriques de flux de clés n’ont pas été communiquées. Il existe plusieurs raisons pour lesquelles ces métriques ne peuvent pas être rapportées :

- Les **rapports QoE n’ont pas été reçus** : les métriques utilisées pour la classification sont communiquées dans un rapport QoE envoyé à la fin d’un appel. Si ce rapport n’est pas fourni (par exemple, parce que certains points de terminaison tiers ne peuvent pas envoyer le nombre d’éléments de type QoE) ou ne peuvent pas être envoyés (par exemple, en raison d’une défaillance du réseau), bord ne peut pas classifier le flux.

> [!TIP]
> La dimension « QoE Record Available » peut être utilisée pour déterminer si un rapport QoE a été reçu pour un flux. Notez que cette dimension aura la valeur « True » si un rapport QoE a été reçu de chaque point de terminaison. Un rapport QoE des deux points de terminaison est requis pour un compte-rendu plus précis des métriques.

- **Appels courts** : il est possible que les appels courts ne disposent pas de suffisamment d’activité multimédia pour calculer les métriques de flux clé. Sans ces métriques, le TBQA est incapable de classifier le flux.

> [!TIP]
> Les dimensions « Durée (Secondes) », « Durée (Minutes) », « Durée 5 secondes ou moins » et « Durée 60 secondes ou plus » peuvent être utilisées pour déterminer la durée d'un flux. La mesure « durée moyenne d'appel » peut également être utilisée pour calculer la durée moyenne d'un ensemble de flux.

- **Faible utilisation des paquets** (par exemple, le scénario « appel court »), une utilisation suffisante des paquets est nécessaire pour le calcul des métriques de flux clé. Sans ces métriques, le TBQA est incapable de classifier le flux.
  - Un scénario courant d’utilisation faible des paquets se produit lorsqu’un participant rejoint une réunion pour écouter le présentateur, mais jamais (le micro est coupé pour la plupart des appels). Ici, le flux audio entrant sur le client a une forte utilisation du paquet alors que le flux audio sortant du client a une faible utilisation du paquet. La durée du flux peut être d’une heure ou plus, mais l’utilisation du paquet sur le flux du client vers le serveur est faible, car le microphone a été coupé et un résultat de flux non _classé_ .

> [!TIP]
> La dimension « Utilisation des paquets » et la mesure « Utilisation moyenne des paquets » peuvent être utilisées pour déterminer l’activité des paquets d’un flux.

## <a name="related-topics"></a>Rubriques connexes

[Activation et utilisation du tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)
