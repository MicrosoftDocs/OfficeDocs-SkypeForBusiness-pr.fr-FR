---
title: Implémenter QoS et contrôler l’analyse des appels dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: Utiliser les paramètres de qualité de Service (QoS) puis Analytique d’appel et appel du tableau de bord qualité dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 505409ac51552a99fabc4eb41801a1f19a737877
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742949"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Mettre en œuvre QoS et surveiller la qualité des appels dans les équipes Microsoft

## <a name="get-started"></a>Mise en route

Que vos utilisateurs commencent à l’aide des équipes pour émettre des appels et organiser des réunions, ils peuvent découvrir les haut-parleurs onduleur rupture ou a et s’en déconnecter un appel ou une réunion. Partagé vidéo peut se figer ou pixellate, ou échouer totalement. Il s’agit en raison de paquets IP qui représentent la voix et le trafic vidéo rencontre une surcharge réseau et d’arriver en dehors de la séquence ou pas du tout. Il existe des méthodes pour éviter ce problème et identifier les autres problèmes lors de leur surface, principalement qualité de Service (QoS).

[**Qualité de Service (QoS)**](monitor-call-quality-qos.md) consiste à identifier les paquets sont sensibles à des retards et congestion, puis fournissez les paquets avec préférentiel afin qu’ils rencontrent beaucoup moins congestion. À ce stade, nous allons dire qu’il est très similaire l’envoi d’une lettre par le biais de la messagerie : Si vous envoyez taux livre il arrive bientôt et qui est suffisant, si vous l’envoyez de première classe il arrive beaucoup plus rapides, et si vous l’envoyez priorité de messagerie , il arrive dans les deux jours. Bien sûr, réseaux fonctionnent plus rapide que la messagerie, mais il s’exécute toujours true que vitesse est essentielle pour certaines applications et n’est pas crucial pour d’autres personnes. Cet objet est fondamentalement détaillée et difficile à comprendre en premier lieu, mais il est très important de l’utilisateur expérience ; il doit donc investir du temps et énergie dès le départ.

Idéalement, vous implémentez QoS sur votre réseau interne lors de la configuration des équipes, mais si vous êtes petite suffisamment, il peut être facultatif. Cela permet de retard critiques voice et le trafic vidéo à obtenir hiérarchisée avant le reste du trafic. Vous effectuez cette définition des priorités sur tous les périphériques clients, ainsi que sur les commutateurs et les routeurs dans votre réseau.

[**Analytique d’appel et tableau de bord qualité des appels**](difference-between-call-analytics-and-call-quality-dashboard.md) sont utilisés pour rechercher et résoudre les problèmes qui affiche lors de l’opération en cours.  

Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité liés aux appels spécifiques et des réunions pour chaque utilisateur de Microsoft Teams Skype pour un compte professionnel. Si vous êtes un administrateur Office 365, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de qualité et connexion appel a rencontré un appel spécifique. Cela peut vous aider à identifier et d’éliminer les problèmes.

Tableau de bord de qualité d’appel (CQD) est conçu pour aider les administrateurs et les ingénieurs réseau optimiser un **réseau**, pas à analyser et résoudre les problèmes d’un seul appel. CQD déplace le focus utilisateurs spécifiques afin de consulter les informations agrégées pour toute une organisation. Cela peut également vous aider à identifier et d’éliminer les problèmes.

## <a name="related-topics"></a>Rubriques connexes

[Vidéo : Vue d’ensemble de la qualité des appels](https://aka.ms/teams-quality)

[Configurer Analytique d’appel](set-up-call-analytics.md)

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et à l’aide du tableau de bord qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)