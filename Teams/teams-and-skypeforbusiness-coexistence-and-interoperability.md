---
title: Comprendre Microsoft Teams coexistence et Skype Entreprise interopérabilité
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Détails des options Skype Entreprise et Microsoft Teams coexistence possibles, et interopérabilité résultante entre les deux Skype Entreprise et Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d06a49069e04b9c2bce05c0ede214f9cbd8fec12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627496"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft Teams coexistence et Skype Entreprise interopérabilité

![Mettre à niveau le diagramme de voyage, mettant en relief la Project phase Définition](media/upgrade-banner-project-definition.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la Project phase Définition")

Cet article fait partie de la Project phase Définition de votre voyage de mise à niveau. Terminé après avoir créé un équipe de financement et de projet et défini l’étendue, les objectifs et le plan de votre projet. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)

Si votre organisation utilise Skype Entreprise aujourd’hui et que vous commencerez à utiliser Teams en même temps que Skype Entreprise (ou si vous démarrez une mise à niveau vers Teams), il est important de comprendre comment les deux applications coexistent, quand et comment elles sont interopérables, et comment gérer la migration de vos utilisateurs jusqu’à leur mise à niveau fin de Skype Entreprise vers Teams.

> [!Tip]
> Regardez la session suivante pour en savoir plus [sur la coexistence et l’interopérabilité.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> En outre, vous pouvez nous rejoindre pour des ateliers interactifs en direct dans lesquels nous allons partager des conseils, des meilleures pratiques et des ressources destinées à lancer la planification et l’implémentation de la mise à niveau.
>
> Participez à la session de mise [à](./upgrade-workshops-landing-page.yml) niveau pour commencer.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Vue d’ensemble de Teams et Skype Entreprise coexistence de personnes

Les sections suivantes décrivent les modes de coexistence disponibles lorsque vous décidez d’Teams et les fonctionnalités de chaque mode. En outre, nous décrivons l’interopérabilité (interop) qui se produit entre les utilisateurs de clients Skype-for-Business et les utilisateurs sur les clients Teams, et la manière dont interop est affectée par le mode de coexistence choisi.

 Teams fonctionnalités de collaboration, de conversation, d’appel et de réunion. Selon la façon dont vous choisissez de déployer Teams, ces fonctionnalités peuvent chevaucher celles d’un Skype Entreprise d’un utilisateur donné. Le mode par défaut est d’exécuter Teams parallèlement Skype Entreprise les fonctionnalités se chevauchent. Toutefois, un utilisateur peut se voir attribuer l’un des modes de coexistence (également appelés modes de mise à niveau) conçus pour s’assurer que ces fonctionnalités ne chevauchent pas cet utilisateur (auquel cas l’interopérabilité entre Teams et Skype Entreprise est disponible). Par exemple, si vous avez des ressources Skype Entreprise Server importantes sur site avec un déploiement Voix Entreprise complexe, mais que vous souhaitez [](meetings-first.md) que vos utilisateurs profitent des réunions modernes le plus rapidement possible, vous pouvez évaluer les réunions d’abord comme alternative.

Nous vous recommandons de passer en revue les modes de coexistence suivants pour déterminer le chemin le plus exact pour votre organisation.

> [!Important]
> Les modes de coexistence continueront d’exister après la mise à la retraite d’Skype Entreprise Online le 31 juillet 2021, mais ne seront pertinents que pour les organisations ayant des déploiements locaux de Skype Entreprise Server. Juste avant la retraite, les utilisateurs homed dans le déploiement local peuvent se voir attribuer n’importe quel mode autre que TeamsOnly. Toutefois, après la mise Skype Entreprise Online, les utilisateurs qui mentent leur domicile dans le cloud peuvent uniquement utiliser TeamsOnly.

### <a name="islands-mode"></a>Mode Îles

Par défaut, les utilisateurs peuvent exécuter des Teams et Skype Entreprise deux solutions distinctes qui offrent des fonctionnalités similaires qui se chevauchent. Les fonctionnalités incluent la présence, les discussions, les appels et les réunions. Teams utilisateurs peuvent également tirer parti des nouvelles fonctionnalités de collaboration, telles que les équipes et les canaux, l’accès aux fichiers dans Microsoft 365 ou Office 365 et les applications.

Dans ce mode de coexistence appelé **Îles,** chacune des applications clientes fonctionne comme une île distincte. Skype Entreprise les négociations Skype Entreprise et Teams les négociations pour Teams. Les utilisateurs sont censés exécuter les deux clients à tout moment et peuvent communiquer en natif dans le client à partir duquel la communication a commencé. Ainsi, l’interopérabilité n’est pas nécessaire en mode **Îles.**

Pour éviter une expérience d’Skype Entreprise confusion ou de régression, le Skype Entreprise gère les intégrations suivantes qui ne sont pas gérées en mode Teams **(Îles)** :

- Communications externes (fédérées).
- Les services vocaux PSTN et les applications vocales, ainsi Office l’intégration.
- Contrôles HID pour les périphériques USB.
- Plusieurs autres intégrations.  

Système téléphonique n’est pas pris en Teams en mode **Îles.** Le mode **Îles** ne prend pas en charge Voix Entreprise client n’Skype Entreprise.

> [!Important]
> En mode **Îles,** tous les messages et appels des utilisateurs fédérés (personnes extérieures à votre organisation) sont remis à Skype Entreprise. Après la mise à **niveau vers Teams** mode Uniquement, tous les messages et appels en provenance de l’extérieur de votre organisation sont remis à Teams.

> [!Tip]
> Skype Entreprise Le chemin d’accès recommandé aux clients en ligne est de démarrer avec le **mode** Îles par défaut, d’augmenter Teams l’adoption au niveau de l’organisation, puis de passer au **mode** Teams’îles uniquement rapidement. Sur les clients locaux et hybrides, en particulier les plus complexes, il peut être avantageux de déployer Skype Entreprise avec le mode **de collaboration Teams** comme point de départ plutôt que d’avoir le mode **Îles,** et de passer de là à Skype Entreprise avec le mode Teams Collaboration et réunions (autrement dit, Réunions en premier lieu), et sur **Teams** Uniquement lorsque l’organisation est prête à adopter des Teams. 

### <a name="teams-only"></a>Teams Uniquement

Un **Teams utilisateur** (également appelé  utilisateur mis à niveau) a accès à toutes les fonctionnalités de Teams. Ils peuvent conserver le client Skype Entreprise pour participer à des réunions sur des Skype Entreprise qui ont été organisées par des utilisateurs non mis à niveau ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui utilisent toujours Skype Entreprise à l’aide des fonctionnalités d’interopérabilité entre Teams et Skype Entreprise (à condition que les utilisateurs de Skype Entreprise ne soient pas en **mode** Îles). Toutefois, un utilisateur mis à niveau ne peut pas démarrer Skype Entreprise conversation, appel ou réunion.

Dès que votre organisation est prête à utiliser Teams pour certains ou tous les utilisateurs comme seul outil de communication et de collaboration, vous pouvez mettre ces utilisateurs à niveau vers Teams **mode Uniquement.** Si vous faites une mise à niveau à partir du mode **Islands,** il est conseillé de saturer d’abord les Teams adoption dans votre organisation avant de commencer le processus de mise à niveau. Cette adoption évite les scénarios de communication rompus dus au mode **Islands** qui ne fournit pas l’interopérabilité.

En mode **Teams uniquement,** Teams est l’application par défaut pour le protocole SIP/Tel. Les liens dans la carte de visite d’un Outlook pour les appels ou les discussions seront gérés par Teams.

Pour plus d’informations sur le passage au mode **Teams’écran** uniquement, voir Teams considérations concernant [le mode Uniquement.](teams-only-mode-considerations.md)

![Capture d’écran du message Teams confirmation de la réception](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype Entreprise client en cours d’exécution dans un mode spécial après la mise à niveau de l’utilisateur en tant Teams utilisateur seul")

### <a name="skype-for-business-only"></a>Skype Entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent en Skype Entreprise (et non en Teams) pour les fonctionnalités de conversation, de réunion et d’appel, et n’utilisent pas de Teams pour les équipes et les canaux. Ce mode est disponible aujourd’hui . toutefois, dans l’implémentation actuelle, les équipes et les canaux ne sont pas désactivés automatiquement pour l’utilisateur. Pour ce faire, utilisez la stratégie de configuration d’application pour masquer les équipes et les fichiers.

Ce mode peut être utilisé avant de démarrer un déploiement géré de Teams pour empêcher les utilisateurs de commencer à utiliser Teams avant d’avoir une préparation prééance. Ce mode permet également d’activer la participation authentifiée aux réunions Teams pour les utilisateurs Skype Entreprise, à condition qu’ils soient titulaires d’une licence Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Entreprise avec Teams collaboration

Utilisez ce mode pour introduire des Teams dans votre environnement tout en continuer à utiliser votre investissement existant dans Skype Entreprise. Ne Skype Entreprise pas pour les fonctionnalités de conversation, d’appel et de réunion. Ajouter Teams fonctionnalités de collaboration :

- Teams et canaux.
- Accès aux fichiers dans Microsoft 365 ou Office 365.
- Applications. Teams fonctionnalités de communication : conversation privée, appel et planification de réunions.

Teams conversation privée, les appels et la planification de réunions sont éteints par défaut dans ce mode.

Les organisations ayant un point de départ de Skype Entreprise Server en local ou hybride doivent envisager ce **mode** comme une alternative au mode Îles si elles souhaitent offrir à leurs utilisateurs l’interopérabilité et la prévisibilité de leurs communications, ainsi qu’avoir un calendrier prévisible pour leur mise à niveau vers Teams (plutôt que de s’appuyer sur une saturation de l’adoption en **mode** Îles).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Entreprise avec Teams collaboration et réunions, également appelées Réunions en premier

Utilisez ce mode de coexistence pour accélérer la disponibilité des Teams de réunion et de collaboration dans votre organisation. Le mode de coexistence permet à vos utilisateurs de tirer parti de l’expérience Teams des réunions :

- Qualité exceptionnelle.
- Transcription et traduction.
- Effet de flou de l’arrière-plan.
- Expérience utilisateur supérieure sur toutes les plateformes, y compris les appareils mobiles et les navigateurs.

En plus de Teams pour les équipes et les canaux dans ce mode, les utilisateurs utiliseront Teams pour planifier et diriger leurs réunions. Les appels et les discussions privées restent sur Skype Entreprise. Teams et Skype Entreprise bénéficiez d’une gamme de fonctionnalités « meilleur ensemble », telles que le rapprochement des présences, la suspension/désins% automatique et la prise en charge des appareils HID dans les deux applications. Vous avez la possibilité de masquer les équipes et les canaux, si vous le souhaitez, à l’aide de la stratégie de configuration de l’application.

Ce mode de coexistence est particulièrement utile pour les Skype Entreprise déploiements locaux avec Voix Entreprise. Ces organisations vont probablement prendre un certain temps avant d’Teams et souhaitent tirer parti de l’expérience Teams réunions dans les plus brefs délais.

> [!TIP]
> Pour vous aider à identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous souhaitez activer dans Teams tant que Skype Entreprise est toujours en cours d’utilisation, tirez parti de [l’Skype](https://aka.ms/SkypeToTeamsWizard)pour Teams Assistant Mise à niveau.

Pour plus d’informations sur les modes de coexistence, les conditions préalables et la gestion, consultez les conseils sur la migration et [l’interopérabilité](./migration-interop-guidance-for-teams-with-skype.md) pour les organisations qui utilisent Teams avec Skype Entreprise et définir vos paramètres de coexistence et de mise à [niveau.](./setting-your-coexistence-and-upgrade-settings.md)

|Icône Du point de décision |Définition de l’icône |Description |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quel (s) mode(s) de coexistence correspond le mieux aux besoins de votre organisation et des utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour votre voyage de mise à niveau.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité des Teams et des Skype Entreprise

L’interopérabilité permet aux utilisateurs Teams et Skype Entreprise au sein d’une même organisation de communiquer entre eux Teams et Skype Entreprise.

L’interopérabilité est régie par le mode de coexistence (également appelé mode de mise à niveau) du récepteur. Il n’y a pas d’interopérabilité lorsque le récepteur est en mode **Îles.**

> [!Note]
> Lorsqu’elles sont déployées dans n’importe quel mode de coexistence à l’exception d’Îles, Teams et Skype Entreprise peuvent [interopérables,](#interoperability-of-teams-and-skype-for-business)permettre aux utilisateurs de discuter et de s’appeler, et de s’assurer que les communications restent fluides au sein de votre organisation dans le cadre de votre voyage de mise à niveau vers Teams. Les modes de coexistence régissent l’interopérabilité. Le mode de coexistence du récepteur détermine si l’interopérabilité sera disponible. Par exemple, si le récepteur est dans un mode dans lequel la conversation est disponible uniquement dans un client (par exemple, Teams), l’interopérabilité des discussions sera généralement disponible si le initiateur utilise l’autre client (dans ce cas, Skype Entreprise) pour démarrer la conversation. En revanche, si le récepteur est dans le mode dans lequel la conversation est disponible dans les deux clients (mode Îles), l’interopérabilité n’est pas disponible pour la conversation. Le message sera reçu par le destinataire dans le même client que celui dans lequel le initiateur a démarré la conversation. Par conséquent, une communication appropriée en mode **Îles** nécessite Teams saturation de l’adoption ; autrement dit, tous les utilisateurs utilisent et contrôlent les deux clients de façon active.

> [!Note]
> **Pour avoir la dernière expérience de coexistence, la version du client doit être la dernière disponible sur le canal de déploiement Office’utilisateur.**

#### <a name="native-interop-and-interop-escalation"></a>Escalade interop et interop native

Il existe deux types d’expériences interop: escalade native et escalade interop.

- Une _expérience d’interop_ native se produit dans le client que l’utilisateur utilise actuellement. L’un des utilisateurs sera dans Skype Entreprise client, l’autre dans Teams. Une expérience d’interop native ne les fait pas communiquer avec un autre client. Les utilisateurs pourront mener leurs conversations dans le client qu’ils utilisent actuellement. Les expériences interop natives sont des appels et des discussions en un-à-un.
- Une  escalade interoper signifie que, dans le cadre de l’aide des utilisateurs à effectuer une action avancée (telle que le partage de leur bureau), le client facilite la création d’une réunion à laquelle les utilisateurs peuvent participer pour continuer l’expérience de cette réunion. La réunion est créée sur la plateforme du initiateur de l’action. Les utilisateurs qui ne utilisent pas cette plateforme reçoivent un lien pour participer à une réunion. Quand ils cliquent sur ce lien, ils sont joints à la réunion dans un client compatible (navigateur, application web ou client complet, selon la configuration). L’escalade entre les Skype Entreprise nécessite un client récent. L’escalade interop Teams est désormais disponible. Les deux sont pris en charge dans les expériences d’interopérabilité au sein du client et pour les clients de communication fédérée.

#### <a name="native-interop-experiences"></a>Expériences interop natives

Selon les modes de coexistence attribués aux utilisateurs (comme décrit précédemment), les expériences d’interop natives suivantes sont disponibles :

Skype Entreprise utilisateurs peuvent discuter en privé avec d Teams utilisateurs, et inversement. Une conversation interop doit passer par une passerelle interop qui fait partie de Teams cloud (et existe par conséquent uniquement en ligne). Les conversations Interop sont en texte intégral : le texte enrichi et les émoticônes ne sont pas pris en charge. Les utilisateurs Teams et Skype Entreprise sont avertis que la conversation est une conversation interop.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype Entreprise utilisateurs peuvent effectuer des appels voix et vidéo en un seul à l’Teams des utilisateurs, et Teams les utilisateurs peuvent faire de même.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Les expériences Interop avec un déploiement local de Skype Entreprise nécessitent que l’environnement local soit en mode hybride avec des Microsoft 365 ou des Office 365 Skype Entreprise. Pour plus d’informations, consultez les [conseils sur la migration et l’interopérabilité.](./migration-interop-guidance-for-teams-with-skype.md)

Ces expériences interop sont disponibles pour les utilisateurs qui disposent de l’un des modes de coexistence suivants : Skype Entreprise avec collaboration **Teams,** Skype Entreprise avec collaboration et réunions **Teams,** **Skype Entreprise Uniquement** ou Teams **Uniquement.** Les utilisateurs n’ont pas accès à l’interopérabilité en mode **Îles.**

#### <a name="native-interop-experience-limitations"></a>Limites de l’expérience interop native

En raison de la différence entre les protocoles et les technologies, il n’est pas possible de prendre en charge toutes les fonctionnalités en natif. Plus précisément, les fonctionnalités suivantes ne sont pas disponibles :

- Les marques, le texte enrichi et l’ensemble complet d’émoticônes ne sont pas pris en charge par les Teams l’Skype Entreprise. Les autres fonctionnalités natives de la zone de composition dans Teams conversations ne sont pas pris en charge.
- Le partage d’écran (partage de Bureau ou d’application) entre Teams et Skype Entreprise n’est pas pris en charge en natif. Toutefois, elle est prise en charge par une escalade interop.
- Les conversations de groupe (conversations à plusieurs) dans une Teams peuvent inclure uniquement les participants qui utilisent Teams.
- Les conversations par messagerie instantanée à plusieurs (conversations de groupe) dans un Skype Entreprise peuvent inclure uniquement les participants qui utilisent Skype Entreprise. Toutefois, l’escalade entre deux parties est disponible depuis Skype Entreprise.
- La escalade d’un appel vocal ou vidéo d’égal à égal en appel multi-partie impliquant à la fois des Teams et des Skype Entreprise n’est pas prise en charge.
- Le transfert de fichiers pour les conversations à deux parties ou la pièce jointe dans les conversations de groupe, de Teams à Skype Entreprise (et inversement) n’est pas pris en charge.
- Il n’y a pas d’interopérabilité avec Skype Entreprise conversation permanente.

Pour toutes ces limitations (à l’exception de la conversation permanente), une solution de contournement possible consiste à ce qu’un utilisateur commence une réunion et invite l’autre utilisateur à la rejoindre.

Cette solution de contournement est à la base de l’escalade interop. En particulier, le partage d’écran et l’escalade vers le multiparte ne sont pas accessibles en natif, mais ils sont pris en charge par une escalade interoperte.

#### <a name="interop-escalation-experiences"></a>Escalade entre les expériences

L’escalade interop consiste à compléter les capacités d’interop natives par des escalades gérées des réunions. Les réunions offrent des expériences enrichies à tous, quel que soit leur client.

Lorsque l’escalade interop est déclenchée par l Teams un utilisateur, une Teams réunion est créée. Lorsqu’elle est déclenchée par l’Skype Entreprise utilisateur, une Skype Entreprise réunion est créée. Dans les deux cas, la réunion créée **est** une réunion Conférence maintenant, qui n’est pas reflétée dans le calendrier de l’utilisateur.

L’autre partie reçoit le lien de participer à la réunion via une conversation interop et des joints en cliquant sur ce lien. Si l Skype Entreprise un utilisateur dispose d’Teams compte et est invité par l’Teams utilisateur, il participera à la réunion authentifiée. Sinon, il rejoint la groupe en tant que participant anonyme. À l’inverse, les utilisateurs Teams ont presque toujours un compte Skype Entreprise et un client Skype Entreprise qu’ils peuvent utiliser pour participer à une réunion Skype Entreprise en tant que participant authentifié, mais ils peuvent également y participer en tant que participant anonyme, par exemple à l’aide de l’application Réunion Skype.

Une fois que les parties ont rejoint la réunion, elles peuvent effectuer toute activité prise en charge dans les réunions, telles que le partage de bureau ou de contenu, le partage de fichiers ou le transfert, l’ajout d’autres participants, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalade entre les deux Skype Entreprise

Les escalades interop et interop depuis Skype Entreprise été mises à jour dans la version mensuelle de C2R de juillet 2019. Auparavant, les Skype Entreprise n’avaient pas conscience que le tiers distant utilisait Teams. Il s’est seulement produit que le signal reçu suite à l’établi d’une session.

Lorsque le signalisation indiquait que la réponse provenait (ou via) la passerelle Interop, la barre d’entreprise jaune (bannière) indiquait que l’autre partie n’utilisait pas Skype Entreprise. Avec l’évolution de notre service, cela a entraîné des faux positifs qui ont permis aux utilisateurs de Skype Entreprise de voir la  barre d’activité lorsqu’ils sont connectés au service Messagerie vocale infonuagique ou à d’autres services vocaux cloud, plutôt qu’à un utilisateur Teams Seul.

Pour éviter ces faux positifs, le service de présence informe désormais le client Skype Entreprise lorsque l’autre partie est un **Teams utilisateur** réel uniquement. Cela permet Skype Entreprise savoir qu’une conversation interop est devant elle et que la fenêtre de conversation doit être spécifique à interoper.

![Capture d’écran Teams d’un message pour créer une conversation interopée avec un Skype Entreprise utilisateur](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si l Skype Entreprise souhaite partager son bureau, par exemple, il est informé que nous démarrerons une réunion et qu’il est guidé au cours des étapes.

![Capture d’écran Teams message de démarrage d’une réunion avec un Teams utilisateur](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

En attendant, l Teams un utilisateur reçoit un message de conversation entrante avec le lien vers la réunion et est guidé pour y participer.

Cette escalade d’Skype Entreprise réunion instantanée est disponible pour les appels et conversations fédérés dans un client interprofessé et inter client. Elle est mise en service par défaut et aucun paramètre n’est à définir par l’administrateur.

#### <a name="interop-escalation-from-teams"></a>Escalade entre les deux Teams

L’escalade entre Teams et une réunion Teams est désormais disponible lorsque l’utilisateur Teams sélectionne le bouton de partage de bureau dans un thread interop dans un client avec un utilisateur Skype Entreprise ou dans un fil de fédération inter-client interop. L’escalade interop est prise en charge dans une conversation à deux ou dans un appel à deux.

Cette fonctionnalité est prise en charge dans le client de bureau Teams pour Windows, dans le client de bureau Teams pour Mac et dans le client web Teams sur les navigateurs où le partage de contenu est pris en charge, tout en communication avec n’importe quelle version du client Skype Entreprise.

Dans les threads d’interopérabilité et dans les threads d’interopérabilité de fédération, le Teams’utilisateur dispose désormais des contrôles (bouton) pour démarrer le partage de contenu. Lorsque l Teams utilisateur sélectionne le bouton, un menu supplémentaire l’informe que pour partager du contenu, il doit démarrer une Teams réunion.

Si les utilisateurs étaient en communication, le menu les avertit également que leur appel actuel entre Teams et Skype Entreprise sera terminé lorsqu’ils seront placés dans une Teams réunion. S’il le choisit, il peut avertir l Skype Entreprise’utilisateur avant de l’accepter.

![Capture d’écran Teams message de partage d’une réunion avec un Skype Entreprise utilisateur](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Sur acceptation, ils sont placés à la réunion Teams réunion ; ils doivent commencer le partage à partir de la bac de partage de la réunion.

En attendant, l Skype Entreprise un utilisateur reçoit un message de conversation entrante avec le lien vers la réunion et est guidé pour y participer.

Cette escalade d’Teams réunion instantanée est disponible pour les appels et conversations fédérés dans un client interprofessé et inter client. Elle est mise en service par défaut et aucun paramètre n’est à définir par l’administrateur. Toutefois, il est désactivé pour l’utilisateur si l’administrateur ``-AllowPrivateMeetNow`` définit ``CsTeamsMeetingPolicy`` sur ``$false`` .

Après avoir lu cet article, voir Choisissez votre voyage de mise à [niveau,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)des conseils sur la migration et [l’interopérabilité,](./migration-interop-guidance-for-teams-with-skype.md)la [coexistence](coexistence-chat-calls-presence.md)avec Skype Entreprise et la définition de vos paramètres de coexistence et de mise à niveau pour des [détails](./setting-your-coexistence-and-upgrade-settings.md) de mise en œuvre. Nous vous recommandons également la vidéo suivante : Vidéo : Gérer la [coexistence et l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Détails techniques de la coexistence Teams et Skype Entreprise collaboration

Les sections suivantes résument le comportement qui peut être utilisé lors de l’exécution de clients Teams et Skype Entreprise dans la même organisation, quel que soit le mode et la méthode de mise à niveau utilisée :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Threads de conversation Interop et natifs](#interop-versus-native-conversation-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)

### <a name="meetings"></a>Réunions

Quel que soit leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion à qui ils sont invités, qu’il s’Skype Entreprise ou Teams.  Toutefois, les utilisateurs doivent participer à la réunion avec un client correspondant au type de réunion :

- Si la réunion est Teams, tous les participants (qu’il s’agit d’utilisateurs de TeamsOnly, d’îles ou d’Skype Entreprise) utilisent le client Teams pour participer à la réunion. Si Teams n’est pas installé, l’utilisateur est dirigé vers le web lorsqu’il tente de participer à une réunion.

- Si la réunion est une réunion Skype Entreprise, tous les participants (qu’il s’agit d’utilisateurs de TeamsOnly, d’îles ou de Skype Entreprise) utilisent le client Skype Entreprise pour participer à la réunion. Si le Skype Entreprise client n’est pas installé, l’utilisateur sera dirigé vers le web pour la rejoindre via l’Réunion Skype App.

Lors de l’organisation de réunions, le type de réunion qui est programmé est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode d’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Toutes les réunions prévues dans Teams. Skype Entreprise-in n’est pas disponible dans Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Toutes les réunions prévues dans Skype Entreprise. Teams-in n’est pas disponible dans Outlook. | 
| Île | Par défaut, les réunions peuvent être programmées soit Skype Entreprise, soit Teams. Les deux modules sont disponibles dans Outlook. Toutefois, vous pouvez demander aux utilisateurs d’îles de toujours planifier des réunions dans Teams en leur attribuant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interopérabilité

Comme décrit ci-dessus dans [l’interopérabilité](#interoperability-of-teams-and-skype-for-business)des Teams et Skype Entreprise, Teams prend en charge l’interopérabilité avec Skype Entreprise dans certains scénarios. La communication Interop fait référence à une conversation ou un appel entre Skype Entreprise utilisateur et un Teams utilisateur.  La communication Interop n’est possible que entre deux utilisateurs. Les discussions/appels à plusieurs ou l’ajout d’utilisateurs supplémentaires ne sont pas pris en charge.

Une conversation ou un appel interop est créé entre deux utilisateurs lorsque chacun des états suivants est vrai :

- Un utilisateur utilise Teams et l’autre Skype Entreprise.

- Le mode du destinataire de la communication initiale n’est PAS (sinon, la communication se place dans le même client) si les deux utilisateurs font partie de la même organisation. Dans les scénarios fédérés, l’utilisateur d’envoi utilise Teams et le destinataire n’est pas en mode TeamsOnly. 

- L Teams un utilisateur n’a pas non Skype Entreprise compte local.

Dans la communication interop, la conversation est uniquement en texte intégral. De plus, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la conversation interop elle-même.* Toutefois, les utilisateurs d’une conversation interop peuvent facilement obtenir un partage de fichier et/ou d’écran en créant une réunion à la demande, au sein de la conversation interop, comme décrit ci-dessous :

- Si l’utilisateur Teams tente de partager son écran, une réunion Teams à la demande est créée automatiquement et un lien d’invitation vers cette réunion est envoyé au client de l’Skype Entreprise. Lorsque vous cliquez sur le lien, l Skype Entreprise un utilisateur ouvre le Teams et rejoint la réunion. Les deux utilisateurs sont maintenant en réunion Teams et peuvent partager le cas nécessaire.

- Si l’utilisateur Skype Entreprise utilise un client depuis 2018 ou une date ultérieure et tente de partager du contenu, une réunion Skype Entreprise à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Teams. Lorsque vous cliquez sur le lien, l Teams un utilisateur tente de rejoindre la Skype Entreprise réunion. Si le Teams a installé le client Skype Entreprise client, il s’ouvre et l’utilisateur est invité à se connecter (s’il n’est pas déjà connecté).  Si le Teams n’a pas Skype Entreprise client installé, l’utilisateur est invité à utiliser la version web. Une fois les deux utilisateurs inscrits, ils sont en réunion Skype Entreprise réunion et peuvent partager le cas nécessaire.

### <a name="interop-versus-native-conversation-threads"></a>Threads de conversation Interop et natifs

Étant donné que les communications interop n’offrent pas toutes les fonctionnalités des conversations Teams natives, le client Teams tient à jour des threads de conversation distincts pour les communications Teams-à-Teams et Teams-à-Skype Entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : les threads Interop peuvent être différenciés à partir d’un thread de conversation native Teams par :

- Absence de contrôles pour le texte enrichi, le partage de fichiers/écran, l’impossibilité d’ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible affichant un « S » pour Skype Entreprise.

Ces différences sont affichées dans les captures d’écran suivantes :

Conversation de Teams en réunion Teams test User G3

![Diagramme montrant une conversation Teams-à-Teams native](media/teams-upgrade-native-thread.png)

Conversation interop avec le même test Utilisateur G3

![Diagramme montrant une conversation Teams entre deux Teams conversation](media/teams-upgrade-interop-thread.png)

Une fois qu’un fil de conversation est créé, son type ne change jamais. Une fois créée, un thread interop dans Teams route toujours vers le client d’Skype Entreprise cible. Un thread natif route toujours vers le client d’Teams cible.  Si le mode d’un utilisateur destinataire change, les threads Teams existants à cet utilisateur ne fonctionnent plus et une note s’affiche dans cette conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.

![Diagramme montrant une conversation avec un utilisateur Skype Entreprise niveau](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est ensuite publiée pour les autres utilisateurs.  Skype Entreprise et Teams services avec des clients distincts, chaque service ayant son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans Teams et Skype Entreprise Online.  Cela permet à un service de publier éventuellement la présence de l’utilisateur à partir de l’autre service si nécessaire. 

Le comportement de publication de présence est basé sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient Teams présence pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient Skype Entreprise présence pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur est en mode Îles, la présence publiée dans Skype Entreprise et Teams est indépendante, de sorte que la présence affichée aux utilisateurs au sein de la même organisation dépend du client de l’autre utilisateur. Les utilisateurs d’organisations fédérées voient la présence de cet utilisateur en fonction de leur activité de Skype Entreprise, car le trafic fédéré vers un utilisateur du mode Îles est Skype Entreprise.

Par exemple, supposons que l’utilisateur A se trouve en mode Îles. Si l’utilisateur A est actif dans Teams mais n’est pas connecté à Skype Entreprise, d’autres utilisateurs le voient comme étant actif à partir de leur client Teams, mais dans leur client Skype Entreprise, ils voient l’utilisateur A comme étant hors connexion. Cela est tout à fait possible, car l’utilisateur A ne peut pas être joint s’il n’exécute pas le client. 


### <a name="federation"></a>Fédération

La fédération d Teams un utilisateur à un autre utilisateur utilisant Skype Entreprise nécessite que l Teams un utilisateur soit homed online dans Skype Entreprise. TeamsUpgradePolicy régit le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les scénarios au même client, sauf en mode Îles. Lorsque les destinataires sont en mode Îles :

- Conversations et appels initiés depuis Teams depuis votre Skype Entreprise si le destinataire se trouve dans un client fédéré.
- Conversations et appels initiés depuis Teams depuis votre Teams si le destinataire se trouve dans le même client.
- Les conversations et appels initiés depuis Skype Entreprise parviennent toujours Skype Entreprise.

Une conversation fédérée peut être un thread natif ou un thread interop. Consultez [les threads de conversation Interop et natifs.](#interop-versus-native-conversation-threads)

- Si le récepteur et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native des [utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) 

- Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’échange avec les messages texte uniquement. L’interface utilisateur expose les conversations fédérées de la même manière que les threads interop du même client, sauf qu’une note indique que l’utilisateur est externe.

Pour plus d’informations, voir Gérer l’accès externe dans Microsoft Teams et [l’expérience](manage-external-access.md) de conversation native pour les utilisateurs externes [(fédérés) Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>Contacts

Teams et Skype Entreprise listes de contacts distinctes. Cela signifie que les ajouts, la suppression et les modifications apportées aux contacts dans un système ne sont pas synchronisés avec l’autre système. Toutefois, les contacts Skype Entreprise sont automatiquement copiés dans le Teams lorsque l’un des deux événements spécifiques se produit : 

- Pour tout Skype Entreprise utilisateur en ligne, la première fois qu’il se connecte à Teams, les contacts de Skype Entreprise sont copiés dans le Teams.  Ce comportement n’est pas disponible pour les utilisateurs avec un compte local dans Skype Entreprise Server.  

- Après la mise à niveau d’un utilisateur vers TeamsOnly (via l’affectation de TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype Entreprise seront fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si l’utilisateur a été déplacé vers TeamsOnly à partir de l’site ou en ligne. 

Dans les deux cas, le transfert de contacts d’Skype Entreprise vers Teams est asynchrone, de sorte que quelques minutes peuvent être avant que les contacts n’apparaissent dans Teams. Les deux événements ci-dessus déclenchent la copie.  

### <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre les Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
