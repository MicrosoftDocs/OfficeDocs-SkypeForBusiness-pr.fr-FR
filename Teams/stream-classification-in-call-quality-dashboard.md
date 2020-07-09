---
title: Classification des flux dans le tableau de bord de qualité des appels (bord)
ms.author: lolajacobsen
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Découvrez comment la qualité des flux est classée dans le tableau de bord de qualité des appels (bord) de Microsoft teams et de Skype entreprise online.
ms.openlocfilehash: 28c3857f1bf30903e9a59d45e8149f8ecbfc57be
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085890"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classification des flux dans le tableau de bord de qualité des appels (bord)

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to set it up, see [Set up Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Définitions du classificateur

Streams in CQD are classified as _Good_, _Poor_, or _Unclassified_ based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables that follow. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a _Poor_ classification. For more information on these dimensions, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificateur audio

Si une ou plusieurs des conditions suivantes sont remplies, un flux audio est marqué comme _médiocre_:

|Mesure|Condition|Explication|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. How much network loss and jitter have impacted the quality of received audio.|
|Round Trip|> 500|Temps moyen de propagation du réseau en boucle arrondi, calculé en millisecondes. Détails disponibles dans [le document rfc3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|> 30|Gigue moyenne pour le flux, en millisecondes.|
|Ratio Concealed Samples Avg|> 0,07|Rapport moyen du nombre de trames audio et d’échantillons masqués générés par la correction de perte de paquets sur le nombre total de trames audio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificateur vidéo en raison de gel

Le flux vidéo est marqué comme _bon_ ou _médiocre_ en fonction de la valeur du score de classifieur généré pour évaluer la vidéo de l’utilisateur final. Ce classificateur est disponible uniquement pour le produit Microsoft Teams.

|N° d’étape|Mesure|Scénario|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Vidéo médiocre à cause du gel du classificateur |Est-ce que la paire de serveurs est client : serveur|>0,246|_Poor_|_Good_|_Unclassified_|Score compris entre 0 et 1, généré en fonction d’une combinaison d’utilisation de l’utilisateur, de statistiques de durée de gel et de l’utilisation globale des appels |
|2|Vidéo médiocre à cause du gel du classificateur |Est-ce que la paire de serveurs est client :|>0,524|_Poor_|_Good_|_Unclassified_|Score compris entre 0 et 1, généré en fonction d’une combinaison d’utilisation de l’utilisateur, de statistiques de durée de gel et de l’utilisation globale des appels |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificateur vidéo
Un flux vidéo est marqué comme _bon_ ou _médiocre_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape|Mesure|Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les trames récupérées à partir d’une perte du réseau.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Taux de perte de paquets après FEC appliqué au regroupement de tous les flux vidéo et codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS est marqué comme _bon_ ou _médiocre_ en fonction de la valeur de la première métrique disponible dans l’ordre suivant :

|N° d’étape |Mesure |Condition |Classification si la condition est vraie |Classification si la condition est fausse |Classification si la métrique n'est pas disponible |Explication |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. La moyenne inclut les trames récupérées à partir d’une perte du réseau.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
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
[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)
