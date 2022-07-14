---
title: Surveiller et améliorer la qualité des appels pour Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Utilisez les paramètres de qualité de service (QoS), puis appelez l’analytique et le tableau de bord qualité des appels dans Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793241"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Surveiller et améliorer la qualité des appels pour Microsoft Teams

Cet article présente trois outils clés que vous pouvez utiliser pour surveiller, dépanner, gérer et améliorer la qualité des appels dans Microsoft Teams. 

- **Tableau de bord de la qualité des appels (CQD)** : pour analyser les tendances ou les problèmes à l’échelle de l’organisation, améliorez les performances

- **Analyse des appels** : pour analyser la qualité des appels et des réunions pour des utilisateurs individuels

- **Qualité de service (QoS)** : pour hiérarchiser le trafic réseau important



## <a name="monitor-and-troubleshoot-call-quality"></a>Surveiller et résoudre les problèmes de qualité des appels
Vous allez utiliser l’analytique des **appels** par utilisateur et le **tableau de bord qualité** des appels pour rechercher et résoudre les problèmes de qualité des appels qui se produisent pendant l’opération en cours. Cela vous permet d’améliorer les performances sur votre réseau. Ces deux outils se trouvent dans le Centre d’administration Teams.

 - **L’analytique des** appels affiche des informations détaillées sur les appareils, les réseaux et la connectivité liés à  **_des appels et réunions spécifiques_** pour chaque utilisateur dans Teams. Les agents d’administration et de support technique Teams utilisent ces informations pour résoudre les problèmes de qualité des appels et de connexion dans un appel spécifique. Pour plus d’informations, consultez [Configurer l’analytique des appels](set-up-call-analytics.md) et [utiliser l’analytique des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **Le tableau de bord de qualité des appels (CQD)** vous offre une **_vue réseau_** de la qualité des appels au sein de votre organisation. Utilisez les informations de CQD pour identifier et résoudre les problèmes. [Tout d’abord, configurez le CQD](turning-on-and-using-call-quality-dashboard.md). Lisez ensuite [Gérer la qualité des appels et des réunions dans Teams](quality-of-experience-review-guide.md).

 L’analytique des appels et le CQD s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, si un spécialiste du support des communications détermine qu’il a besoin d’aide supplémentaire pour résoudre le problème d’appel d’un utilisateur, il fait remonter l’appel à un ingénieur du support des communications, qui a accès à des informations supplémentaires sur l’appel. À son tour, l’ingénieur du support des communications avertit un ingénieur réseau d’un éventuel problème lié au site qu’il a remarqué dans l’analyse des appels. L’ingénieur réseau vérifie le CQD pour voir si un problème global lié au site peut être une cause contributrice du problème d’appel de l’utilisateur.


## <a name="prioritize-important-network-traffic-using-qos"></a>Hiérarchiser le trafic réseau important à l’aide de QoS
Lorsque vos utilisateurs commencent à utiliser Teams pour les appels et les réunions, ils peuvent rencontrer une rupture ou une coupure de voix d’un appelant lors d’un appel ou d’une réunion. La vidéo partagée peut se figer ou se pixeliser, ou échouer complètement. Cela est dû aux paquets IP qui représentent le trafic vocal et vidéo qui rencontrent une congestion réseau et arrivent hors séquence ou pas du tout. Si cela se produit (ou pour l’empêcher de se produire en premier lieu), utilisez la **qualité de service (QoS).** 

Avec QoS, vous hiérarchisez le trafic réseau sensible aux retards (par exemple, les flux vocaux ou vidéo), ce qui lui permet de « couper en ligne » devant le trafic qui est moins sensible (comme le téléchargement d’une nouvelle application, où le téléchargement d’une seconde supplémentaire n’est pas une grande affaire). QoS identifie et marque tous les paquets dans des flux en temps réel à l’aide d’objets windows stratégie de groupe et d’une fonctionnalité de routage appelée Listes de Access Control basées sur les ports, qui indique à votre réseau d’accorder à votre réseau une voix, une vidéo et un écran partageant leur propre bande passante réseau dédiée.

Dans l’idéal, vous allez implémenter QoS sur votre réseau interne tout en étant prêt à déployer Teams, mais vous pouvez le faire à tout moment. Si vous êtes suffisamment petit, il se peut que vous n’ayez pas besoin de QoS.

Lorsque vous êtes prêt, lisez [Implémenter la qualité de service (QoS) dans Microsoft Teams](QoS-in-Teams.md).

Pour utiliser QoS pour gérer le trafic des réunions, lisez [Définir la façon dont vous souhaitez gérer le trafic multimédia en temps réel pour les réunions Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Voir aussi

[Configurer l’analytique des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurer le CQD](turning-on-and-using-call-quality-dashboard.md)

[Gérer la qualité des appels et des réunions dans Teams](quality-of-experience-review-guide.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
