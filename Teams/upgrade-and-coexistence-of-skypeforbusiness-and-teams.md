---
title: Mise à niveau de Microsoft teams à partir de Skype entreprise | Modes, coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Des informations sur les modes et modes de coexistence de Skype entreprise et Microsoft Teams, ainsi que la mise à niveau vers des équipes de Skype entreprise avec des exemples de scénario.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcb1570a87740d899a5f92957c0335e70d7f91ba
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665416"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Choisissez le passage de votre mise à niveau de Skype entreprise à teams

![Diagramme de parcours de mise à niveau, mettant l’accent sur l’étape de définition du projet](media/upgrade-banner-project-definition.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de définition du projet")

Cet article fait partie de l’étape définition du projet de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)

En tant que client Skype entreprise existant, la transition complète vers teams peut prendre un certain temps. Néanmoins, vous pouvez commencer à utiliser teams dès aujourd’hui en permettant à vos utilisateurs d’utiliser teams en même temps que Skype entreprise. Étant donné qu’il existe d’autres fonctionnalités qui se chevauchent entre les deux applications, nous vous conseillons de passer en revue les modes de coexistence et de mise à niveau disponibles pour vous aider à déterminer le chemin approprié pour votre organisation. Par exemple, vous pouvez choisir d’activer toutes les charges de travail sur les deux solutions sans interopérabilité. Vous pouvez également décider de gérer l’utilisation de l’utilisateur, soit en introduisant progressivement les fonctionnalités d’équipe ou en ciblant des groupes d’utilisateurs pour les fonctionnalités sélectionnées, tant que votre organisation n’est pas en mesure de mettre à niveau tout le monde vers Teams. Utilisez le résultat de votre pilote pour vérifier le bon déroulement de la mise à niveau de votre organisation.

> [!IMPORTANT]
> Skype Entreprise Online sera supprimé le 31 juillet 2021. Après cette date, il ne sera plus accessible ni pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui.

Cet article présente les différents modes qui vous permettent de gérer les modalités de gestion des modalités de Skype entreprise et équipes disponibles pour les utilisateurs. Comme pour n’importe quel déploiement, nous vous encourageons vivement à [piloter votre plan prévu](pilot-essentials.md) avec un groupe d’utilisateurs sélectionné avant de mettre à niveau votre organisation vers Teams. N’oubliez pas que l’introduction d’une nouvelle technologie peut être perturbatrice pour les utilisateurs. Prenez le temps d’évaluer la compatibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter les modes décrits dans les présentes.

> [!TIP]
> Rejoignez-nous pour des ateliers en direct et interactifs qui vous aideront à partager des conseils, des meilleures pratiques et des ressources conçues pour lancer la planification et l’implémentation de la mise à niveau.
>
>Participez d’abord à la planification de votre session de [mise à niveau](https://aka.ms/SkypeToTeamsPlanning) pour commencer.


## <a name="upgrade-journey-building-blocks"></a>Briques de construction de mise à niveau

Pour préparer officiellement votre organisation aux équipes, vous devez commencer à planifier des scénarios de mise à niveau, ce qui permettra finalement à votre organisation d’adopter pleinement teams comme votre solution de communication et de collaboration unique.

Pour vous guider dans le processus de prise de décision, vous devez vous familiariser avec les différents modes, concepts et terminologie pertinents pour la mise à niveau de Skype entreprise vers Teams. Pour plus d’informations, reportez-vous à la rubrique [Microsoft Teams, coexistence et interopérabilité de Skype entreprise](https://aka.ms/SkypeToTeams-Coexist).

Un utilisateur ayant migré vers teams n’utilise plus un client Skype entreprise, à l’exception de la participation à une réunion hébergée dans Skype entreprise. Toutes les conversations et les appels entrants dans le client teams de l’utilisateur, que l’expéditeur utilise teams ou Skype entreprise. Toutes les nouvelles réunions organisées par l’utilisateur mis à niveau seront planifiées en tant que réunions d’équipes. Si l’utilisateur tente d’utiliser le client Skype entreprise, le lancement de conversations et d’appels est bloqué<sup>1</sup>. Toutefois, l’utilisateur peut (et doit) toujours utiliser le client Skype entreprise pour participer aux réunions auxquelles il est invité.

Les administrateurs gèrent leur transition vers teams à l’aide du concept de [mode](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), qui est une propriété de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un utilisateur migré vers teams comme décrit ci-dessus est en mode « TeamsOnly ». Dans le cas d’une organisation migrant vers Teams, l’objectif ultime consiste à déplacer tous les utilisateurs vers le mode TeamsOnly.

Il existe deux méthodes pour migrer une organisation existante avec Skype entreprise (en ligne ou sur site) vers teams :

- **Méthode de superposition de capacités** (avec le mode îlot) : les utilisateurs d’une organisation Skype entreprise existante sont introduits dans teams pour qu’ils puissent utiliser les deux clients côte à côte pendant une phase de transition. Pendant ce laps de temps, la plupart des fonctionnalités d’équipe sont disponibles. Le mode de cette configuration est appelé îlots, et il s’agit du mode par défaut de toute organisation existante avec Skype entreprise. Lorsque l’organisation est prête, l’administrateur déplace les utilisateurs vers le mode TeamsOnly.

- **Sélectionner une méthode de fonctions** (à l’aide d’un ou de plusieurs modes Skype entreprise) : l’administrateur gère la transition (de Skype entreprise à Teams) de la fonctionnalité de conversation, d’appel et de planification de réunion pour les utilisateurs de leur organisation. Chacune de ces fonctions est disponible dans Skype entreprise ou Teams, mais pas les deux. Les administrateurs utilisent TeamsUpgradePolicy pour contrôler le moment auquel décaler cette fonctionnalité vers équipes pour leurs utilisateurs. Les utilisateurs qui ne sont pas encore en mode TeamsOnly continuent d’utiliser Skype entreprise pour les discussions et les appels, et les deux utilisateurs peuvent communiquer par le biais de fonctionnalités d’interopérabilité. Les administrateurs gèrent la transition en migrant progressivement de plus utilisateurs vers le mode TeamsOnly.

<sup>1</sup> les anciens clients Skype entreprise livrés avant 2017 ne respectent pas TeamsUpgradePolicy. Vérifiez que vous utilisez la dernière version de client Skype entreprise disponible dans votre canal Office.

Vous trouverez ci-dessous les principaux facteurs qui vous aideront à déterminer le chemin approprié pour votre organisation. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Méthode de superposition des capacités (à l’aide du mode îlot)

Grâce à la méthode de superposition des capacités, les utilisateurs peuvent utiliser des équipes et des clients Skype entreprise pour la messagerie instantanée, les appels VoIP et les réunions. Dans le cadre de cette méthode, l’appel de chat et VOIP dans teams est axé sur l’organisation intra-entreprise, alors que Skype entreprise autorise les appels vocaux et VOIP/PSTN avec des organisations externes (le cas échéant). Les réunions peuvent être planifiées et suivies dans les deux produits.

Lors de l’utilisation de la méthode de superposition des capacités, le trafic de communication pour Skype entreprise et teams reste différent (même pour le même utilisateur) et les deux clients ne communiquent jamais entre eux (pour les utilisateurs au sein de la même organisation). Les expériences utilisateur sont basées sur la configuration du destinataire. Par exemple, supposons que l’utilisateur A utilise cette méthode de mise à niveau :

- Les communications déclenchées à partir du client Skype entreprise d’un autre utilisateur seront toujours portées sur le client Skype entreprise d’un utilisateur.

- Les communications déclenchées par le client teams par un *utilisateur au sein de la même organisation* seront toujours débarquées dans le client teams de l’utilisateur.

- Les communications déclenchées par le client équipes par un *utilisateur dans une organisation externe* seront toujours affectées par le client Skype entreprise de l’utilisateur.

Si vous avez affecté une licence Microsoft 365 ou Office 365 à vos utilisateurs, il s’agit de l’option de mise à niveau par défaut de votre organisation. Lorsque vous affectez une licence Microsoft 365 ou Office 365, les licences équipes et Skype entreprise Online sont affectées par défaut. <sup>2</sup>

Pour que cette méthode fonctionne efficacement, tous les utilisateurs doivent exécuter les deux clients simultanément. Les discussions et les appels entrants au sein de l’organisation à un utilisateur en mode d’îlot peuvent débarquer dans le client Skype entreprise ou équipes, et ce n’est pas le contrôle du destinataire. Tout dépend du client utilisé par l’expéditeur pour initier la communication. Si l’expéditeur et le destinataire se trouvent dans différentes organisations, les appels et les discussions entrants à un utilisateur en mode îlot sont toujours terrains dans le client Skype entreprise.

Par exemple, si le destinataire du mode d’îlot est connecté à Skype entreprise, mais pas Teams, et qu’une personne en provient d’une équipe, le destinataire du mode îles ne verra pas le message (mais il recevra finalement un message électronique indiquant qu’il a manqué un message dans Teams). De même, si un utilisateur travaille sur Teams, mais pas sur Skype entreprise, et qu’il est adressé à un utilisateur de Skype entreprise, il ne verra pas la discussion. Le comportement dans chacun de ces cas est similaire pour les appels. Si les utilisateurs ne sont pas en mesure d’exécuter les deux clients, ils peuvent facilement susciter votre frustration.

La présence fonctionne également indépendamment entre teams et Skype entreprise à l’aide de cette méthode de mise à niveau. Cela signifie que d’autres utilisateurs peuvent voir des États de présence différents pour l’utilisateur A, en fonction du client qu’il utilise. Pour en savoir plus, voir [présence](upgrade-to-Teams-on-prem-overview.md#presence).

- Les autres utilisateurs, lors de l’utilisation d’équipes, verront leur présence en fonction de l’activité de l’utilisateur dans Teams.

- Les autres utilisateurs, lors de l’utilisation de Skype entreprise, verront leur présence en fonction de l’activité de l’utilisateur A dans Skype entreprise.

Lorsque vous êtes prêt à mettre à niveau les utilisateurs vers le mode TeamsOnly, vous pouvez mettre à niveau les utilisateurs individuellement ou procéder à la mise à niveau de tout le client à la fois à l’aide de la stratégie utilisateur<sup>3</sup>à l’échelle du client. Une fois qu’un utilisateur a procédé à la mise à niveau vers le mode TeamsOnly, il reçoit toutes les discussions et les appels entrants dans Teams.

Toutefois, les destinataires non mis à niveau en mode îlot peuvent continuer à recevoir des conversations et des appels de la part d’un utilisateur TeamsOnly dans leurs clients Skype entreprise ou équipes. Pour les conversations existantes, l’utilisateur TeamsOnly répond au client auquel l’expéditeur a lancé la discussion ou un appel à partir de. 

En ce qui concerne les nouvelles conversations du point de vue de l’utilisateur TeamsOnly, l’appel ou la conversation s’affiche toujours sur le client du mode îlot utilisateurs Teams. En effet, le client teams gère des threads de conversation distinctes pour la communication équipes-à---------Skype entreprise, même pour le même utilisateur. Pour en savoir plus, reportez-vous à la section [conversations en équipe-interopérabilité et threads natifs](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads)

Le tableau suivant résume l’interface du mode de travail de l’équipe et du mode TeamsOnly :

| Expertise dans teams | En mode îlot | En mode TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Discussions entrantes et appels reçus dans :|  Teams ou Skype entreprise | Équipes |
| Appels RTC reçus dans : | Skype Entreprise <br>(L’utilisation de la fonctionnalité RTC dans teams n’est pas prise en charge en mode îlot.)     | Équipes |   
 |Présence    | La présence dans Skype entreprise et équipes est indépendante. Les utilisateurs peuvent voir des États différents pour les mêmes utilisateurs d’îlot, en fonction du client qu’ils utilisent. | La présence est basée uniquement sur l’activité de l’utilisateur dans Teams. Tous les autres utilisateurs, quel que soit le client qu’ils utilisent, voient leur présence. | 
 | Planification de réunions    | Les utilisateurs peuvent planifier des réunions dans teams ou Skype entreprise. Par défaut, les deux compléments s’afficheront dans Outlook. Vous pouvez définir une stratégie de réunion teams pour contrôler si les utilisateurs peuvent uniquement utiliser le complément de réunion équipes ou les compléments réunion Skype entreprise et réunion en équipe. Pour en savoir plus, consultez [la rubrique définir le fournisseur de réunion pour les utilisateurs en mode îlot](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode). |     Les utilisateurs planifient uniquement les réunions dans Teams. Le complément équipes n’est disponible que dans Outlook. | 

Le tableau suivant récapitule les avantages et inconvénients de l’utilisation de la méthode de superposition de capacités pour migrer votre organisation vers Teams.

| Spécialistes     |       Argument |
| :------------------ | :---------------- |
| Autorise une adoption rapide au sein d’une organisation.| Potentiel pour la confusion des utilisateurs finaux, car il existe deux clients dotés de fonctionnalités similaires, mais différentes interfaces utilisateur. Par ailleurs, ils n’ont aucun contrôle sur le client sur lequel les discussions/appels entrants sont débarqués. |
| Permet aux utilisateurs de se familiariser avec les équipes tout en possédant un accès complet à Skype entreprise. | Potentiel pour une insatisfaction de l’utilisateur final en raison de messages manqués si l’utilisateur n’exécute pas les deux clients.|
| Effort d’administration minimal pour la mise en route dans Teams. | Il peut être difficile de « sortir du mode îlot » et de basculer vers le mode TeamsOnly si les utilisateurs et les personnes avec lesquelles ils communiquent régulièrement n’utilisent pas activement Teams.|
|Permet aux utilisateurs d’utiliser des fonctionnalités pour améliorer le travail d’équipe qui ne sont pas disponibles dans Skype entreprise.| Les utilisateurs de Skype entreprise sur site et équipes ne seront pas en mesure de communiquer avec un utilisateur de Skype entreprise sur site, mais ne dispose pas d’équipes.  |

<sup>2</sup> c’est vrai même si l’utilisateur est hébergé sur site dans Skype entreprise Server. Que l’utilisateur réside en local ou en ligne, laissez la licence Skype entreprise Online activée, car elle est actuellement requise pour les fonctionnalités complètes d’équipes.

<sup>3</sup> Notez que la migration des réunions Skype entreprise vers des réunions teams est déclenchée uniquement lors de l’application de TeamsUpgradePolicy à des utilisateurs individuels, et non au niveau de chaque client. Pour plus d’informations, voir migration de la [réunion](upgrade-to-Teams-on-prem-overview.md#meeting-migration) .

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Sélectionner une méthode de fonctions (à l’aide du mode Skype entreprise)

Certaines organisations peuvent proposer à leurs utilisateurs finaux une plus grande prédiction de la transition de Skype entreprise à Teams. Dans ce modèle, les administrateurs informatiques ont recours à l’un des modes Skype entreprise de TeamsUpgradePolicy pour désigner explicitement les fonctionnalités qui restent dans Skype entreprise avant de procéder à la migration vers le mode TeamsOnly. Étant donné qu’ils sont prêts à décaler les fonctions sélectionnées vers le mode TeamsOnly, l’administrateur met à jour le mode de ces utilisateurs pour qu’ils TeamsOnly. Lors de cette transition :

- Les administrateurs ont la possibilité d’offrir certaines fonctionnalités d’équipe aux utilisateurs, tout en conservant leurs fonctions de discussion et d’appels dans Skype entreprise, avant que les utilisateurs ne migrent vers l’interface TeamsOnly. L’administration peut activer les fonctionnalités de collaboration d’équipes ou les réunions teams + capacités de collaboration.

- Les utilisateurs de Skype entreprise reçoivent toutes les discussions et les appels entrants dans leur client Skype entreprise, que la communication provient de l’équipe ou du client Skype entreprise. Par ailleurs, pour ces utilisateurs Skype entreprise, les fonctionnalités d’appel et de discussion dans le client teams sont désactivées pour éviter toute confusion et garantir le routage et la présence appropriés.

- Les utilisateurs en mode TeamsOnly reçoivent toutes les discussions et les appels entrants dans le client équipes et la présence est assurée par Teams, quel que soit le lieu d’origine de la communication : Teams, Skype entreprise ou tout type d’utilisateur fédéré.

Contrairement à la méthode de superposition des capacités, dans la méthode sélectionner des fonctionnalités, les utilisateurs de Skype entreprise peuvent communiquer avec des utilisateurs dans TeamsOnly. La communication entre un utilisateur de Skype entreprise et des équipes est appelée [interopérabilité](upgrade-to-Teams-on-prem-overview.md#interoperability) ou « interopérabilité ». La communication d’interopérabilité est possible sur une base un-à-un pour les conversations et les appels entre un utilisateur dans Skype entreprise et un autre utilisateur dans Teams. De plus, les utilisateurs invités peuvent toujours participer à une réunion Skype entreprise ou Teams, mais ils doivent utiliser un client correspondant au type de réunion. Pour plus d’informations, reportez-vous à la section [réunions](upgrade-to-Teams-on-prem-overview.md#meetings).

Pour les utilisateurs ayant procédé à une sélection de fonctionnalités, la présence d’un utilisateur est cohérente quel que soit le client utilisé par l’autre utilisateur. Si l’utilisateur se trouve dans l’un des modes Skype entreprise, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Skype entreprise. De même, si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Teams. Pour plus d’informations, voir [présence](upgrade-to-Teams-on-prem-overview.md#presence).

Dans le cas d’une organisation qui a choisi de suivre la méthode sélectionner des capacités, l’administrateur doit changer le mode de travail à l’échelle du client de îles en le mode de coexistence Skype entreprise approprié (SfbWithTeamsCollab ou SfBWithTeamsCollabAndMeetings).  

Le mode de coexistence attribué au client est destiné aux utilisateurs invités. Si vous définissez un mode Skype entreprise au niveau du client, les invités ne peuvent pas discuter, appeler ou montrer leur présence. Pour plus d’informations, lisez [Accès invité dans Teams](guest-access.md).

Lorsque le mode passe d’îlot à SfbWithTeamsCollab, un utilisateur qui ne les utilise jamais n’aura pas de différence dans la façon dont il utilise Skype entreprise. Toutefois, si l’utilisateur commence à utiliser Teams, il ne serait exposé qu’aux fonctionnalités telles que les équipes & le canal et les fichiers. Les discussions, les appels et la planification de réunions ne seront pas disponibles dans Teams, dans la mesure où l’administrateur dispose de Skype entreprise (pour le moment) pour ces fonctions.

> [!NOTE]
> Lorsque l’utilisateur passe d’îlot à l’un des modes Skype entreprise, le client teams de tout autre utilisateur qui communique avec l’utilisateur A doit savoir que le mode de l’utilisateur a changé de sorte qu’il puisse diriger la communication vers le client approprié pour l’utilisateur A. Pour tous les utilisateurs qui ont déjà établi des discussions d’équipes ou d’équipes natives avec l’utilisateur A, il peut être utile de tenir compte du changement du mode de ses îles sur n’importe quel mode Skype entreprise. Lorsque les administrateurs sont prêts, ils peuvent passer des conversations, des appels et une planification de réunion pour un utilisateur donné aux équipes en une seule fois en mettant à jour le mode de l’utilisateur sur TeamsOnly.

Par ailleurs, l’administrateur peut commencer par changer uniquement la planification des réunions en équipes, tout en laissant les fonctions de conversation et d’appel dans Skype entreprise à l’aide du mode SfBWithTeamsCollabAndMeetings. Ce mode permet aux organisations de basculer vers teams pour les réunions, si les utilisateurs ne sont pas encore prêts à migrer vers le mode TeamsOnly (par exemple, vous n’êtes pas encore prêt à migrer la fonctionnalité RTC existante). Ce scénario de transition est appelé d' [abord réunions](meetings-first.md).


|Expertise dans teams  |En mode SfBWithTeamsCollab |En mode SfBWithTeamsCollabAndMeetings |En mode TeamsOnly  |
|---------|---------|---------|---------|
|Les discussions entrantes et les appels VOIP des utilisateurs de votre organisation ont reçu :     | Skype Entreprise        | Skype Entreprise       | Teams        |
|Appels RTC reçus dans :     | Skype Entreprise        |Skype Entreprise         | Teams        |
|Présence     | Skype Entreprise        |Skype Entreprise         | Teams        |
|Planification de réunions     | Skype Entreprise         | Teams        | Teams        |


Le tableau suivant récapitule les avantages et inconvénients de l’utilisation du mode Skype entreprise comme étape de transition vers le mode TeamsOnly.

| Spécialistes     |       Argument |
| :------------------ | :---------------- |
| Routage prévisible pour l’utilisateur final. Tous les appels et messages instantanés dans Skype entreprise ou équipes (mais pas les deux), en fonction de la sélection de l’administrateur.|Les conversations d’interopérabilité ne prennent pas en charge le texte enrichi, le partage de fichiers et le partage d’écran. Pour cela, vous pouvez tirer parti de la fonctionnalité Conférence maintenant pour lancer une réunion. |
|Peut réduire la confusion des utilisateurs finaux, car une fonctionnalité donnée est disponible uniquement dans un client. | Les utilisateurs n’ont pas accès à teams pour les activités courantes effectuées dans Skype entreprise, telles que les discussions et les appels avant la mise à niveau vers TeamsOnly.|
|L’administrateur a renforcé le contrôle sur l’ensemble des fonctionnalités disponibles pour les utilisateurs lors de la transition de Skype entreprise à Teams. | |
| Permet à une organisation d’utiliser des équipes pour les réunions, même si elle n’est pas encore prête pour le passage entièrement au mode TeamsOnly.||
|Le statut de présence d’un utilisateur donné affiché par les autres est le même quel que soit le client qu’il utilise.||

## <a name="summary-of-upgrade-methods"></a>Résumé des méthodes de mise à niveau
Le tableau suivant récapitule les méthodes de mise à niveau :


|Fonctionnalités qui se chevauchent (à l’aide du mode îlot)  |Fonctions sélectionnées (utilisation du mode Skype entreprise)  |
|---------|---------|
|Avant la mise à niveau vers TeamsOnly, les utilisateurs doivent exécuter les deux clients simultanément, dans la mesure où les conversations et les appels entrants peuvent débarquer dans l’un ou l’autre client.     | Discussions et appels uniquement terrestres d’un client, en fonction du mode du destinataire. Les utilisateurs non mis à niveau peuvent exécuter les deux clients, mais il n’y a pas de chevauchement fonctionnel (les appels et les discussions ne sont pas disponibles dans Teams).         |
|Permet aux administrateurs d’introduire des fonctionnalités qui se chevauchent (discussions, réunions, appels VOIP) dans Skype entreprise et équipes aux utilisateurs finaux ainsi que de nouvelles fonctionnalités (équipes et canaux) dans Teams.     | Permet aux administrateurs d’introduire une fonctionnalité de sélection d’équipes pour les utilisateurs finaux (équipes et canaux), sans proposer de fonctionnalités similaires à celles de Skype entreprise.        |
|L’interopérabilité entre Skype entreprise et équipes n’existe pas tant que les deux utilisateurs sont en mode îlot.      |L’interopérabilité est requis pour la communication entre les utilisateurs de Skype entreprise et Teams.         |

> [!NOTE]
> Si vous ne parvenez pas à suivre les méthodes prises en charge pour migrer vos utilisateurs de Skype entreprise Server vers Teams, il est possible de faire basculer vos utilisateurs vers teams en supprimant Skype entreprise Server et tous les attributs d’utilisateur associés dans Active Directory. Une fois que les attributs Azure Active Directory de l’utilisateur ont été désactivés, les attributs de serveur et les enregistrements DNS de Skype entreprise ont été redirigés vers Microsoft 365 ou Office 365, il est possible que les utilisateurs disposent de licences dans Microsoft 365 ou Office 365 et de les mettre à niveau de teams. 

> [!IMPORTANT]
> Avec la migration à basculement, les données de contact et les données de réunions ne seront pas déplacées de l’environnement local vers Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quelle est la fréquence de mise à niveau adaptée aux besoins de votre organisation ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Étape suivante</td><td><ul> L’identification de votre modèle de déploiement actuel, des scénarios d’utilisation et des principales considérations relatives à votre organisation informeront les équipes qui sont les plus adaptées à votre organisation.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quels sont les scénarios de mise à niveau applicables à votre organisation ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul> Déterminez la chronologie de la mise à niveau de votre organisation sur la base de la messagerie, des réunions et des besoins de l’entreprise.<br><br> Déterminez le fonctionnement supplémentaire requis pour terminer la mise à niveau.<br><br></ul></td></tr>
</table>

Une fois que vous avez choisi le meilleur niveau de mise à niveau pour votre organisation, [effectuez la mise à niveau vers teams](https://aka.ms/SkypeToTeams-Upgrade).
