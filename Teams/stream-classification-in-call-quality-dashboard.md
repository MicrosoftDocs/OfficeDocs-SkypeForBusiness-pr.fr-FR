---
title: Classification de flux dans le tableau de bord qualité des appels (CQD)
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
description: Découvrez comment la qualité du flux est classifiée dans le tableau de bord de qualité des appels (CQD) pour Microsoft Teams et Skype Entreprise Online.
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059255"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classification de flux dans le tableau de bord de qualité des appels (CQD)

Le tableau de bord de qualité des appels (CQD) pour Microsoft Teams et Skype Entreprise Online vous permet d’obtenir des insights sur la qualité des appels effectués à l’aide des services Microsoft Teams et Skype Entreprise. Cette rubrique fournit des informations détaillées sur la classification de qualité des flux de médias. Pour en savoir plus sur le CQD et comment le configurer, consultez [Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Définitions du classificateur

Flux dans CQD sont classés comme _bons_, _pauvres_ ou _non classés_ en fonction des valeurs des métriques de qualité clés disponibles. Les métriques et conditions utilisées pour classer le flux sont affichées dans les tableaux qui suivent. Les dimensions « Poor Due To » de CQD peuvent être utilisées pour comprendre quelle métrique est responsable d’une classification _médiocre_ . Pour plus d’informations sur ces dimensions, consultez [Dimensions et mesures disponibles dans le tableau de bord qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificateur audio

Si une ou plusieurs des conditions suivantes sont remplies et que l’utilisation des paquets est > 500 paquets, un flux audio est marqué comme _médiocre_ :

|Mesure|Scénario|Condition|Explication|
|:-----|:-----|:-----|:-----|
|Round Trip|TOUS|> 500|Durée moyenne de propagation du réseau aller-retour, calculée en millisecondes. Détails disponibles dans [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|TOUS|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|TOUS|> 30|Gigue moyenne pour le flux, en millisecondes.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Classifier due to Freeze

Le flux vidéo est marqué  _Good_ or _Poor_ en fonction de la valeur d’un score de classifieur généré pour estimer que l’utilisateur final a rencontré Frozen Video. Ce classifieur est disponible pour Microsoft Teams produit uniquement.

|N° d’étape|Mesure|Scénario|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Est-ce que la paire de serveurs est client : serveur|>0,246|_Poor_|_Good_|_Unclassified_|Score compris entre 0 et 1 généré en fonction d’une combinaison d’expérience utilisateur, de figer les statistiques de durée et d’expérience globale des appels |
|2|Video Poor Due to Freeze Classifier |Est-ce que la paire de serveurs est client : client|>0,524|_Poor_|_Good_|_Unclassified_|Score compris entre 0 et 1 généré en fonction d’une combinaison d’expérience utilisateur, de figer les statistiques de durée et d’expérience globale des appels |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificateur vidéo
Un flux vidéo est marqué comme _bon_ ou _mauvais_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape|Mesure|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les images récupérées à la suite de pertes réseau.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets une fois fec appliqué agrégé sur tous les flux vidéo et codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS est marqué comme _bon_ ou _mauvais_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape |Mesure |Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|Codec n’est PAS H264S</br>Et</br>StreamDirection est entrant</br></br>Si FrameLoss > 50 %|_Poor_|_Good_|_Unclassified_|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les images récupérées à la suite de pertes réseau. FrameLoss est utilisé uniquement pour classifier les flux entrants non H264S.|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session. S’applique à tous les flux sortants et à StreamDirection pour H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Classificateur de partage d'applications

Un flux de partage d’applications est marqué comme _médiocre_ si une ou plusieurs des conditions suivantes sont remplies :

| Mesure     | Condition | Explication |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Pourcentage de vignettes qui sont ignorées au lieu d’être envoyées à un homologue distant (par exemple, du MCU à une visionneuse). Les vignettes ignorées (ou gâtées) peuvent être provoquées par des restrictions de bande passante entre le client et le serveur. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latence moyenne en millisecondes du traitement des vignettes sur la pile RDP du serveur de téléconférence. |
| AppSharing Relative OneWay Average | > 1,75 | Délai unidirectionnel relatif moyen entre les points de terminaison en secondes pour les flux de partage d’applications. |
| | | |

## <a name="unclassified-streams"></a>Flux non classifiés

Dans CQD, un flux est marqué _Comme non classifié_ en cas d’échec de la connectivité ICE (Interactive Connectivity Establishment) ou lorsque toutes les métriques nécessaires au calcul de la classification de flux ne sont pas signalées.

Pour vérifier les échecs de la connectivité ICE, examinez les dimensions « First Connectivity Ice » et « Second Connectivity Ice » pour une valeur « FAILED ». Si l’une ou l’autre valeur indique un échec, le flux est marqué comme _non classé_.

Si la connectivité ICE a réussi pour un flux _non classifié_ , le flux est probablement considéré comme _non classifié_ , car les métriques de flux clés n’ont pas été signalées. Il existe plusieurs raisons pour lesquelles ces métriques ne peuvent pas être rapportées :

- **Les rapports QoE n’ont pas été reçus** : les métriques utilisées pour la classification sont signalées dans un rapport QoE envoyé à la fin d’un appel. Si ce rapport n’est pas produit (par exemple, parce que certains points de terminaison tiers ne peuvent pas envoyer QoE) ou n’a pas pu être envoyé (par exemple, en raison d’une panne réseau), CQD ne peut pas classer le flux.

  > [!TIP]
  > La dimension « QoE Record Available » peut être utilisée pour déterminer si un rapport QoE a été reçu pour un flux. Notez que cette dimension aura la valeur « True » si un rapport QoE a été reçu de chaque point de terminaison. Un rapport QoE des deux points de terminaison est requis pour un compte-rendu plus précis des métriques.

- **Appels courts** : les appels courts peuvent ne pas avoir suffisamment d’activité multimédia pour calculer les métriques de flux clés. Sans ces métriques, le TBQA est incapable de classifier le flux.

  > [!TIP]
  > Les dimensions « Durée (Secondes) », « Durée (Minutes) », « Durée 5 secondes ou moins » et « Durée 60 secondes ou plus » peuvent être utilisées pour déterminer la durée d'un flux. La mesure « durée moyenne d'appel » peut également être utilisée pour calculer la durée moyenne d'un ensemble de flux.

- **Faible utilisation des paquets** : comme dans le scénario d’appel court, une utilisation suffisante des paquets est requise pour le calcul des métriques de flux clés. Sans ces métriques, le TBQA est incapable de classifier le flux.
  - Un scénario courant d’utilisation faible des paquets se produit lorsqu’un participant rejoint une réunion pour écouter le présentateur, mais ne parle jamais (le microphone est désactivé pour la plupart de l’appel). Ici, le flux audio entrant vers le client a une utilisation élevée des paquets, tandis que le flux audio sortant du client n’a que peu ou pas d’utilisation des paquets. La durée du flux peut être d’une heure ou plus, mais l’utilisation des paquets sur le flux entre le client et le serveur est faible, car le microphone a été désactivé et un flux _non classifié_ s’affiche.

  > [!TIP]
  > La dimension « Utilisation des paquets » et la mesure « Utilisation moyenne des paquets » peuvent être utilisées pour déterminer l’activité des paquets d’un flux.

## <a name="related-topics"></a>Voir aussi
[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)
