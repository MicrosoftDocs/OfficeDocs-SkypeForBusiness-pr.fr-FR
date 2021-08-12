---
title: Surveiller et améliorer de la qualité des appels pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Utilisez les paramètres de qualité de service (QoS), puis analyse des appels et tableau de bord de qualité des appels dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286263"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Surveiller et améliorer de la qualité des appels pour Microsoft Teams

Cet article présente trois outils clés que vous pouvez utiliser pour surveiller, dépanner, gérer et améliorer la qualité des appels dans Microsoft Teams. 

- **Tableau de bord de qualité des appels :** pour analyser les tendances ou les problèmes à l’échelle de l’organisation, améliorez les performances

- **Analyse des appels**: pour analyser la qualité des appels et des réunions pour des utilisateurs individuels

- **Qualité de service (QoS)**: pour hiérarchiser le trafic réseau important



## <a name="monitor-and-troubleshoot-call-quality"></a>Surveiller et résoudre les problèmes de qualité des appels
Vous utiliserez l’analyse des  appels par utilisateur et le Tableau de bord de qualité des appels pour rechercher et résoudre les problèmes de qualité des appels qui surviennent au cours des opérations en cours.  Cela vous permet d’améliorer les performances sur votre réseau. Ces deux outils sont dans le centre d Teams’administration.

 - **L’analyse** des appels affiche des informations détaillées sur les appareils, les réseaux et la connectivité liés à des appels et réunions **_spécifiques_** pour chaque utilisateur Teams. Teams administrateur et les agents du service d’aide utilisent ces informations pour résoudre les problèmes de qualité et de connexion des appels dans un appel spécifique. Pour en savoir plus, [lisez Configurer l’analyse des appels](set-up-call-analytics.md) et utiliser l’analyse des appels [pour résoudre les problèmes de qualité des appels médiocres.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - Le Tableau de bord de qualité **** des appels **(CQD)** vous donne une vue à l’échelle du réseau de la qualité des appels au sein de votre organisation. Utilisez les informations de CQD pour vous aider à identifier et résoudre les problèmes. Tout [d’abord, configurer le CQD](turning-on-and-using-call-quality-dashboard.md). Lisez ensuite [Gérer la qualité des appels et des réunions dans Teams](quality-of-experience-review-guide.md).

 L’analyse des appels et le CQD s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, si un spécialiste du support des communications détermine qu’il a besoin d’aide supplémentaire pour résoudre le problème d’appel d’un utilisateur, il passe l’appel à un ingénieur du support des communications, qui a accès à des informations supplémentaires sur l’appel. À son tour, l’ingénieur du support des communications avertit un ingénieur réseau d’un éventuel problème lié au site qu’il a remarqué dans l’analyse des appels. L’ingénieur réseau vérifie le CQD pour voir si un problème global lié au site peut être à l’origine du problème d’appel de l’utilisateur.


## <a name="prioritize-important-network-traffic-using-qos"></a>Hiérarchiser le trafic réseau important à l’aide de QoS
Lorsque vos utilisateurs commencent à utiliser Teams pour les appels et les réunions, ils peuvent rencontrer la coupure de voix d’un appelant ou l’coupure d’un appel ou d’une réunion. La vidéo partagée peut se figer, pixelner ou échouer complètement. Cela est dû aux paquets IP qui représentent le trafic vocal et vidéo qui rencontre une congestion du réseau et arrive en dehors de l’ordre ou pas du tout. Si cela se produit (ou pour l’empêcher de se produire en premier lieu), utilisez la qualité **de service (QoS).** 

Avec QoS, vous hiérarchisez le trafic réseau retardé (par exemple, les flux vocaux ou vidéo), ce qui lui permet de « couper en ligne » devant le trafic qui est moins sensible (comme le téléchargement d’une nouvelle application, où une seconde supplémentaire à télécharger n’est pas une grande affaire). QoS identifie et marque tous les paquets dans les flux en temps réel à l’aide d’objets de stratégie de groupe Windows et d’une fonctionnalité de routage appelée Listes de contrôle d’accès basée sur les ports, qui demande à votre réseau de fournir la voix, la vidéo et le partage d’écran de sa propre bande passante réseau dédiée.

Dans l’idéal, vous allez implémenter la QoS sur votre réseau interne tout en vous préparez à déployer Teams, mais vous pouvez le faire à tout moment. Si vous êtes assez petit, vous n’aurez peut-être pas besoin de QoS.

Lorsque vous êtes prêt, lisez Implémenter la qualité de [service (QoS) dans Microsoft Teams](QoS-in-Teams.md).

Pour utiliser la QoS pour gérer le trafic des réunions, lisez Définir la façon dont vous souhaitez gérer le trafic multimédia en temps réel pour [Teams réunions.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Rubriques connexes

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’Analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurer le TBQA](turning-on-and-using-call-quality-dashboard.md)

[Gérer la qualité des appels et des réunions dans Teams](quality-of-experience-review-guide.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)