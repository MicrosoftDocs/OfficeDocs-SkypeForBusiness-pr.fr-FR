---
title: Résoudre les problèmes de faible bande passante pour Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Obtenez de l’aide sur les problèmes de réunion et de vidéo liés aux problèmes de bande passante faible dans Teams. Que vous soyez parent, enseignant ou Administration informatique, vous disposez d’options pour améliorer l’expérience avec Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426811"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Résoudre les problèmes de faible bande passante pour Teams

Cet article fournit aux administrateurs informatiques les meilleures pratiques en cas de problèmes de bande passante faible dans Teams.

De nombreux éléments réseau peuvent affecter les performances lors de l’utilisation de Microsoft Teams.

- Connexion Internet à faible vitesse pour l’école.
- Connexion Internet à faible vitesse pour un ou plusieurs étudiants.
- Les moments de la journée où la bande passante est faible en raison de l'utilisation du réseau dans une zone donnée.
- Les pannes ne sont pas locales pour l’école ou les étudiants, mais affectent le rendement.
- Problèmes avec le matériel qui provoquent des problèmes de bande passante faible.

> [!IMPORTANT]
> Découvrez [comment Microsoft Teams utilise la mémoire](teams-memory-usage-perf.md) pour les limitations de ressources sur les appareils.
>
>Pour obtenir des conseils sur le réseau Teams, consultez [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>Résolution des problèmes de faible bande passante pour les administrateurs informatiques

Certains problèmes peuvent uniquement être résolus avec un focus étroit au niveau de l’utilisateur individuel.

Si des problèmes de bande passante se produisent pour de nombreux utilisateurs ou si les actions effectuées au niveau de l’utilisateur n’ont pas été utiles, l’action à l’échelle de l’école est l’étape suivante.

> [!NOTE]
> Vous pouvez également lire le [Guide de révision de la qualité de l’expérience](quality-of-experience-review-guide.md). Il n’est pas spécifique à EDU, mais a des informations précieuses.

### <a name="meetings-and-video"></a>Réunions et vidéo

Tenez compte des actions ci-dessous lorsque vous traitez des problèmes de réunion liés à une bande passante réseau faible.

#### <a name="meeting-video-policies"></a>Stratégies vidéo de réunion

Teams met automatiquement à l’échelle la qualité de la réunion en fonction de la bande passante détectée par un utilisateur. Toutefois, vous pouvez définir d’autres restrictions pour préserver la bande passante.

Voici quelques restrictions que vous pouvez définir via la stratégie :

- Désactivez complètement la vidéo afin que personne ne puisse utiliser la vidéo.
- Limitation du débit de bits multimédias, qui est défini par utilisateur.

Pour plus de stratégies que vous devez définir pour les réunions et la vidéo, lisez [les paramètres de stratégie de réunion dans Teams : Audio et vidéo](meeting-policies-audio-and-video.md).

#### <a name="screen-sharing-policies"></a>Stratégies de partage d'écran

Dans Teams, les utilisateurs peuvent partager l’ensemble de leur écran ou fenêtres individuelles.

Le partage d’un écran entier utilise plus de bande passante que le simple partage d’une fenêtre.

- Empêcher les utilisateurs de partager l’intégralité de leur écran par le biais d’une stratégie.
- Demandez aux enseignants de partager uniquement des applications, et non leur écran entier.

Découvrez les stratégies de partage d’écran dans [les paramètres de stratégie de réunion dans Teams : Audio et vidéo](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Numéro à composer pour des réunions

Il peut être plus facile pour certains étudiants de se connecter à des sessions en classe.

- Fournissez un numéro d’accès pour les réunions Teams en guise d’alternative à une réunion vidéo.

Pour plus d’informations, consultez [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Scénarios de faible bande passante en tant qu'éducateur

La résolution des problèmes de bande passante par les enseignants peut être un meilleur choix que l’action informatique dans les situations suivantes :

- Le problème est intermittent.
- Il y a une heure spécifique de la journée que vous pouvez prévoir qu’il y a un problème.

Pour connaître les étapes qu’un enseignant peut suivre pour résoudre les problèmes de bande passante, consultez [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Scénarios de faible bande passante en tant que parent ou élève

Parfois, le problème de bande passante est du côté d’un étudiant.

- Leur domicile n’a peut-être pas accès à une bande passante élevée.
- Il se peut que de nombreuses personnes dans leur région immédiate consomment également de la bande passante.
- Il peut y avoir une instabilité d’Internet.

Nous avons mis en place des conseils dans notre article [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) pour les parents et les étudiants.
