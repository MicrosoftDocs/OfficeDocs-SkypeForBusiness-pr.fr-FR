---
title: Choisissez votre voyage de mise à niveau de Skype Entreprise à Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Détails des Skype Entreprise des Microsoft Teams de coexistence, et des voyages de mise à niveau possibles vers des Teams, avec des exemples de scénarios.
ms.localizationpriority: medium
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
ms.openlocfilehash: 11644e527338e4c37056071893c3d3ad735253f0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733703"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Choisissez votre voyage de mise à niveau de Skype Entreprise à Teams

![Diagramme de voyage de mise à niveau mettant en relief la Project phase Définition.](media/upgrade-banner-project-definition.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la Project phase Définition")

Cet article fait partie de la phase Project de votre parcours vers la mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

En tant que client Skype Entreprise client, la transition complète vers Teams peut prendre un certain temps. Toutefois, vous pouvez commencer à réaliser la valeur d Teams aujourd’hui, en permettant à vos utilisateurs d’utiliser des Teams en parallèle Skype Entreprise. Étant donné que les fonctionnalités qui se chevauchent entre les deux applications se chevauchent, nous vous recommandons de passer en revue les modes de coexistence et de mise à niveau disponibles pour déterminer le chemin le plus exact pour votre organisation. Par exemple, vous pouvez choisir d’activer toutes les charges de travail sur les deux solutions sans interopérabilité. Vous pouvez également décider de gérer l’expérience utilisateur, soit en introduisant progressivement des fonctionnalités de Teams, soit en ciblant des groupes d’utilisateurs pour des fonctionnalités sélectionnées, jusqu’à ce que votre organisation soit prête à mettre à niveau tout le monde vers Teams. Utilisez les résultats de votre pilote pour évaluer le chemin de mise à niveau souhaité pour votre organisation.

> [!IMPORTANT]
> Skype Entreprise Online sera supprimé le 31 juillet 2021. Après cette date, il ne sera plus accessible ni pris en charge. Pour optimiser l’utilisation des avantages et vous assurer que votre organisation dispose du temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre chemin vers Microsoft Teams aujourd’hui.

Cet article décrit les différents modes qui vous permettent de gérer les différentes qualités de Skype Entreprise et Teams disponibles pour vos utilisateurs. Comme pour tout déploiement, nous vous encourageons vivement à piloter votre [plan](pilot-essentials.md) prévu avec un groupe d’utilisateurs sélectionné avant de mettre à niveau votre organisation vers Teams. N’oubliez pas que l’introduction d’une nouvelle technologie peut perturber les utilisateurs. Prenez le temps d’évaluer la disponibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter l’un des modes décrits ici.

> [!TIP]
> Rejoignez-nous pour des ateliers interactifs en direct où nous partagerons des recommandations, des pratiques et des ressources destinées à démarrer la planification et l’implémentation de la mise à niveau.
>
>Participez à la session de mise [à](./upgrade-workshops-landing-page.yml) niveau pour commencer.


## <a name="upgrade-journey-building-blocks"></a>Blocs de construction de voyage de mise à niveau

Pour préparer officiellement votre organisation pour son parcours vers Teams, vous devez commencer à planifier les scénarios de mise à niveau qui finiront par laisser votre organisation adopter entièrement les Teams comme solution de communication et de collaboration.

Pour vous aider à guider votre processus de prise de décision, familiarisez-vous avec les différents modes, concepts et termes pertinents pour la mise à niveau d’Skype Entreprise vers Teams. Pour plus d’informations, [voir Microsoft Teams et Skype Entreprise coexistence et l’interopérabilité.](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> Vous devrez également envisager vos scénarios de migration vocale. Système téléphonique est la technologie de Microsoft qui permet d’activer le contrôle d’appel et les fonctionnalités de Exchange de branche privée (PBX) dans le cloud Microsoft 365 ou Office 365. Pour vous Système téléphonique au réseau téléphonique public commuté (PSTN) afin que les utilisateurs peuvent passer des appels téléphoniques dans le monde entier, vous avez accès à des options en fonction de vos besoins professionnels. Pour plus d’informations sur les options Système téléphonique et de connectivité PSTN, voir Voice - Système téléphonique et Connectivité [PSTN.](cloud-voice-landing-page.md)

Un utilisateur qui a été migré vers Teams n’utilise plus un client Skype Entreprise sauf pour participer à une réunion hébergée dans Skype Entreprise. Toutes les conversations et appels entrants arrivent dans le client de messagerie Teams de l’utilisateur, que l’expéditeur utilise Teams ou Skype Entreprise. Toute nouvelle réunion organisée par l’utilisateur mis à niveau sera Teams réunions. Si l’utilisateur tente d’utiliser le client Skype Entreprise, le démarrage de conversations et d’appels est bloqué<sup>1.</sup> Toutefois, l’utilisateur peut (et doit) continuer à utiliser Skype Entreprise client pour participer aux réunions à qui il est invité.

Les administrateurs gèrent leur transition vers Teams en utilisant le concept de [mode,](migration-interop-guidance-for-teams-with-skype.md)qui est une propriété de [TeamsUpgradePolicy.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true) Un utilisateur qui a été migré vers Teams décrit ci-dessus est en mode « TeamsOnly ». Pour une organisation qui migre vers le Teams, l’objectif ultime est de déplacer tous les utilisateurs en mode TeamsOnly.

Il existe deux méthodes pour migrer une organisation existante avec des Skype Entreprise (en ligne ou en local) vers un réseau Teams :

- Méthode des fonctionnalités superposées **(à** l’aide du mode Îles) : les utilisateurs d’une organisation Skype Entreprise existante sont introduits dans Teams de sorte qu’ils peuvent utiliser les deux clients côte à côte lors d’une phase de transition. Pendant cette période, la plupart des fonctionnalités de Teams fonctionnalités sont disponibles. Le mode pour cette configuration est appelé Îles, et il s’agit du mode par défaut pour toute organisation existante ayant Skype Entreprise. Une fois que l’organisation est prête, l’administrateur déplace les utilisateurs en mode TeamsOnly.

- Méthode De sélection des fonctionnalités **(à** l’aide d’un ou plusieurs modes de Skype Entreprise) : l’administrateur gère la transition (de Skype Entreprise à Teams) des fonctionnalités de conversation, d’appel et de planification de réunion pour les utilisateurs de leur organisation. Chacune de ces fonctions est disponible dans Skype Entreprise ou Teams, mais pas les deux. Les administrateurs utilisent TeamsUpgradePolicy pour contrôler quand déplacer cette fonctionnalité vers Teams pour leurs utilisateurs. Les utilisateurs qui ne sont pas encore en mode TeamsOnly continuent d’utiliser Skype Entreprise pour les discussions et les appels, et les deux ensembles d’utilisateurs peuvent communiquer via les fonctionnalités interop. Les administrateurs gèrent la transition en migrant progressivement d’autres utilisateurs en mode TeamsOnly.

<sup>1 Les</sup> clients Skype Entreprise plus anciens qui ont été expédiés avant 2017 n’honorent pas TeamsUpgradePolicy. Assurez-vous d’utiliser la dernière version Skype Entreprise client disponible dans votre Office canal.

Une fois que vous avez compris et choisi votre méthode de mise à niveau, vous pouvez en savoir plus sur les outils de gestion de la mise à niveau vers [Teams.](upgrade-to-teams-on-prem-tools.md)

Vous trouverez ci-dessous les principaux facteurs qui vous aideront à déterminer le chemin approprié pour votre organisation.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Méthode des capacités superposées (à l’aide du mode Îles)

Grâce à la méthode des fonctionnalités qui se chevauchent, les utilisateurs peuvent utiliser à la fois des clients Teams et Skype Entreprise pour les discussions instantanées, les appels VoIP et les réunions. Dans cette méthode, la conversation et les appels VOIP dans Teams sont axées sur l’organisation, tandis que Skype Entreprise active la conversation et les appels VOIP/PSTN avec les organisations externes (si configurées). Les réunions peuvent être programmées et participées dans les deux produits.

Lorsque vous utilisez la méthode des fonctionnalités superposées, le trafic des communications pour Skype Entreprise et Teams reste distinct (même pour le même utilisateur) et les deux clients ne communiquent jamais entre eux (pour les utilisateurs au sein de la même organisation). Les expériences utilisateur sont basées sur la configuration du destinataire. Par exemple, supposons que l’utilisateur A du destinataire soit en mode Îles :

- Les communications initiées par le client d’Skype Entreprise d’un autre utilisateur seront toujours propriétés dans le client Skype Entreprise utilisateur A.

- Les communications initiées par le  client Teams d’un utilisateur de la même organisation seront toujours propriétés dans le client Teams utilisateur A.

- Les communications initiées par Teams client d’un utilisateur dans une *organisation* externe seront toujours propriétés dans le client Skype Entreprise utilisateur A.

Si vous avez attribué Microsoft 365 ou Office 365 licence aux utilisateurs, il s’agit de l’expérience de mise à niveau par défaut pour votre organisation. Lorsque vous affectez une licence Microsoft 365 ou Office 365, les licences Teams et Skype Entreprise Online sont affectées par défaut. <sup>2</sup>

Pour que cette méthode fonctionne efficacement, tous les utilisateurs doivent exécuter les deux clients simultanément. Les conversations et appels entrants, au sein de l’organisation, à un utilisateur en mode Îles peuvent se trouver dans le client Skype Entreprise ou Teams, et ce n’est pas sous le contrôle du destinataire. Cela dépend du client utilisé par l’expéditeur pour démarrer la communication. Si l’expéditeur et le destinataire sont dans différentes organisations, les appels et conversations entrants avec un utilisateur en mode Îles arrivent toujours dans le client Skype Entreprise messagerie.

Par exemple, si un destinataire en mode Îles est inscrit à Skype Entreprise mais pas à Teams et qu’un destinataire le envoie depuis Teams, le destinataire du mode Îles ne verra pas le message (mais il recevra un e-mail lui disant qu’il a manqué un message dans Teams). De même, si un utilisateur exécute Teams mais pas Skype Entreprise et un message provenant d’un utilisateur provenant d’Skype Entreprise, il ne verra pas cette conversation. Dans chacun de ces cas, le comportement est similaire pour les appels. Si les utilisateurs n’exécutent pas les deux clients, cela peut facilement entraîner de la frustration.

La présence fonctionne également indépendamment entre les niveaux Teams et Skype Entreprise lorsque vous utilisez cette méthode de mise à niveau. Cela signifie que les autres utilisateurs peuvent voir des états de présence différents pour l’utilisateur A, selon le client qu’ils utilisent. Pour plus d’informations, voir [Présence.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

- Les autres utilisateurs, lors de l’Teams, voient les informations de présence en fonction de l’activité de l’utilisateur A dans Teams.

- Les autres utilisateurs, lors de Skype Entreprise, voient les informations de présence en fonction de l’activité de l’utilisateur A dans Skype Entreprise.

Lorsque vous êtes prêt à mettre à niveau les utilisateurs vers le mode TeamsOnly, vous pouvez mettre à niveau les utilisateurs individuellement ou mettre à niveau l’ensemble du client en une seule fois à l’aide de la stratégie 3 à l’échelle du<sup>client.</sup> Une fois qu’un utilisateur est mis à niveau en mode TeamsOnly, il reçoit toutes les conversations et appels entrants en Teams. (Notez que la migration de réunions Skype Entreprise vers des réunions Teams est déclenchée uniquement lors de l’application de TeamsUpgradePolicy à des utilisateurs individuels, et non pas par client. Pour [plus d’informations,](upgrade-to-teams-on-prem-tools.md#meeting-migration) voir Migration de réunion.)

Toutefois, les destinataires non mis à niveau en mode Îles peuvent continuer à recevoir des conversations et des appels d’un utilisateur TeamsOnly dans ses clients Skype Entreprise ou Teams messagerie. Pour les conversations existantes, l’utilisateur TeamsOnly répondra au client à partir de qui l’expéditeur a initié la conversation ou l’appel. 

Pour les nouvelles conversations à partir du point de vue de l’utilisateur de TeamsOnly, la conversation ou l’appel passe toujours aux utilisateurs du mode Teams client. En effet, le client Teams conserve des threads de conversation distincts pour les communications de Teams à Teams et de Teams à Skype Entreprise, même pour le même utilisateur. Pour en savoir plus, voir [Teams conversations - Interop ou threads natifs.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

Le tableau suivant récapitule l’expérience de Teams pour le mode Islands et le mode TeamsOnly :

| Teams expérience utilisateur | En mode Îles | En mode TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Conversations et appels entrants reçus dans :|  Teams ou Skype Entreprise | Équipes |
| Appels PSTN reçus dans : | Skype Entreprise <br>(L’utilisation de la fonctionnalité PSTN dans Teams n’est pas prise en charge en mode Îles.)     | Équipes |   
 |Présence    | La présence au Skype Entreprise et Teams est indépendante. Les utilisateurs peuvent voir des états différents pour le même utilisateur des îles, selon le client qu’ils utilisent. | La présence est basée uniquement sur l’activité de l’utilisateur dans Teams. Tous les autres utilisateurs, quel que soit le client qu’ils utilisent, voient cette présence. | 
 | Planification de réunions    | Les utilisateurs peuvent planifier des réunions à l’Teams ou Skype Entreprise. Par défaut, ils voient les deux Outlook. Vous pouvez définir une stratégie de réunion Teams pour contrôler si les utilisateurs peuvent uniquement utiliser le Teams Meeting add-in ou les deux au niveau des modules Teams Meeting et Skype Entreprise Meeting. Pour en savoir plus, voir définir le fournisseur de réunion [des utilisateurs en mode Îles.](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode) |     Les utilisateurs ne peuvent planifier des réunions que Teams. Seul le Teams de groupe est disponible dans Outlook. | 

Le tableau suivant récapitule les avantages et les inconvénients de l’utilisation de la méthode des fonctionnalités de chevauchement pour migrer votre organisation vers Teams.

| Professionnels     |       Inconvénients |
| :------------------ | :---------------- |
| Permet une adoption rapide au sein d’une organisation.| Risque de confusion chez les utilisateurs finaux, car deux clients ont des fonctionnalités similaires, mais des interfaces utilisateur différentes. En outre, ils n’ont aucun contrôle sur le client auquel les conversations/appels entrants arrivent. |
| Permet aux utilisateurs d’apprendre et de se familiariser avec Teams tout en ayant un accès total à Skype Entreprise. | Insatisfaction potentielle de l’utilisateur final suite à l’insatisfaction des messages manqués si l’utilisateur n’exécute pas les deux clients.|
| Minimum d’efforts d’administration pour commencer à Teams. | Il peut être difficile de « sortir des îles » et de passer en mode TeamsOnly si les utilisateurs et ceux avec qui ils communiquent régulièrement ne font pas activement appel à Teams. Par exemple, une fois qu’un sous-ensemble d’utilisateurs est mis à niveau en mode TeamsOnly, ces utilisateurs les envoient uniquement dans Teams. Pour le reste de la population en mode Îles, ces messages sont toujours reçus en Teams. Mais si une partie de cette population ne fonctionne pas Teams, elle aura l’impression que ces messages sont manqués.|
|Permet aux utilisateurs de tirer parti de fonctionnalités permettant d’améliorer le travail d’équipe qui ne sont pas disponibles dans Skype Entreprise.| Un utilisateur qui utilise Skype Entreprise en local et Teams ne pourra pas communiquer à partir de Teams avec un autre utilisateur qui utilise Skype Entreprise sur site, mais n’a pas de Teams.  |
|  | Lors de l Teams, les utilisateurs qui ont un compte local dans un Skype Entreprise Server ne peuvent pas prendre en charge Interop ou de fédération.  Cela peut potentiellement semer la confusion si vous avez un mélange d’utilisateurs d’îles (certains d’entre eux nt domicile dans Skype Entreprise Online et d’autres Skype Entreprise sur site.   |

<sup>2</sup> C’est vrai même si l’utilisateur est homed sur site dans Skype Entreprise Server. Que l’utilisateur soit homed local ou en ligne, laissez la licence Skype Entreprise Online activée, car elle est actuellement nécessaire pour utiliser toutes les fonctionnalités Teams web.

<sup>3</sup> Notez que la migration de réunions Skype Entreprise vers des réunions Teams est déclenchée uniquement lors de l’application de TeamsUpgradePolicy à des utilisateurs individuels, et non pas par client. Pour plus [d’informations,](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) voir Migration de réunion.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Sélectionner la méthode des fonctionnalités (à l’Skype Entreprise mode d’affichage)

Certaines organisations préféreront peut-être offrir à leurs utilisateurs finaux une expérience plus prévisible au cours de la transition de leur organisation Skype Entreprise vers Teams. Dans ce modèle, les administrateurs informatiques utilisent l’un des modes Skype Entreprise de TeamsUpgradePolicy pour désigner explicitement les fonctionnalités qui restent dans Skype Entreprise avant la migration vers le mode TeamsOnly. Étant prêt à déplacer les fonctionnalités sélectionnées en mode TeamsOnly, l’administrateur met à jour le mode pour ces utilisateurs vers TeamsOnly. Au cours de cette transition :

- Les administrateurs ont des options pour activer certaines fonctionnalités de Teams pour les utilisateurs tout en conservant les fonctionnalités de conversation et d’appel dans Skype Entreprise avant que les utilisateurs ne passeront à l’expérience TeamsOnly. L’administration peut activer Teams de collaboration ou Teams réunions et de collaboration.

- Les utilisateurs toujours sur Skype Entreprise reçoivent toutes les conversations et appels entrants dans leur client Skype Entreprise, que la communication provienne du client Teams ou du client Skype Entreprise de l’autre utilisateur. De plus, pour ces Skype Entreprise utilisateurs, les fonctionnalités d’appel et de conversation sont désactivées dans le client Teams afin d’éviter toute confusion chez les utilisateurs finaux et de garantir un routage et une présence appropriés.

- Les utilisateurs en mode TeamsOnly reçoivent toutes les conversations et appels entrants dans leur client Teams et la présence est fournie par Teams, quelle que soit l’origine de la communication : Teams, Skype Entreprise ou tout type d’utilisateur fédéré.

Contrairement à la méthode des fonctionnalités superposées (Islands), dans la méthode de sélection des fonctionnalités, les utilisateurs qui utilisent Skype Entreprise peuvent communiquer avec les utilisateurs de TeamsOnly. La communication entre un Skype Entreprise utilisateur et Teams’utilisateur est appelée [interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) ou « interop ». La communication Interop est possible pour des conversations et des appels entre un utilisateur du Skype Entreprise et un autre utilisateur Teams. En outre, les utilisateurs invités peuvent toujours participer à une réunion Skype Entreprise ou Teams, toutefois, ils doivent utiliser un client correspondant au type de réunion. Pour plus d’informations, [voir Réunions.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)

Pour les utilisateurs d’une méthode de transition de fonctionnalités sélectionnées, la présence d’un utilisateur est cohérente quel que soit le client utilisé par l’autre utilisateur. Si l’utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient la présence en fonction de l’activité de cet utilisateur dans Skype Entreprise. De même, si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence en fonction de l’activité de cet utilisateur dans Teams. Pour plus d’informations, [consultez Présence.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

Pour une organisation qui n’a pas encore commencé à utiliser Teams, l’administrateur doit changer le mode à l’échelle du client d’Islands à SfbWithTeamsCollab. (Pour les organisations qui ont déjà une Teams d’utilisation, l’administrateur doit « inexer » les utilisateurs déjà actifs dans Teams pour s’assurer que cette modification ne s’applique pas à eux. Pour plus d’informations, consultez une méthode de sélection des fonctionnalités pour une organisation qui utilise déjà [Teams en mode Îles.)](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode) 

L’expérience des utilisateurs des invités respecte le mode de coexistence qui est attribué au client. Si vous définissez un mode Skype Entreprise client, les invités ne peuvent pas discuter, appeler ou afficher leur présence. Pour plus d’informations, lisez [Accès invité dans Teams](guest-access.md).

Lorsque le mode passe d’Islands à SfbWithTeamsCollab, un utilisateur qui n’a jamais utilisé Teams ne voit aucune différence dans sa façon d’Skype Entreprise. Toutefois, si cet utilisateur commence à utiliser Teams, il sera exposé uniquement à des fonctionnalités telles que Teams & Channel et Files. Les fonctionnalités de conversation, d’appel et de planification de réunions ne sont pas disponibles dans Teams, car l’administrateur a (pour l’instant) désigné Skype Entreprise comme client souhaité pour ces fonctions.

> [!NOTE]
> Lorsque l’utilisateur A passe d’Îles à l’un des modes Skype Entreprise, le client Teams d’un autre utilisateur qui communique avec l’utilisateur A doit savoir que le mode de l’utilisateur A a changé pour pouvoir router la communication vers le client approprié pour l’utilisateur A. Pour les utilisateurs qui ont déjà établi des conversations Teams-à-Teams natives avec l’utilisateur A, jusqu’à 36 heures peuvent être avant que les clients Teams de ces autres utilisateurs sachent que le mode passe d’Islands à n’importe quel mode Skype Entreprise. En revanche, les modifications apportées au mode TeamsOnly d’un utilisateur existant sont découvertes par d’autres clients dans les 2 heures.<br>
> Lorsque les administrateurs sont prêts, ils peuvent modifier la conversation, les appels et la planification de réunions pour un utilisateur donné pour Teams en mettant à jour le mode de l’utilisateur sur TeamsOnly.

Par alternative, l’administrateur peut tout d’abord déplacer la planification des réunions uniquement vers Teams, tout en laissant les fonctions de conversation et d’appel dans Skype Entreprise à l’aide du mode SfBWithTeamsCollabAndMeetings. Ce mode permet aux organisations de passer à des Teams pour les réunions, si les utilisateurs ne sont pas encore prêts à passer en mode TeamsOnly (par exemple, si vous n’êtes pas encore prêt à migrer les fonctionnalités PSTN existantes). Ce scénario d’urgence est appelé [Réunions en premier.](meetings-first.md)


|Teams expérience utilisateur  |En mode SfBWithTeamsCollab |En mode SfBWithTeamsCollabAndMeetings |En mode TeamsOnly  |
|---------|---------|---------|---------|
|Conversations entrantes et appels VOIP des utilisateurs de votre organisation reçus dans :     | Skype Entreprise        | Skype Entreprise       | Teams        |
|Appels PSTN reçus dans :     | Skype Entreprise        |Skype Entreprise         | Teams        |
|Présence     | Skype Entreprise        |Skype Entreprise         | Teams        |
|Planification de réunions     | Skype Entreprise         | Teams        | Teams        |


Le tableau suivant récapitule les avantages et les inconvénients de l’utilisation de modes Skype Entreprise comme étape de transition vers le mode TeamsOnly.

| Professionnels     |       Inconvénients |
| :------------------ | :---------------- |
| Routage prévisible pour l’utilisateur final. Tous les appels et conversations se Skype Entreprise ou Teams (mais pas les deux) sur la base de la sélection de l’administrateur.|Il manque à Vos conversations Interop la prise en charge du texte enrichi, du partage de fichiers et du partage d’écran. Vous pouvez contourner ce point en tirant parti de la fonctionnalité Conférence maintenant pour démarrer une réunion. |
|Peut réduire la confusion des utilisateurs, car une fonctionnalité donnée n’est disponible que dans un seul client. | Avant la mise à niveau des utilisateurs vers TeamsOnly, ils n’ont pas accès à des Teams pour les activités courantes effectuées dans Skype Entreprise telles que les discussions et les appels. Signification : aucune fonctionnalité côte à côte.|
|Un administrateur contrôle l’ensemble des fonctionnalités disponibles pour les utilisateurs lors de la transition d’Skype Entreprise à Teams. Ce contrôle permet d’introduire incrémentiellement Teams fonctionnalités. | |
| Permet à une organisation d’Teams des réunions, même si elle n’est pas encore prête à passer entièrement en mode TeamsOnly.||
|La présence d’un utilisateur donné telle qu’elle est vue par d’autres est la même, quel que soit le client qu’il utilise.||

## <a name="summary-of-upgrade-methods"></a>Résumé des méthodes de mise à niveau
Le tableau suivant récapitule les méthodes de mise à niveau :


|Capacités superposées (à l’aide du mode Îles)  |Fonctionnalités sélectionnées (à l’Skype Entreprise mode)  |
|---------|---------|
|Avant la mise à niveau vers TeamsOnly, les utilisateurs doivent exécuter les deux clients simultanément, car les conversations et appels entrants peuvent être dirigés vers l’un ou l’autre client.     | Les conversations et appels n’ont lieu que dans un seul client, selon le mode du destinataire. Les utilisateurs non mis à niveau peuvent exécuter les deux clients, mais il n’existe aucun chevauchement fonctionnel (les appels et les discussions ne sont pas disponibles dans Teams). Les administrateurs peuvent également déterminer si les utilisateurs planifierent des réunions Teams ou Skype Entreprise.         |
|Permet aux administrateurs d’introduire des fonctionnalités superposées (conversation, réunions, appels VOIP) dans Skype Entreprise et Teams pour les utilisateurs finaux (ce qui autorise les fonctionnalités côte à côte), ainsi que de nouvelles fonctionnalités (Teams et canaux) dans Teams.     | Permet aux administrateurs d’introduire la fonctionnalité de sélection d’Teams pour les utilisateurs finaux (Teams et canaux), sans fournir les mêmes fonctionnalités qu’Skype Entreprise.        |
|Interop entre les Skype Entreprise et Teams n’existe pas tant que les deux utilisateurs sont en mode Îles. Une fois que certains utilisateurs ont été mis à niveau vers la conversation Interop TeamsOnly, il se peut que ces utilisateurs et d’autres utilisateurs toujours en mode Îles soient mis à niveau. Toutefois, les utilisateurs d’îles pouvaient choisir d Teams et d’éviter la conversation interop.      |Interop est requis pour la communication entre les Skype Entreprise et Teams utilisateurs.         |

> [!NOTE]
> Si vous ne parvenez pas à suivre les méthodes de migration de vos utilisateurs Skype Entreprise Server vers Teams, il est possible de migrer vos utilisateurs vers Teams en supprimant Skype Entreprise Server et tous les attributs utilisateur associés dans Active Directory. Une fois que les attributs Azure Active Directory des utilisateurs ont été effacés des attributs Skype Entreprise Server et des enregistrements DNS ont été de nouveau pointés vers Microsoft 365 ou Office 365, il serait ensuite possible de leur attribuer une licence dans Microsoft 365 ou Office 365 et de les mettre à niveau vers Teams. 

> [!IMPORTANT]
> Avec la migration à pas de point, les données de contact et de réunions ne sont pas migrées de l’environnement local vers l’Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quel voyage de mise à niveau convient aux besoins de votre entreprise ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Étape suivante</td><td><ul> L’identification de votre modèle de déploiement actuel, des scénarios d’utilisation des cas et des considérations clés pour votre organisation vous permettra d’établir un Teams adapté à votre organisation.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quel scénario de mise à niveau est applicable à votre organisation ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul> Déterminez la chronologie du parcours de mise à niveau de votre organisation en fonction des besoins de messagerie, de réunions et d’appels pour l’entreprise.<br><br> Décidez du travail supplémentaire nécessaire pour effectuer votre voyage de mise à niveau.<br><br></ul></td></tr>
</table>

Une fois que vous avez choisi le meilleur chemin de mise à niveau pour votre organisation, [effectuez la mise](./upgrade-to-teams.md)à niveau vers Teams.

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre les Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)