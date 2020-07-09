---
title: Surveiller et améliorer la qualité des appels de Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Utiliser les paramètres de qualité de service (QoS), puis appeler le tableau de bord d’analyse et de qualité des appels dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085942"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Surveiller et améliorer la qualité des appels de Microsoft teams

Cet article présente les trois principaux outils que vous pouvez utiliser pour contrôler, résoudre les problèmes, gérer et améliorer la qualité d’appel dans Microsoft Teams. 

- **Tableau de bord de qualité des appels (bord)**: pour analyser des tendances ou des problèmes à l’échelle de l’organisation, améliorer les performances

- **Analyse des appels**: pour analyser la qualité des appels et des réunions pour des utilisateurs individuels

- **Qualité de service (QoS)**: définir les priorités du trafic réseau important



## <a name="monitor-and-troubleshoot-call-quality"></a>Surveiller et résoudre les problèmes de qualité d’appel
Vous allez utiliser le tableau de bord d' **analyse des appels** et de **qualité** d’appel par utilisateur pour détecter et résoudre les problèmes de qualité d’appel en cours. Cela vous permet d’améliorer les performances de votre réseau. Ces deux outils se trouvent dans le centre d’administration Teams.

 - L' **analyse des appels** affiche des informations détaillées sur les périphériques, les réseaux et la connectivité liés à des ***appels et des réunions spécifiques*** pour chaque utilisateur dans Teams. Pour résoudre les problèmes de qualité des appels et de connexion d’un appel en particulier, l’administrateur teams et les agents du support technique utilisent ces informations. Pour en savoir plus, consultez la rubrique Configuration de l' [analyse des appels](set-up-call-analytics.md) et [utilisation de l’analyse des appels pour résoudre les problèmes de mauvaise qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - Le **tableau de bord de qualité des appels (bord)** vous permet d' ***accéder à*** l’ensemble de votre organisation via le réseau. Utilisez des informations bord pour vous aider à identifier et résoudre les problèmes. Tout d’abord, [configurez bord](turning-on-and-using-call-quality-dashboard.md). Ensuite, lisez [gérer la qualité des appels et des réunions dans Microsoft teams](quality-of-experience-review-guide.md).

 L’analyse des appels et bord s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, si un spécialiste du support des communications détermine qu’il a besoin d’une aide supplémentaire pour résoudre le problème d’appel d’un utilisateur, il a transféré l’appel vers un technicien du support technique, qui a accès à des informations supplémentaires sur l’appel. Le technicien du support technique alerte par le biais d’un ingénieur réseau qu’il a rencontré un problème de site potentiel qu’il a remarqué dans l’analyse de l’appel. L’ingénieur réseau vérifie bord pour savoir si un problème global lié au site peut être à l’origine du problème de l’utilisateur.


## <a name="prioritize-important-network-traffic-using-qos"></a>Hiérarchiser le trafic réseau important à l’aide de QoS
À mesure que les utilisateurs commencent à utiliser teams pour les appels et les réunions, ils peuvent rencontrer le problème de la voix de l’appelant ou de les couper et sortir d’un appel ou d’une réunion. La vidéo partagée risque de se figer ou de s’embloquer complètement. Ce problème est dû aux paquets IP qui représentent le trafic audio et vidéo, qui rencontrent une congestion du réseau et qui arrivent en entrée ou pas du tout. Le cas échéant, utilisez la **qualité de service (QoS)** pour éviter qu’elle ne se produise au départ. 

Avec la qualité de service (QoS), vous donnez la priorité au trafic réseau (par exemple, les flux vocaux ou vidéo), qui lui permet d’être « coupé ligne » devant le trafic moins sensible (par exemple, le téléchargement d’une nouvelle application, où une seconde supplémentaire à télécharger n’est pas une grande affaire). La fonction QoS identifie et marque tous les paquets en flux temps réel à l’aide d’objets de stratégie de groupe Windows et d’une fonctionnalité de routage appelée listes de contrôle d’accès basée sur le port, qui demande à votre réseau de partager de la bande passante, de la vidéo et de l’écran à l’aide de leur propre bande passante réseau dédiée.

Idéalement, vous mettrez en œuvre la qualité de service (QoS) sur votre réseau interne tout en vous préparez à déployer Teams, mais vous pouvez le faire à tout moment. Si vous avez un petit nombre d’insuffisant, vous n’aurez peut-être pas besoin de QoS.

Lorsque vous êtes prêt, lisez [mettre en œuvre la qualité de service (QoS) dans Microsoft teams](QoS-in-Teams.md).

Pour utiliser la qualité de service (QoS) pour gérer le trafic de la réunion, consultez [définir la manière dont vous souhaitez gérer le trafic multimédia en temps réel pour les réunions teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Rubriques connexes

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurer bord](turning-on-and-using-call-quality-dashboard.md)

[Gérer la qualité des appels et des réunions dans Microsoft teams](quality-of-experience-review-guide.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

