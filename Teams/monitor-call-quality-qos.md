---
title: Surveiller et améliorer la qualité des appels pour les Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Utilisez les paramètres de qualité de service (QoS), puis le tableau de bord d’analyse des appels et de la qualité des Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2c40e3a79ab8cf3776ecfdb9c6488f219b24e407
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636812"
---
# <a name="microsoft-teams-monitor-and-improve-call-quality"></a>Microsoft Teams : surveiller et améliorer la qualité des appels

Cet article présente trois outils clés que vous pouvez utiliser pour surveiller, résoudre des problèmes, gérer et améliorer la qualité des appels Microsoft Teams. 

- **Tableau de bord de qualité** des appels : pour analyser les tendances ou problèmes à l’échelle de l’organisation, améliorer les performances

- **Analyse des appels**: analyser la qualité des appels et des réunions pour des utilisateurs individuels

- **Qualité de service (QoS)**: pour hiérarchiser le trafic réseau important



## <a name="monitor-and-troubleshoot-call-quality"></a>Surveiller la qualité des appels et résoudre les problèmes
Vous utiliserez l’analyse des  appels et le tableau de bord de qualité des appels par utilisateur pour rechercher et résoudre les problèmes de qualité des appels qui surviennent en cours d’opération.  Cela vous permet d’améliorer les performances sur votre réseau. Ces deux outils sont disponibles dans le Teams d’administration.

 - **L’analyse** des appels affiche des informations détaillées sur les appareils, les réseaux et la connectivité liés à des appels et réunions **_spécifiques_** pour chaque utilisateur Teams. Teams et les agents du service d’aide utilisent ces informations pour résoudre les problèmes de qualité et de connexion d’un appel spécifique. Pour en savoir plus, lisez [Configurer l’analyse](set-up-call-analytics.md) des appels et Utiliser l’analyse des appels pour [résoudre les problèmes de qualité des appels.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Le tableau de bord de** qualité **** des appels offre une vue d’ensemble de la qualité des appels au sein de votre organisation. Utilisez les informations du CQD pour identifier et résoudre les problèmes. Tout [d’abord, définissez le CQD.](turning-on-and-using-call-quality-dashboard.md) Lisez ensuite [Gérer l’appel et la qualité des réunions dans Teams.](quality-of-experience-review-guide.md)

 L’analyse des appels et le CQD s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, si un spécialiste des communications détermine qu’il lui faut une aide supplémentaire pour résoudre un problème d’appel d’un utilisateur, il le fait à un ingénieur du support des communications, qui a accès à des informations supplémentaires sur l’appel. L’ingénieur du support des communications avertit également un ingénieur réseau d’un problème lié au site qu’il a remarqué dans l’analyse des appels. L’ingénieur réseau vérifie le CQD pour voir si un problème global lié au site peut être une cause de contribution du problème d’appel de l’utilisateur.


## <a name="prioritize-important-network-traffic-using-qos"></a>Hiérarchiser le trafic réseau important à l’aide de QoS
Lorsque vos utilisateurs commencent à utiliser des Teams pour les appels et les réunions, ils peuvent rencontrer la coupure de voix d’un appelant ou la coupure ou l’coupure d’un appel ou d’une réunion. La vidéo partagée peut se figer ou pixelner, ou échouer. Cela est dû aux paquets IP qui représentent le trafic voix et vidéo rencontré une congestion du réseau et l’arrivée ou non d’une séquence. Si cela se produit (ou pour éviter qu’il se produise en premier lieu), utilisez la qualité de **service (QoS).** 

Avec QoS, vous hiérarchisez le trafic réseau qui demande un délai important (par exemple, les flux vocaux ou vidéo), ce qui permet de l’aligner sur le trafic moins sensible (par exemple, le téléchargement d’une nouvelle application, qui ne demande pas une seconde supplémentaire de téléchargement). QoS identifie et marque tous les paquets dans des flux en temps réel à l’aide d’objets de stratégie de groupe Windows et d’une fonctionnalité de routage appelée Listes de contrôle d’accès basée sur les ports, qui demande à votre réseau de fournir à la voix, à la vidéo et au partage d’écran sa propre bande passante réseau dédiée.

Dans l’idéal, vous devez implémenter QoS sur votre réseau interne lorsque vous êtes prêt à déployer Teams, mais vous pouvez le faire à tout moment. Si vous êtes assez petit, vous n’aurez peut-être pas besoin de QoS.

Lorsque vous êtes prêt, lisez Implémenter la qualité de [service (QoS) dans Microsoft Teams.](QoS-in-Teams.md)

Pour utiliser la QoS pour gérer le trafic des réunions, lisez Définir la façon dont vous voulez gérer le trafic de médias en temps réel pour [Teams réunions.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurer le CQD](turning-on-and-using-call-quality-dashboard.md)

[Gérer la qualité des appels et des réunions dans Teams](quality-of-experience-review-guide.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
