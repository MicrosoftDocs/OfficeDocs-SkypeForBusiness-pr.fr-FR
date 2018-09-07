---
title: Classification des flux dans le tableau de bord de qualité des appels
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: fc5028fbf8955b4988b29121474e775478175fd1
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23871021"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classification des flux dans le tableau de bord de qualité des appels

Le tableau de bord de la qualité des appels (CQD) pour Microsoft Teams et Skype pour Business Online vous permet d’obtenir des informations sur la qualité des appels effectués à l’aide de Microsoft Teams et Skype pour les services. Cette rubrique fournit des informations détaillées sur la classification de qualité des flux de médias. Pour en savoir plus sur les CQD et comment l’activer, voir [activation et à l’aide du tableau de bord qualité des appels](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Définitions du classificateur

Les flux dans le TBQA sont classés comme bons, médiocres ou non classifiés en fonction des valeurs des métriques clés de qualité disponibles. Les métriques et conditions utilisées pour classer les flux sont présentées dans les tableaux ci-dessous. Les dimensions « Médiocre en raison de » du TBQA peuvent être utilisées pour comprendre quelle métrique est responsable d'une mauvaise classification. Voir [Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md) pour plus d'informations sur ces dimensions.

### <a name="audio-classifier"></a>Classificateur audio

Un flux audio est marqué comme médiocre si une ou plusieurs des anomalies suivantes sont relevées :

|**Mesure**|**Condition**|**Explication**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Dégradation moyenne de la note moyenne d'opinion réseau pour le flux. Elle représente l'impact des pertes ou des gigues au niveau du réseau sur l'audio reçu.|
|Round Trip|> 500|Durée moyenne de l'aller-retour de propagation sur le réseau calculée selon les spécifications du document RFC3550 en millisecondes.|
|Packet Loss Rate|> 0,1|Taux moyen de perte de paquets pour le flux.|
|Jitter|> 30|Gigue moyenne pour le flux, en millisecondes.|
|Ratio Concealed Samples Avg|> 0,07|Taux moyen d’un nombre de trames audio avec échantillons masqués générés par la perte de paquets correcteur et le nombre total d’images audio.|

### <a name="video-classifier"></a>Classificateur vidéo

Un flux vidéo est marqué comme bon ou médiocre selon la valeur de la première métrique disponible dans l'ordre suivant :

|**N° d’étape**|**Mesure**|**Condition**|**Classification si la condition est vraie**|**Classification si la condition est fausse**|**Classification si la métrique n'est pas disponible**|**Explication**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. Cela inclut les images récupérées après des pertes de réseau.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taux de pertes de paquets après avoir appliqué FEC regroupées sur tous les flux vidéo et les codecs.|

### <a name="vbss-classifier"></a>Classificateur VBSS

Un flux VBSS est marqué comme bon ou médiocre selon la valeur de la première métrique disponible dans l'ordre suivant :

|**N° d’étape**|**Mesure**|**Condition**|**Classification si la condition est vraie**|**Classification si la condition est fausse**|**Classification si la métrique n'est pas disponible**|**Explication**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |Poor|Good|Passez à l’étape 2|Pourcentage moyen de perte de trames vidéo tel qu'affiché pour l'utilisateur. Cela inclut les images récupérées après des pertes de réseau.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Passez à l’étape 3|Moyenne de fréquence d'images par seconde reçues pour un flux vidéo calculée pour toute la durée de la session.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taux de pertes de paquets après avoir appliqué FEC regroupées sur tous les flux vidéo et les codecs.|

### <a name="application-sharing-classifier"></a>Classificateur de partage d'applications

Un flux de partage d’applications est marqué comme médiocre si une ou plusieurs des anomalies suivantes sont rencontrées :

**Mesure**|**Condition**|**Explication**|
|:-----|:-----|:-----|
|Spoiled Tile Percent Total|> 36|Pourcentage de mosaïques sont supprimés au lieu de l’envoi d’un homologue distant (par exemple, de MCU une visionneuse). Mosaïques supprimés (ou altérées) peuvent être dû à des restrictions de bande passante entre client et serveur.|
|AppSharing RDP Tile Processing Latency Average|400 >|Latence moyenne en millisecondes du traitement des vignettes sur la pile RDP du serveur de téléconférence.|
|AppSharing Relative OneWay Average|> 1,75|Délai moyen des relative à sens unique entre les points de terminaison en secondes pour le flux de partage d’application.|

## <a name="unclassified-streams"></a>Flux non classifiés

Dans le TBQA, un flux est marqué comme non classifié lorsque la connectivité ICE échoue ou lorsque toutes les métriques requises pour calculer la classification de flux ne sont pas rapportées.

Pour vérifier les échecs de la connectivité ICE, examinez les dimensions « First Connectivity Ice » et « Second Connectivity Ice » pour une valeur « FAILED ». Si l'une ou l'autre valeur indique un échec, le flux sera marqué comme non classifié.

Si la connectivité ICE a réussi pour un flux non classifié, le flux est probablement considéré comme non classifié car les métriques clés du flux n'ont pas été rapportées. Il existe plusieurs raisons pour lesquelles ces métriques ne peuvent pas être rapportées :

- **Les rapports QoE n'ont pas été reçus** - Les métriques utilisées pour la classification sont rapportées dans un rapport de QoE envoyé à la fin d'un appel. Si ce rapport n'est pas produit (par exemple, parce que certains terminaux tiers ne peuvent pas envoyer de QoE) ou n'a pas pu être envoyé (par exemple, en raison d'une panne de réseau), le TBQA est incapable de classifier le flux.

> [!TIP]
> La dimension « QoE Record Available » peut être utilisée pour déterminer si un rapport QoE a été reçu pour un flux. Notez que cette dimension aura la valeur « True » si un rapport QoE a été reçu de chaque point de terminaison. Un rapport QoE des deux points de terminaison est requis pour un compte-rendu plus précis des métriques.

- **Appels courts** - Les appels courts peuvent ne pas avoir assez d'activité média pour calculer les métriques clés du flux. Sans ces métriques, le TBQA est incapable de classifier le flux.

> [!TIP]
> Les dimensions « Durée (Secondes) », « Durée (Minutes) », « Durée 5 secondes ou moins » et « Durée 60 secondes ou plus » peuvent être utilisées pour déterminer la durée d'un flux. La mesure « durée moyenne d'appel » peut également être utilisée pour calculer la durée moyenne d'un ensemble de flux.

- **Faible utilisation des paquets** - Comme le scénario « appel court », une utilisation suffisante des paquets est nécessaire pour le calcul des métriques clés du flux. Sans ces métriques, le TBQA est incapable de classifier le flux.
    - Un scénario commun d'utilisation faible de paquets se produit lorsqu'un utilisateur se joint à une réunion pour écouter le présentateur mais ne parle jamais (en coupant probable le micro pendant la plus grande partie de l'appel). Dans un tel scénario, un flux audio aura une forte utilisation de paquets (entrant vers le client) tandis que l'autre sens aura peu ou pas d'utilisation de paquets (sortant du client). Dans ce scénario, la durée du flux peut être d'une heure ou plus, mais l'utilisation des paquets dans le flux du client vers le serveur sera extrêmement faible en raison du fait que le micro étant coupé, ce qui entraîne un flux non classifié.

> [!TIP]
> La dimension « Utilisation des paquets » et la mesure « Utilisation moyenne des paquets » peuvent être utilisées pour déterminer l’activité des paquets d’un flux.


## <a name="related-topics"></a>Rubriques connexes
[Activation et à l’aide du tableau de bord de la qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)
