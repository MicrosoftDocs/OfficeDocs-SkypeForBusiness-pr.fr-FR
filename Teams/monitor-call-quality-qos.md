---
title: Implémenter QoS et contrôler l’analyse des appels dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: Utiliser les paramètres de qualité de service (QoS), puis appeler le tableau de bord d’analyse et de qualité des appels dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70e862adf2aad795a9ef1ab34eaa2de21240a388
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239252"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Mettre en œuvre QoS et surveiller la qualité d’appel dans Microsoft teams

## <a name="get-started"></a>Commencer

À mesure que les utilisateurs commenceront à utiliser teams pour passer des appels et participer à des réunions, il est possible que la voix d’un appelant soit déconcertée ou détourée de l’appel ou de la réunion. La vidéo partagée risque de se figer ou de s’embloquer complètement. Ce problème est dû aux paquets IP qui représentent le trafic audio et vidéo, qui rencontrent une congestion du réseau et qui arrivent en entrée ou pas du tout. Il existe différentes façons d’identifier ces problèmes quand ils sont en surface et empêchent leur retour, c’est-à-dire la qualité de service (QoS).

La **qualité de service (QoS)** est une méthode permettant d’autoriser le trafic réseau en temps réel (par exemple, les flux vocaux ou vidéo) qui est sensible aux retards de réseau pour «couper ligne» devant le trafic moins sensible (comme le téléchargement d’une nouvelle application, par exemple, pour le téléchargement d’une application supplémentaire ce n’est pas une grande affaire. La fonction QoS identifie et marque tous les paquets en flux temps réel à l’aide d’objets de stratégie de groupe Windows et d’une fonctionnalité de routage appelée listes de contrôle d’accès basée sur le port, qui permet de faire en sorte que votre réseau transmette les flux vocaux, vidéo et d’écran à leurs propres parties dédiées de bande passante réseau.

 Pour le moment, nous vous conseillons de dire qu’il s’agit d’envoyer une lettre par courrier électronique: Si vous nous adressez des tarifs très avantageux et si vous envoyez un message prioritaire par le biais de cette offre, c’est encore plus rapide et si vous envoyez un message prioritaire. , il est là dans un délai de deux jours. Bien sûr, les réseaux s’exécutent plus rapidement que le courrier, mais ils s’exécutent quand même la vitesse est essentielle pour certaines applications et n’est donc pas essentielle pour les autres. Ce sujet est par essence détaillée et difficile à comprendre, mais il a une grande différence quant à l’utilisation de l’utilisateur, c’est pourquoi il est utile de consacrer du temps et de l’énergie. Pour plus d’informations, voir implémenter la [qualité de service (QoS) dans Microsoft teams](QoS-in-Teams.md) .

Idéalement, vous pouvez implémenter la qualité de service (QoS) sur votre réseau interne lorsque vous configurez Teams, mais si vous n’êtes pas suffisamment petit, cela peut être facultatif. Ainsi, le trafic audio et vidéo en retard est prioritaire par rapport à d’autres trafics. Pour ce faire, vous devez utiliser cette priorité sur tous les [appareils clients](QoS-in-Teams-clients.md), dans le [Centre d’administration de Microsoft teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), ainsi que sur les commutateurs et les routeurs de votre réseau.

Le [**tableau de bord d’analyse des appels et de qualité des appels**](difference-between-call-analytics-and-call-quality-dashboard.md) permet de rechercher et de résoudre les problèmes qui surviennent au cours de l’opération en cours.  

L' **analyse des appels** affiche des informations détaillées sur les appareils, réseaux et connectivité liés à des ***appels et des réunions spécifiques*** pour chaque utilisateur d’un compte Microsoft teams ou Skype entreprise. Si vous êtes un administrateur 365 Office, vous pouvez utiliser les services d’analyse des appels pour résoudre les problèmes de qualité d’appel et de connexion rencontrés dans un appel spécifique. Cela peut vous aider à identifier et éliminer les problèmes.

Le **tableau de bord de qualité des appels (bord)** est conçu pour permettre aux administrateurs et aux ingénieurs réseau d’optimiser leur ***réseau***, et pas d’analyser et résoudre les problèmes d’un seul appel. BORD déplace le focus entre des utilisateurs spécifiques pour accéder à des informations agrégées dans l’ensemble de l’organisation. Cela peut également vous aider à identifier et éliminer les problèmes.

## <a name="related-topics"></a>Rubriques connexes

[Mise en œuvre de la qualité de service (QoS) dans Microsoft teams](QoS-in-Teams.md)

[Vidéo: vue d’ensemble de la qualité d’appel](https://aka.ms/teams-quality)

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et utilisation du tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)