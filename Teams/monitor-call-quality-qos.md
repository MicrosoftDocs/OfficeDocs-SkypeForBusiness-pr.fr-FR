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
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a40b5d14268323f1231377e96b75a3120145245
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408250"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Mettre en œuvre QoS et surveiller la qualité des appels dans les équipes Microsoft

## <a name="get-started"></a>Mise en route

Que vos utilisateurs commencent à l’aide des équipes pour émettre des appels et organiser des réunions, ils peuvent rencontrer vocale d’un appelant divisions ou hachage et s’en déconnecter un appel ou de la réunion. Shared mai vidéo figés ou pixellisation, ou échouer totalement. Il s’agit en raison de paquets IP qui représentent la voix et le trafic vidéo rencontre une surcharge réseau et d’arriver en dehors de la séquence ou pas du tout. Il existe des méthodes permettant d’identifier ces problèmes lors de la surface et d’empêcher leur retour, principalement qualité de Service (QoS).

**Qualité de Service (QoS)** consiste à autoriser en temps réel le trafic réseau (par exemple, les flux audio ou vidéo) qui est sensible aux délais réseau « réduction à la ligne « devant le trafic est moins sensible (comme le téléchargement d’une nouvelle application, où une seconde supplémentaire à télécharger pas très important). QoS identifie et marque tous les paquets de flux de données en temps réel à l’aide des objets de stratégie de groupe Windows et une fonctionnalité de routage appelée Port-based Access Control Lists, qui vous aide à votre réseau pour donner à la voix, vidéo et partage d’écran diffuse leurs propres parties dédiés de bande passante du réseau.

 À ce stade, nous allons dire qu’il est très similaire l’envoi d’une lettre par le biais de la messagerie : Si vous envoyez taux livre il arrive bientôt et qui est suffisant, si vous l’envoyez de première classe il arrive beaucoup plus rapides, et si vous l’envoyez priorité de messagerie , il arrive dans les deux jours. Bien sûr, réseaux fonctionnent plus rapide que la messagerie, mais il s’exécute toujours true que vitesse est essentielle pour certaines applications et n’est pas crucial pour d’autres personnes. Cet objet est fondamentalement détaillée et difficile à comprendre en premier lieu, mais il est très important de l’utilisateur expérience ; il doit donc investir du temps et énergie dès le départ. Lisez [Implémenter la qualité de Service (QoS) dans les équipes Microsoft](QoS-in-Teams.md) pour une description plus détaillée.

Idéalement, vous implémentez QoS sur votre réseau interne lors de la configuration des équipes, mais si vous êtes petite suffisamment, il peut être facultatif. Cela permet de retard critiques voice et le trafic vidéo à obtenir hiérarchisée avant le reste du trafic. Vous effectuez cette définition des priorités sur tous les [périphériques clients](QoS-in-Teams-clients.md), dans le [Centre d’administration de Microsoft équipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), ainsi que sur les commutateurs et les routeurs dans votre réseau.

[**Analytique d’appel et tableau de bord qualité des appels**](difference-between-call-analytics-and-call-quality-dashboard.md) sont utilisés pour rechercher et résoudre les problèmes qui affiche lors de l’opération en cours.  

**Analytique d’appel** affiche des informations détaillées sur les périphériques, les réseaux et connectivité liées aux ***réunions et appels spécifiques*** pour chaque utilisateur de Microsoft Teams Skype pour un compte professionnel. Si vous êtes un administrateur Office 365, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de qualité et connexion appel a rencontré un appel spécifique. Cela peut vous aider à identifier et d’éliminer les problèmes.

**Tableau de bord de la qualité des appels (CQD)** est conçu pour aider les administrateurs et les ingénieurs réseau optimiser leur ***réseau***, pas à analyser et résoudre les problèmes d’un seul appel. CQD déplace le focus utilisateurs spécifiques afin de consulter les informations agrégées pour toute une organisation. Cela peut également vous aider à identifier et d’éliminer les problèmes.

## <a name="related-topics"></a>Rubriques connexes

[Implémenter la qualité de Service (QoS) dans les équipes Microsoft](QoS-in-Teams.md)

[Vidéo : Vue d’ensemble de la qualité des appels](https://aka.ms/teams-quality)

[Configurer Analyse des appels](set-up-call-analytics.md)

[Utiliser l’Analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et utilisation du tableau de bord d’appel de qualité d’appel](turning-on-and-using-call-quality-dashboard.md)

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)