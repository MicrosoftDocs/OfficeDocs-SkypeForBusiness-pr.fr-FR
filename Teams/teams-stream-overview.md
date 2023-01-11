---
title: Vue d’ensemble de l’encodeur pour le streaming dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cet article fournit une vue d’ensemble de la configuration RTMP basée sur l’encodeur pour les événements de streaming Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767940"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Événements de streaming en direct dans Microsoft Teams

Vous pouvez créer des événements en direct à l’aide de Microsoft Teams au sein de votre organisation. Vous pouvez planifier, produire et fournir des événements en direct pour différents scénarios, tels que des événements à l’échelle de l’entreprise, des mises à jour de direction, etc. Les événements de diffusion en continu en direct permettent aux producteurs d’organiser et de contrôler le contenu qui est diffusé à un public.

Vous pouvez créer, planifier et exécuter des événements en direct à l’aide d’un flux RTMP ou RTMPS à débit binaire unique à partir d’un encodeur. Nous nous chargerons de tout le transcodage pour la remise à débit adaptatif à vos visionneuses.

Comme n’importe quelle autre vidéo dans Teams, vous pouvez rendre l’événement en direct ouvert à l’ensemble de votre entreprise ou limiter l’accès à des groupes spécifiques. Cela fournit une expérience de création et d’affichage de bout en bout à l’intérieur de Teams.

Après l’événement, la vidéo sera disponible à la demande avec des fonctionnalités intelligentes, notamment :

- Reconnaissance vocale et sous-titres.
- La recherche de transcription et les timecodes vous permettent de trouver rapidement des moments importants dans une vidéo.

## <a name="live-events-in-microsoft-365"></a>Événements en direct dans Microsoft 365

Vous pouvez créer un événement de diffusion en direct dans Teams ou Yammer, où se trouve votre public, votre équipe ou votre communauté. Les participants peuvent regarder l’événement en haute définition (HD) vidéo et soumettre des questions par le biais d’une expérience Q&R modérée. L’intégration transparente dans Microsoft 365 signifie que vous pouvez utiliser Teams pour fournir des événements de qualité studio hautement produits.

## <a name="get-started"></a>Prise en main

Assurez-vous que les utilisateurs auxquels vous souhaitez créer des événements en direct disposent des autorisations requises pour créer un événement en direct. Par défaut, tous les membres de votre organisation peuvent créer un événement en direct, mais un administrateur Teams peut restreindre l’accès. En savoir plus sur l’administration des événements en direct.

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Stratégies d’événements****en direct** réunions  >  > l’onglet **Gérer les stratégies**.
1. Si vous souhaitez :
    1. modifiez la stratégie par défaut existante, choisissez **Global (valeur par défaut à l’échelle de l’organisation).**
    1. créez une stratégie personnalisée, choisissez **+Ajouter**.
    1. modifiez une stratégie personnalisée, sélectionnez-la, puis choisissez **Modifier**.

## <a name="monitor-your-event"></a>Surveiller votre événement

En tant que producteur, vous pouvez utiliser le client Teams pour voir le flux d’audience (visible sur le côté droit) et le nombre de participants qui consultent actuellement l’événement.

## <a name="capabilities"></a>Fonctionnalités

Voici les fonctionnalités des événements de streaming en direct :

|Opération                                            |Limites                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|Créer des événements en direct dans Teams (avec un encodeur externe)  |Entreprise (E1, E3, E5), Éducation (A3, A5)                          |
|Regarder l’événement en direct                                     |Visionneuses disposant d’autorisations pour afficher l’événement et d’une licence Teams valide (sauf si l’événement est public, une licence à afficher n’est pas nécessaire) |
|Résolution maximale                                   |720p                                                                 |
|Nombre maximal d’événements en direct simultanés (en pré-direct ou en direct) |15                                                                   |
|Visionneuses simultanées actives                            |10000                                                                |
|Durée maximale de l’événement en direct                         |4 heures                                                              |
|Prise en charge de la mise en cache réseau des partenaires                      |Hive, Kollective, Riverbed, Ramp, Microsoft                          |
|Autre prise en charge de la mise en cache réseau                        |Peut fonctionner, mais n’est pas pris en charge                                        |
|Contrôles DVR des participants                                |Pause, vitesse de lecture (2x rattrapage, 1x en direct), recherche                |
|Légendes en temps réel                                   |Transmission directe de légende 708 à partir de l’encodeur                                |
|Reconnaissance vocale et légendes automatiques                |Traité après l’événement                                            |
|Discussions interactives                              |Pris en charge via Yammer lorsque l’événement est créé à partir de Yammer           |
|Commentaires teams                                       |Disponible après la fin de l’événement                                       |
|Affichage à la demande sur l’événement en direct (après l’événement)        |Transition automatique du live à la demande pour une consultation et une indexation immédiates dans Teams |
|Enregistrement téléchargeable                               |Traité et disponible après l’événement en direct par les propriétaires               |

Les événements en direct dans Teams sont un service hautement disponible et vous pouvez vous attendre à de bonnes performances à grande échelle. Dans le scénario peu probable qui entraîne la nécessité d’un basculement, les événements en direct utilisant l’encodage externe n’auront pas de redondance et ne seront pas récupérables.
