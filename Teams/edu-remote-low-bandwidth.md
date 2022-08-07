---
title: Guidage de Microsoft Teams à faible bande passante pour EDU
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Article sur Microsoft Teams pour EDU pour aider à résoudre les problèmes de réunion et de vidéo liés à une faible bande passante. Que vous soyez un parent, un éducateur ou un administrateur informatique, vous avez des options pour améliorer l'expérience avec Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87800943dc6e6a615e09b7995a613d109ebcf30c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269049"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Aide pour les situations de faible bande passante pour Teams for EDU

Il existe de nombreux éléments réseau en matière d’utilisation de Microsoft Teams qui peuvent affecter les performances. Une bande passante faible est l’une des situations qui peuvent vous paraître complètement hors de votre contrôle. Prenez en compte les situations suivantes :

- Une connexion Internet à faible débit pour l’établissement scolaire.
- Une connexion Internet à faible débit pour un ou plusieurs étudiants.
- Les moments de la journée où la bande passante est faible en raison de l'utilisation du réseau dans une zone donnée.
- Périodes de faible bande passante dues à des pannes qui ne concernent ni l'école ni les étudiants, mais qui affectent néanmoins les performances.
- Les problèmes non liés à la bande passante (par exemple, les problèmes de matériel) qui se font passer pour des problèmes de faible bande passante.

Cet article vous donnera les meilleures pratiques à suivre pour diverses activités de Teams lorsque vous êtes confronté à un problème de faible bande passante.

> [!IMPORTANT]
> Vous trouverez ici des informations sur [Comment Microsoft Teams utilise la mémoire](teams-memory-usage-perf.md), car outre les problèmes de faible bande passante, il est possible que vous rencontriez des problèmes de ressources sur votre appareil. Si vous recherchez des conseils sur le réseau dans Microsoft Teams, voir [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-admins"></a>Résolution des problèmes de faible bande passante pour les administrateurs

Le point important à retenir, en tant qu’administrateur informatique, est que même si vous avez des solutions aux problèmes de faible bande passante qui sont largement répartis pour résoudre rapidement les problèmes, les solutions doivent être prises en compte avec soin. Certains problèmes peuvent être en mesure de résoudre avec un focus plus étroit au niveau de l’enseignant ou même de l’étudiant/parent.

En résumé, si le problème de faible bande passante concerne un grand nombre d'élèves, il est logique que l'administrateur informatique prenne des mesures, et il est également logique que les mesures prises au niveau des élèves et des éducateurs n'aient pas été utiles.

> [!NOTE]
> Si vous avez le temps de vous investir, le [Guide d’examen de la qualité de l’expérience](quality-of-experience-review-guide.md) constitue une lecture intéressante (cet article n’est pas spécifique à l’éducation, elle contient toutefois des informations précieuses). Ce guide permettra aux administrateurs informatiques expérimentés d'approfondir l'expérience pour leurs éducateurs et leurs élèves.

### <a name="meetings-and-video"></a>Réunions et vidéo

Les réunions constituent un objectif principal pour les problèmes de faible bande passante . plus précisément, vidéo dans les réunions. Un administrateur informatique doit prendre en compte les actions ci-dessous lors du traitement des problèmes signalés par les étudiants ou les enseignants en ce qui concerne la meilleure expérience de réunion dans un cadre pédagogique.

#### <a name="meeting-policies"></a>Stratégies de réunion

En ce qui concerne les réunions, l'un des domaines les plus préoccupants dans les situations de faible bande passante est celui des vidéos. En plus de la capacité de Teams à s'adapter automatiquement à la bande passante détectée, vous disposez, en tant qu'administrateur informatique, d'options de stratégie que vous pouvez définir au niveau de chaque organisateur et/ou de chaque utilisateur. Ces options vous permettent d'offrir à chacun la meilleure expérience possible compte tenu de la bande passante dont il dispose à un moment donné.

Voici quelques-uns des éléments que vous pouvez définir par le biais d’une stratégie :

- Désactivation totale de la vidéo pour qu'aucune personne ne puisse l'activer.
- Débit binaire du média (ce paramètre est défini par utilisateur).

Pour en savoir plus sur les options qui s'offrent à vous et sur les stratégies à définir pour les réunions et les vidéos, voir la rubrique [Paramètres des stratégies de réunion dans Teams : Audio et vidéo](meeting-policies-audio-and-video.md).

#### <a name="screen-sharing-policies"></a>Stratégies de partage d'écran

Dans d’autres cas, il est possible que les enseignants partagent l’intégralité de leur écran avec des étudiants, alors que le partage doit être limité à une application en rapport avec le cours enseigné. Ce paramètre peut également être défini par le biais d'une stratégie, s'il s'agit d'un moyen plus souhaitable que de laisser les éducateurs faire ce choix individuellement.

Pour avoir une bonne idée de ce que vous pouvez faire pour limiter le partage d'écran par le biais des paramètres de stratégie, consultez la rubrique [Paramètres de stratégie de réunion dans Teams : Audio et vidéo](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Numéro à composer pour des réunions

Il peut être plus facile aux étudiants de tenter de se connecter à certaines sessions de cours. Vous pouvez fournir un numéro de connexion pour les réunions Teams afin que les étudiants ayant des problèmes puissent avoir une alternative pour participer à une réunion vidéo.

Pour plus d’informations à ce sujet, vous pouvez consulter [Définir des numéros de téléphone inclus sur les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Scénarios de faible bande passante en tant qu'éducateur

Les éducateurs doivent se sentir habilités à prendre des mesures pour résoudre les problèmes de bande passante insuffisante, et peuvent être un choix supérieur à l'action de l'administration informatique dans les situations suivantes :

- Si le problème est intermittent ou relativement éphémère.
- S’il existe une heure précise dans la journée lors de laquelle vous pouvez anticiper le problème ou que la période de faible bande passante est prévisible.

Dans ces situations, vous pouvez prendre des mesures.

Pour plus d’informations, voir [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Scénarios de faible bande passante en tant que parent ou élève

Il existe également des situations dans lesquelles vous devez aborder les problèmes de manière proactive avec vos enseignants, où le problème de bande passante peut se situer au niveau de l’étudiant (par exemple, un grand nombre d’étudiants peuvent regarder les leçons vidéo sans problème, mais un petit nombre rencontre des problèmes).

Il n’est pas raisonnable de s’attendre à ce que de nombreux parents soient en mesure de résoudre ces problèmes. Les problèmes de faible bande passante peuvent être hors du contrôle d’un étudiant ou d’un parent (leur domicile n’a peut-être pas accès à une bande passante élevée, il peut y avoir de nombreuses personnes dans leur zone immédiate consommant de la bande passante et affectant ce qu’ils peuvent faire, il peut y avoir une instabilité d’Internet, etc.).

Nous avons réuni des conseils dans notre article [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) pour les parents et les étudiants. Vous pouvez également consulter et essayer ces recommandations si vous rencontrez des problèmes.