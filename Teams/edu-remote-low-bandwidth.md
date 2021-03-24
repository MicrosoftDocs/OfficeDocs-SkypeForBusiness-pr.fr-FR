---
title: Instructions pour une faible bande passante dans Microsoft Teams pour l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: L'article de Microsoft Teams pour l’éducation vous aide à résoudre les problèmes de réunion et de vidéo liés à une bande passante faible. Que vous soyez parent, enseignant ou administrateur informatique, vous disposez d’options pour améliorer votre expérience avec Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111080"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Aide dans des situations de bande passante faible dans Teams pour l'éducation

Un grand nombre d’éléments réseau s’appliquent à Microsoft Teams et peuvent affecter ses performances. Une bande passante faible en fait partie et représente une situation lors de laquelle vous sentez que vous perdez totalement le contrôle. Vous devez tenir compte des éléments suivants :

- Une connexion Internet à faible débit pour l’établissement scolaire.
- Une connexion Internet à faible débit pour un ou plusieurs étudiants.
- L'heure de la journée où la bande passante est faible due à une utilisation du réseau dans la région.
- Des périodes de faible bande passante en raison de pannes locales autres qu'à l’école ou pour les étudiants, mais qui affectent néanmoins les performances.
- Des problèmes non liés à la bande passante (par exemple, des problèmes de matériel) passant pour des problèmes de bande passante faible.

Cet article vous présente les meilleures pratiques à suivre pour plusieurs activités Teams lorsque vous rencontrez un problème de bande passante faible.

> [!IMPORTANT]
> Vous trouverez ici des informations sur [Comment Microsoft Teams utilise la mémoire](teams-memory-usage-perf.md), car outre les problèmes de faible bande passante, il est possible que vous rencontriez des problèmes de ressources sur votre appareil. Si vous recherchez des conseils sur le réseau dans Microsoft Teams, voir [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Résoudre les problèmes de bande passante faible pour les administrateurs informatiques

Il est important de ne pas oublier en tant qu'administrateur informatique que, bien que vous disposiez de solutions largement répandues pour des problèmes de faible bande passante qui permettent de résoudre rapidement les problèmes, cette démarche doit être étudiée avec soin, car certains problèmes peuvent être résolus avec une vue plus ciblée au niveau de l'enseignant ou de l’étudiant/parent.

En bref, si le problème de faible bande passante se produit pour un grand groupe d’étudiants, l’exécution d’une action de la part d'un administrateur informatique est logique et elle est également utile si les actions effectuées au niveau étudiant/enseignant ne sont pas efficaces.

> [!NOTE]
> Si vous avez le temps de vous investir, le [Guide d’examen de la qualité de l’expérience](quality-of-experience-review-guide.md) constitue une lecture intéressante (cet article n’est pas spécifique à l’éducation, elle contient toutefois des informations précieuses). Cela permet aux administrateurs informatiques d’entrer dans les détails quant à l’expérience des enseignants et des étudiants.

### <a name="meetings-and-video"></a>Réunions et vidéo

Les réunions, notamment les vidéos dans des réunions, sont le focus principal en matière de problèmes de faible bande passante. Vous trouverez ci-dessous quelques-unes des mesures qu’un administrateur informatique doit prendre en compte lors de la résolution de problèmes signalés par des étudiants ou des enseignants en ce qui concerne la meilleure expérience en réunion dans un cadre éducatif.

#### <a name="meeting-policies"></a>Stratégies de réunion

En ce qui concerne les réunions, l’un des aspects les plus importants quant aux situations de faible bande passante est lié aux vidéos. Heureusement, outre Teams qui est capable de s'adapter automatiquement à la bande passante détectée, vous disposez d’options de stratégie, en tant qu'administrateur informatique, que vous pouvez définir au niveau de l’organisateur et/ou de l’utilisateur pour offrir à tout le monde une expérience optimale compte tenu de la bande passante qu’ils doivent utiliser à un moment donné.

Voici quelques-uns des éléments que vous pouvez définir par le biais d’une stratégie :

- Désactivation totale de la vidéo pour qu'aucune personne ne puisse l'activer.
- Vitesse de transmission du multimédia (définie par l’utilisateur).

Pour en savoir plus sur les options disponibles et découvrir les spécificités des stratégies à mettre en place pour les réunions et les vidéos, consultez les [Paramètres de stratégie de réunion dans Teams : audio et vidéo](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) pour obtenir des informations détaillées.

#### <a name="screen-sharing-policies"></a>Stratégies de partage d'écran

Dans d’autres cas, il est possible que les enseignants partagent l’intégralité de leur écran avec des étudiants, alors que le partage doit être limité à une application en rapport avec le cours enseigné. Il est également possible de paramétrer cette option par le biais d’une stratégie, si celle-ci représente une meilleure option que de laisser les enseignants effectuer ce choix de manière individuelle.

Pour découvrir ce que vous pouvez faire au sujet de la limitation du partage d’écran via des paramètres de stratégie, voir les [Paramètres de stratégie de réunion dans Teams : partage d’écran](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Numéro à composer pour des réunions

Il peut être plus facile aux étudiants de tenter de se connecter à certaines sessions de cours. Vous pouvez fournir un numéro de connexion pour les réunions Teams afin que les étudiants ayant des problèmes puissent avoir une alternative pour participer à une réunion vidéo.

Pour plus d’informations à ce sujet, vous pouvez consulter [Définir des numéros de téléphone inclus sur les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Scénarios de faible bande passante en tant qu’enseignant

Les enseignants doivent se sentir habilités à prendre des mesures pour résoudre les problèmes de faible bande passante. Il s'agit d’un choix d'action plus élevé de la part de l'administrateur informatique dans les situations suivantes :

- Si le problème est intermittent ou relativement éphémère.
- S’il existe une heure précise dans la journée lors de laquelle vous pouvez anticiper le problème ou que la période de faible bande passante est prévisible.

Dans ces situations, vous pouvez prendre des mesures.

Pour plus d’informations, voir [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Scénarios de faible bande passante en tant que parent ou étudiant

Il existe également des situations dans lesquelles vous devez aborder les problèmes de manière proactive avec vos enseignants, où le problème de bande passante peut se situer au niveau de l’étudiant (par exemple, un grand nombre d’étudiants peuvent regarder les leçons vidéo sans problème, mais un petit nombre rencontre des problèmes).

Il n’est pas raisonnable de s'attendre à ce que beaucoup de parents soient en mesure de résoudre ces problèmes. Les problèmes de bande passante faible peuvent en effet provenir de l'étudiant ou d’un contrôle parental (leur domicile n’a peut-être pas accès à une bande passante élevée, il est possible qu’un grand nombre de personnes situées dans les environs immédiats s'accaparent la bande passante et affectent ce qui peut être effectué, Internet est peut-être instable, etc.).

Nous avons réuni des conseils dans notre article [Utiliser Teams pour le travail scolaire lorsque la bande passante est faible](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) pour les parents et les étudiants. Vous pouvez également consulter et essayer ces recommandations si vous rencontrez des problèmes.