---
title: Classification des flux dans le tableau de bord de qualité des appels
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Découvrez comment la qualité du flux est classée dans le tableau de bord de qualité des appels pour Microsoft Teams et Skype Entreprise Online.
ms.openlocfilehash: f4c4fb72d15ce79c60c2400b068898ad463f1b07
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598338"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classification des flux dans le tableau de bord de qualité des appels

Le tableau de bord de qualité des appels pour Microsoft Teams et Skype Entreprise Online vous permet d’obtenir des informations sur la qualité des appels effectués à l’aide des services Microsoft Teams et Skype Entreprise’appels. Cette rubrique fournit des informations détaillées sur la classification de qualité des flux de médias. Pour en savoir plus sur le tableau de bord de qualité des appels et découvrir comment le configurer, voir Configurer le tableau de [bord de qualité des appels.](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Définitions du classificateur

Flux du même nom sont classés comme _Bons,_ Médiocres ou _Non classés_ selon les valeurs des mesures clés de qualité disponibles. Les mesures et conditions utilisées pour classifier le flux sont présentées dans les tableaux qui suivent. Les dimensions « Poor Due To » du CQD peuvent être utilisées pour comprendre quelle mesure est responsable d’une _classification_ médiocre. Pour plus d’informations sur ces dimensions, voir Dimensions et mesures disponibles dans le [tableau de bord de qualité des appels.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Classificateur audio

Si une ou plusieurs des conditions suivantes sont remplies, un flux audio est marqué comme _Médiocre_:

|Mesure|Scénario|Condition|Explication|
|:-----|:-----|:-----|:-----|
|Round Trip|ALL|> 500|Durée moyenne de propagation sur le réseau d’aller-retour, calculée en millisecondes. Détails disponibles dans [le RFC3550.](https://tools.ietf.org/html/rfc3550)|
|Packet Loss Rate|ALL|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|ALL|> 30|Gigue moyenne pour le flux, en millisecondes.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificateur vidéo dû au gel

Le flux vidéo est  _marqué_ « Bon ou Médiocre » sur la base de la valeur d’un score de classificateur généré pour estimer que l’utilisateur final a accès à une vidéo figée. Ce classificateur n’est disponible que Microsoft Teams produit.

|N° d’étape|Mesure|Scénario|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Note entre 0 et 1 générée sur la base d’une combinaison d’expérience utilisateur, statistiques de durée figée et expérience d’appel globale |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Note entre 0 et 1 générée sur la base d’une combinaison d’expérience utilisateur, statistiques de durée figée et expérience d’appel globale |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificateur vidéo
Un flux vidéo est marqué comme _Bon_ ou _Médiocre_ en fonction de la valeur de la première mesure disponible dans l’ordre suivant :

|N° d’étape|Mesure|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les images récupérées après des pertes de réseau.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets après FEC agrégé sur tous les flux et les codecs vidéo.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS  est  marqué comme bon ou médiocre selon la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape |Mesure |Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les images récupérées après des pertes de réseau.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets après FEC agrégé sur tous les flux et les codecs vidéo.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificateur de partage d'applications

Un flux de partage d’application est marqué comme _Médiocre_ si une ou plusieurs des conditions suivantes sont remplies :

| Mesure     | Condition | Explication |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Pourcentage de vignettes rejetées au lieu d’être envoyées à un homologue distant (par exemple du MCU à une visionneuse). Les vignettes rejetées (ou spoiled) peuvent être provoquées par des restrictions de bande passante entre le client et le serveur. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latence moyenne en millisecondes du traitement des vignettes sur la pile RDP du serveur de téléconférence. |
| AppSharing Relative OneWay Average | > 1,75 | Retard à sens sensé relatif moyen entre les points de terminaison en secondes pour les flux de partage d’application. |
| | | |

## <a name="unclassified-streams"></a>Flux non classifiés

Dans le tableau de performance  général, un flux est marqué comme non classé en cas d’échec de la connectivité ICE (Interactive Connectivity Connectivity) ou lorsque toutes les mesures requises pour calculer la classification des flux ne sont pas signalées.

Pour vérifier les échecs de la connectivité ICE, examinez les dimensions « First Connectivity Ice » et « Second Connectivity Ice » pour une valeur « FAILED ». Si l’une ou l’autre des valeurs indique un échec, le flux est marqué comme _non classé._

Si la connectivité ICE  a réussi pour un flux non classé, le flux est probablement considéré comme _non_ classé, car les métriques de flux clés n’ont pas été signalées. Il existe plusieurs raisons pour lesquelles ces métriques ne peuvent pas être rapportées :

- **Aucun rapport QoE n’a** été reçu. Les mesures utilisées pour la classification sont signalées dans un rapport QoE envoyé à la fin d’un appel. Si ce rapport n’est pas produit (par exemple, parce que certains points de terminaison tiers peuvent ne pas envoyer QoE) ou ne peuvent pas être envoyés (par exemple, en raison d’une panne du réseau), le CQD ne peut pas classifier le flux.

  > [!TIP]
  > La dimension « QoE Record Available » peut être utilisée pour déterminer si un rapport QoE a été reçu pour un flux. Notez que cette dimension aura la valeur « True » si un rapport QoE a été reçu de chaque point de terminaison. Un rapport QoE des deux points de terminaison est requis pour un compte-rendu plus précis des métriques.

- **Appels courts** : les appels courts risquent de ne pas avoir assez d’activité multimédia pour calculer les métriques de flux clés. Sans ces métriques, le TBQA est incapable de classifier le flux.

  > [!TIP]
  > Les dimensions « Durée (Secondes) », « Durée (Minutes) », « Durée 5 secondes ou moins » et « Durée 60 secondes ou plus » peuvent être utilisées pour déterminer la durée d'un flux. La mesure « durée moyenne d'appel » peut également être utilisée pour calculer la durée moyenne d'un ensemble de flux.

- **Faible utilisation des paquets** : comme dans le scénario « appel court », une utilisation suffisante des paquets est nécessaire pour le calcul des métriques de flux clés. Sans ces métriques, le TBQA est incapable de classifier le flux.
  - Un scénario courant de faible utilisation des paquets se produit lorsqu’un participant participe à une réunion pour écouter le présentateur, mais ne parle jamais (le micro est muet pendant la plupart des appels). Ici, l’utilisation des paquets pour le flux audio entrant au client est élevée, tandis que le flux audio sortant du client a peu ou pas d’utilisation des paquets. La durée du flux peut être d’une heure ou plus, mais l’utilisation du paquet sur  le flux entre le client et le serveur est faible depuis que le microphone a été muet et qu’un flux non classé en résulte.

  > [!TIP]
  > La dimension « Utilisation des paquets » et la mesure « Utilisation moyenne des paquets » peuvent être utilisées pour déterminer l’activité des paquets d’un flux.

## <a name="related-topics"></a>Voir aussi
[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données de bâtiment et de client](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)
