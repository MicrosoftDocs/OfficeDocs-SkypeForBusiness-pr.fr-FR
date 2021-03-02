---
title: Comprendre la coexistence et l’interopérabilité de Microsoft Teams et De Skype Entreprise
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Détails des options de coexistence entre Skype Entreprise et Microsoft Teams, et interopérabilité résultante entre Skype Entreprise et Teams.
localization_priority: Normal
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
ms.openlocfilehash: 430c64fed77412ca555048adf3cf5e323fa20856
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397589"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre la coexistence et l’interopérabilité entre Microsoft Teams et Skype Entreprise

![Diagramme de voyage de mise à niveau mettant en relief la phase Définition de Projet](media/upgrade-banner-project-definition.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape Définition de projet")

Cet article fait partie de la phase Définition de projet de votre voyage de mise à niveau. Terminé après avoir créé un équipe de financement et de projet, et défini l’étendue, les objectifs et le plan de votre projet. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](https://aka.ms/SkypetoTeams-Scope)

Si votre organisation utilise Skype Entreprise aujourd’hui et que vous commencerez à utiliser Teams en même temps que Skype Entreprise , ou si vous démarrez une mise à niveau vers Teams, il est important de comprendre comment les deux applications coexistent, quand et comment elles sont interopérables, et comment gérer la migration de vos utilisateurs jusqu’à leur mise à niveau fin de Skype Entreprise vers Teams.

> [!Tip]
> Regardez la session suivante pour en savoir plus [sur la coexistence et l’interopérabilité.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> En outre, vous pouvez nous rejoindre pour des ateliers interactifs en direct dans lesquels nous allons partager des recommandations, des pratiques et des ressources destinées à lancer la planification et l’implémentation de la mise à niveau.
>
> Participez à la session de mise [à](https://aka.ms/SkypeToTeamsPlanning) niveau pour commencer.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Vue d’ensemble de la coexistence de Teams et de Skype Entreprise

Les sections suivantes décrivent les modes de coexistence disponibles lorsque vous décidez de mettre à niveau vers Teams, ainsi que les fonctionnalités de chaque mode. En outre, nous décrivons l’interopérabilité (interop) qui se produit entre les utilisateurs sur les clients Skype Entreprise et les utilisateurs sur les clients Teams, et la manière dont interop est affectée par le mode de coexistence choisi.

 Teams offre des fonctionnalités de collaboration, de conversation, d’appel et de réunion. Selon la façon dont vous choisissez de déployer Teams, ces fonctionnalités peuvent chevaucher celles de Skype Entreprise pour un utilisateur donné. Le mode par défaut est d’exécuter Teams avec Skype Entreprise avec les fonctionnalités qui se chevauchent. Toutefois, un utilisateur peut se voir attribuer l’un des différents modes de coexistence (également appelés modes de mise à niveau) conçus pour garantir que ces fonctionnalités ne chevauchent pas cet utilisateur (auquel cas l’interopérabilité entre Teams et Skype Entreprise est disponible). Par exemple, si vous avez des ressources importantes pour Skype Entreprise Server sur site avec un déploiement Voix Entreprise complexe, mais que [](meetings-first.md) vous souhaitez que vos utilisateurs profitent des réunions modernes le plus rapidement possible, vous pouvez évaluer d’abord les réunions dans un autre chemin.

Nous vous recommandons de passer en revue les modes de coexistence suivants pour déterminer le chemin le plus exact pour votre organisation.

> [!Important]
> L’introduction d’une nouvelle technologie ou la modification de votre environnement Skype Entreprise existant et familier, tout en vous présentant de nouveaux avantages, peut perturber l’activité des utilisateurs. Prenez le temps d’évaluer la disponibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter les modifications décrites dans cet article. De plus, nous vous encourageons vivement à piloter votre plan avec un groupe d’utilisateurs sélectionné avant de l’implémenter au sein de votre organisation.

### <a name="islands-mode"></a>Mode Îles

Par défaut, les utilisateurs peuvent exécuter Teams avec Skype Entreprise comme deux solutions distinctes qui offrent des fonctionnalités similaires qui se chevauchent. Les fonctionnalités incluent la présence, les discussions, les appels et les réunions. Les utilisateurs de Teams peuvent également tirer parti des nouvelles fonctionnalités de collaboration, telles que les équipes et les canaux, l’accès aux fichiers dans Microsoft 365 ou Office 365 et aux applications.

Dans ce mode de coexistence appelé **Îles,** chacune des applications clientes fonctionne comme une île distincte. Les négociations Skype Entreprise avec Skype Entreprise et Teams avec Teams. Les utilisateurs sont censés exécuter les deux clients à tout moment et peuvent communiquer en natif dans le client à partir duquel la communication a commencé. Ainsi, l’interopérabilité n’est pas nécessaire en mode **Îles.**

Pour éviter une expérience Skype Entreprise déconcertante ou régressée, Skype Entreprise gère  les intégrations suivantes qui ne sont pas gérées en mode Îles Teams :

- Communications externes (fédérées).
- Services vocaux PSTN et applications vocales, intégration d’Office.
- Contrôles HID pour les périphériques USB.
- Plusieurs autres intégrations.  

Phone System n’est pas pris en charge dans Teams en mode **Îles.** Le mode **Îles** ne prend pas en charge Voix Entreprise client skype entreprise.

> [!Important]
> En mode **Îles,** tous les messages et appels des utilisateurs fédérés (personnes extérieures à votre organisation) sont remis à Skype Entreprise. Après la mise à niveau vers le mode **Teams uniquement,** tous les messages et appels en provenance de l’extérieur de votre organisation sont remis dans Teams.

> [!Tip]
> Le chemin recommandé par les clients Skype Entreprise Online consiste à utiliser le **mode** Îles par défaut, à augmenter la saturation de l’adoption de Teams au niveau de l’organisation, puis à passer au mode **Teams** uniquement rapidement. Sur les clients locaux et hybrides, en particulier les plus complexes, il peut être avantageux de déployer Skype Entreprise avec **teams** en tant que point de départ plutôt que d’utiliser le **mode** **Îles,** et de passer de là à Skype Entreprise avec le mode Collaboration et réunions Teams (autrement dit, Réunions en premier), le cas échéant, et vers le mode **Teams** uniquement lorsque l’organisation est prête à adopter Teams.

### <a name="teams-only"></a>Teams uniquement

Un **utilisateur Teams uniquement** (également appelé utilisateur mis à niveau) a accès à toutes les fonctionnalités de Teams.  Ils peuvent conserver le client Skype Entreprise pour participer à des réunions sur Skype Entreprise organisées par des utilisateurs non mis à niveau ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui utilisent toujours Skype Entreprise à l’aide des fonctionnalités d’interopérabilité entre Teams et Skype Entreprise (à condition que les utilisateurs de Skype Entreprise ne soient pas en **mode** Îles). Toutefois, un utilisateur mis à niveau ne peut pas démarrer une conversation, un appel ou une réunion Skype Entreprise.

Dès que votre organisation est prête à ce que certains ou tous les utilisateurs utilisent Teams comme seul outil de communication et de collaboration, vous pouvez mettre à niveau ces utilisateurs vers le mode **Teams uniquement.** Si vous faites une mise à niveau à partir du mode **Îles,** il est conseillé de saturer l’adoption de Teams dans l’ensemble de votre organisation avant de commencer le processus de mise à niveau. Cette adoption évite les scénarios de communication rompus dus au mode **Islands** qui ne fournit pas l’interopérabilité.

En mode **Teams uniquement,** Teams est l’application par défaut pour le protocole SIP/Tel. Les liens dans la carte de visite d’un utilisateur dans Outlook pour les appels ou la conversation sont gérés par Teams.

Pour plus d’informations sur la façon de passer en mode **Teams uniquement,** consultez [les considérations concernant le mode Teams uniquement.](teams-only-mode-considerations.md)

![Capture d’écran du message de confirmation de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Client Skype Entreprise en cours d’exécution dans un mode spécial après la mise à niveau de l’utilisateur en tant qu’utilisateur de Teams uniquement")

### <a name="skype-for-business-only"></a>Skype Entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype Entreprise, et non dans Teams, pour les fonctionnalités de conversation, de réunion et d’appel, et n’utilisent pas Teams pour les équipes et les canaux. Ce mode est disponible aujourd’hui . toutefois, dans l’implémentation actuelle, les équipes et les canaux ne sont pas désactivés automatiquement pour l’utilisateur. Pour ce faire, utilisez la stratégie de configuration d’application pour masquer les équipes et les fichiers.

Ce mode peut être utilisé avant de commencer un déploiement géré de Teams afin d’empêcher les utilisateurs de commencer à utiliser Teams avant d’avoir établi la préparation. Ce mode permet également d’activer la participation authentifiée aux réunions Teams pour les utilisateurs de Skype Entreprise, à condition qu’ils soient titulaires d’une licence pour Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Entreprise avec la collaboration avec Teams

Utilisez ce mode pour présenter Teams dans votre environnement tout en continuer à utiliser votre investissement existant dans Skype Entreprise. Ne changez pas Skype Entreprise pour les fonctionnalités de conversation, d’appel et de réunion. Ajouter des fonctionnalités de collaboration dans Teams :

- Équipes et canaux.
- Accès aux fichiers dans Microsoft 365 ou Office 365.
- Applications. Fonctionnalités de communication Teams : conversation privée, appel et planification de réunions.

Dans ce mode, les discussions privées, les appels et la planification de réunions d’équipes sont éteints par défaut.

Les organisations 365 ayant un point de départ de Skype Entreprise Server en local ou hybride doivent envisager ce **mode** comme une alternative au mode Îles si elles souhaitent offrir à leurs utilisateurs l’interopérabilité et la prévisibilité de leurs communications, ainsi qu’avoir un calendrier prévisible pour leur mise à niveau vers Teams (par opposition à la saturation de l’adoption en mode **Islands).**

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Entreprise avec La collaboration et les réunions d’équipes, également appelées Réunions en premier

Utilisez ce mode de coexistence pour accélérer la disponibilité des fonctionnalités de réunion et de collaboration dans Teams dans votre organisation. Le mode de coexistence permet à vos utilisateurs de tirer parti de l’expérience de réunions Teams supérieure :

- Qualité exceptionnelle.
- Transcription et traduction.
- Effet de flou de l’arrière-plan.
- Expérience utilisateur supérieure sur toutes les plateformes, y compris les appareils mobiles et les navigateurs.

En plus de l’utilisation de Teams pour les équipes et les canaux dans ce mode, les utilisateurs utiliseront Teams pour planifier et mener leurs réunions. Les appels et les discussions privées restent sur Skype Entreprise. Teams et Skype Entreprise bénéficient d’une gamme de fonctionnalités de « meilleur ensemble », telles que le rapprochement des présences, la suspension/désachage automatique et la prise en charge des appareils HID dans les deux applications. Vous avez la possibilité de masquer les équipes et les canaux, si vous le souhaitez, à l’aide de la stratégie de configuration de l’application.

Ce mode de coexistence est particulièrement utile pour les organisations qui utilisent des déploiements Skype Entreprise sur site avec Voix Entreprise. Ces organisations prennent probablement un certain temps de mise à niveau vers Teams et souhaitent bénéficier des réunions Teams supérieures dès que possible.

> [!TIP]
> Pour vous aider à identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous souhaitez activer dans Teams lorsque Skype Entreprise est toujours en cours d’utilisation, tirez parti de l’Assistant Mise à niveau [de Skype vers Teams.](https://aka.ms/SkypeToTeamsWizard)

Pour plus d’informations sur les modes de coexistence, les conditions préalables et la gestion, consultez les conseils sur la migration et [l’interopérabilité](https://aka.ms/SkypeToTeams-Interop) pour les organisations qui utilisent Teams avec Skype Entreprise et définir vos paramètres de coexistence et de [mise à niveau.](https://aka.ms/SkypeToTeams-SetCoexistence)

|Icône Du point de décision |Définition de l’icône |Description |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quel (s) mode(s) de coexistence correspond le mieux aux besoins de votre organisation et des utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour votre voyage de mise à niveau.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité de Teams et Skype Entreprise

L’interopérabilité permet aux utilisateurs de Teams et de Skype Entreprise au sein de la même organisation de communiquer entre Teams et Skype Entreprise.

L’interopérabilité est régie par le mode de coexistence (également appelé mode de mise à niveau) du récepteur. Il n’y a pas d’interopérabilité lorsque le récepteur est en mode **Îles.**

> [!Note]
> Lorsqu’elles sont déployées dans n’importe quel mode de coexistence à l’exception d’Îles, Teams et Skype Entreprise peuvent [interopérables,](#interoperability-of-teams-and-skype-for-business)ce qui permet aux utilisateurs de discuter et de s’appeler, et de s’assurer que les communications restent fluides au sein de votre organisation pendant le chemin de mise à niveau vers Teams. Les modes de coexistence régissent l’interopérabilité. Le mode de coexistence du récepteur détermine si l’interopérabilité sera disponible. Par exemple, si le récepteur est dans un mode dans lequel la conversation est disponible uniquement dans un client (par exemple, Teams), l’interopérabilité des discussions sera généralement disponible au cas où le initiateur utilise l’autre client (dans ce cas, Skype Entreprise) pour démarrer la conversation. En revanche, si le récepteur est dans le mode dans lequel la conversation est disponible dans les deux clients (mode Îles), l’interopérabilité n’est pas disponible pour la conversation. Le message sera reçu par le destinataire dans le même client que celui dans lequel le initiateur a démarré la conversation. Par conséquent, une communication appropriée en mode **Îles** nécessite une saturation de l’adoption de Teams ; autrement dit, tous les utilisateurs utilisent et contrôlent les deux clients de façon active.

> [!Note]
> **Pour avoir la dernière expérience de coexistence, la version du client doit être la dernière disponible sur le canal de déploiement d’Office de l’utilisateur.**

#### <a name="native-interop-and-interop-escalation"></a>Escalade interop et interop native

Il existe deux types d’expériences interop, à l’escalade native et entre les deux.

- Une _expérience d’interop_ native se produit dans le client que l’utilisateur utilise actuellement. Un utilisateur sera dans le client Skype Entreprise, l’autre dans Teams. Une expérience d’interop native ne les fait pas communiquer avec un autre client. Les utilisateurs pourront mener leurs conversations dans le client qu’ils utilisent actuellement. Les expériences interop natives sont des appels et des discussions en un-à-un.
- Une  escalade interoper signifie que, dans le cadre de l’aide des utilisateurs à effectuer une action avancée (telle que le partage de leur bureau), le client facilite la création d’une réunion à laquelle les utilisateurs peuvent participer pour continuer l’expérience de cette réunion. La réunion est créée sur la plateforme du initiateur de l’action. Les utilisateurs qui ne utilisent pas cette plateforme reçoivent un lien pour participer à une réunion. Quand ils cliquent sur ce lien, ils sont joints à la réunion dans un client compatible (navigateur, application web ou client complet, selon la configuration). L’escalade entre utilisateurs de Skype Entreprise nécessite un client récent. L’escalade interop depuis Teams est désormais disponible. Les deux sont pris en charge dans les expériences d’interopérabilité au sein du client et pour les clients de communication fédérée.

#### <a name="native-interop-experiences"></a>Expériences interop natives

Selon les modes de coexistence attribués aux utilisateurs (comme décrit précédemment), les expériences d’interop native suivantes sont disponibles :

Les utilisateurs de Skype Entreprise peuvent discuter en tête-à-tête avec les utilisateurs de Teams, et inversement. Une conversation interop doit passer par une passerelle interop qui fait partie des services cloud de Teams (et existe par conséquent uniquement en ligne). Les conversations Interop sont en texte intégral : le texte enrichi et les émoticônes ne sont pas pris en charge. Les utilisateurs de Teams et de Skype Entreprise sont avertis que la conversation est une conversation interopée.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Les utilisateurs de Skype Entreprise peuvent effectuer des appels vocaux et vidéo en tête-à-tête avec les utilisateurs de Teams, et les utilisateurs de Teams peuvent faire de même.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Les expériences Interop avec un déploiement local de Skype Entreprise nécessitent que l’environnement local soit en mode hybride avec Microsoft 365 ou Office 365 Skype Entreprise. Pour plus d’informations, consultez les [conseils sur la migration et l’interopérabilité.](https://aka.ms/SkypeToTeams-Interop)

Ces expériences d’interopation sont disponibles pour les utilisateurs qui disposent de l’un des modes de coexistence suivants : Skype Entreprise avec la collaboration avec **Teams,** Skype Entreprise avec la collaboration et les réunions **d’équipes,** Skype Entreprise **uniquement** ou **Teams uniquement.** Les utilisateurs n’ont pas accès à l’interopérabilité en mode **Îles.**

#### <a name="native-interop-experience-limitations"></a>Limites de l’expérience interop native

En raison de la différence entre les protocoles et les technologies, il n’est pas possible de prendre en charge toutes les fonctionnalités en natif. Plus précisément, les fonctionnalités suivantes ne sont pas disponibles :

- La liste de marques, le texte enrichi et l’ensemble complet d’émoticônes ne sont pas pris en charge par Teams ou Skype Entreprise. Les autres fonctionnalités natives de la zone de composition dans les conversations Teams ne sont pas prise en charge.
- Le partage d’écran (partage de Bureau ou d’application) entre Teams et Skype Entreprise n’est pas pris en charge en natif. Elle est toutefois prise en charge par une escalade interop.
- Les conversations de groupe (conversations à plusieurs) dans Teams peuvent inclure uniquement les participants qui utilisent Teams.
- Les conversations par messagerie instantanée à plusieurs (conversations de groupe) dans Skype Entreprise ne peuvent inclure que les participants qui utilisent Skype Entreprise. Toutefois, l’escalade entre deux parties est disponible à partir de Skype Entreprise.
- La escalade d’un appel vocal ou vidéo d’égal à égal en appel multi-partie impliquant à la fois Teams et les utilisateurs de Skype Entreprise n’est pas prise en charge.
- Le transfert de fichiers pour les conversations à deux ou pièces jointes dans des conversations de groupe, de Teams vers Skype Entreprise (et inversement) n’est pas pris en charge.
- Il n’y a pas d’interopérabilité avec la conversation permanente Skype Entreprise.

Pour toutes ces limitations (à l’exception de la conversation permanente), une solution de contournement possible consiste à ce qu’un utilisateur commence une réunion et invite l’autre utilisateur à la rejoindre.

Cette solution de contournement est à la base de l’escalade interop. En particulier, le partage d’écran et l’escalade vers le multiparte ne sont pas accessibles en natif, mais ils sont pris en charge par une escalade interoperte.

#### <a name="interop-escalation-experiences"></a>Escalade entre les expériences

L’escalade interop consiste à compléter les fonctionnalités d’interconnexion natives par des escalades gérées des réunions. Les réunions offrent des expériences enrichies à tous, quel que soit leur client.

Lorsque l’escalade interop est déclenchée par l’utilisateur de Teams, une réunion Teams est créée. Lorsque cette réunion est déclenchée par l’utilisateur Skype Entreprise, une réunion Skype Entreprise est créée. Dans les deux cas, la réunion créée **est** une réunion Conférence maintenant, qui n’est pas reflétée dans le calendrier de l’utilisateur.

L’autre partie reçoit le lien de participer à la réunion via une conversation interop et des joints en cliquant sur ce lien. Si l’utilisateur de Skype Entreprise dispose d’un compte Teams et est invité par l’utilisateur de Teams, il participera à la réunion authentifiée. Sinon, il rejoint la groupe en tant que participant anonyme. À l’inverse, les utilisateurs de Teams ont presque toujours un compte Skype Entreprise et un client Skype Entreprise qu’ils peuvent utiliser pour participer à une réunion Skype Entreprise en tant que participant authentifié, mais ils peuvent également la rejoindre en tant que participant anonyme, par exemple à l’aide de l’application réunion Skype.

Une fois que les parties ont rejoint la réunion, elles peuvent effectuer toute activité prise en charge dans les réunions, telles que le partage de bureau ou de contenu, le partage ou le transfert de fichiers, l’ajout d’autres participants, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalade interop à partir de Skype Entreprise

L’escalade interop et interop depuis Skype Entreprise a été mise à jour dans la version mensuelle de C2R de juillet 2019. Auparavant, Skype Entreprise n’avait pas conscience que le groupe distant utilisait Teams. Il s’est seulement produit que le signal reçu suite à l’établi d’une session.

Lorsque le signalisation indiquait que la réponse provenait (ou via) la passerelle Interop, la barre d’entreprise jaune (bannière) indiquait que l’autre partie n’utilisait pas Skype Entreprise. Avec l’évolution de notre service, cela a pour conséquence de faux positifs que les utilisateurs de Skype Entreprise voient la barre d’activité lorsqu’ils sont connectés au service de messagerie vocale cloud ou à d’autres services vocaux cloud, plutôt qu’à un véritable utilisateur de **Teams uniquement.**

Pour éviter ces faux positifs, le service de présence informe désormais le client Skype Entreprise lorsque l’autre partie est un utilisateur **réel de Teams.** Cela permet à Skype Entreprise de savoir qu’une conversation interop est nécessaire avant sa création et que la fenêtre de conversation doit être spécifique à interoper.

![Capture d’écran du message Teams pour créer une conversation interop avec un utilisateur Skype Entreprise](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Par exemple, si l’utilisateur de Skype Entreprise souhaite partager son Bureau, il est informé que nous allons démarrer une réunion et qu’il est guidé au cours des étapes.

![Capture d’écran du message Teams pour démarrer une réunion avec un utilisateur de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

En attendant, l’utilisateur de Teams reçoit un message de conversation entrante avec le lien vers la réunion et est guidé pour y participer.

Cette escalade d’accès à une réunion Skype Entreprise est disponible pour les appels et conversations fédérés dans un client interprofessé et inter client. Elle est mise en service par défaut et aucun paramètre n’est à mettre en service par l’administrateur.

#### <a name="interop-escalation-from-teams"></a>Escalade interop depuis Teams

L’escalade entre Teams et une réunion Teams est désormais disponible lorsque l’utilisateur de Teams sélectionne le bouton de partage de bureau dans une conversation interop client avec un utilisateur Skype Entreprise ou dans un fil de fédération inter-client interop. L’escalade interop est prise en charge dans une conversation à deux ou dans un appel à deux.

Cette fonctionnalité est prise en charge dans le client de bureau Teams pour Windows, dans le client de bureau Teams pour Mac et dans le client web Teams sur les navigateurs où le partage de contenu est pris en charge, tout en communication avec n’importe quelle version du client Skype Entreprise.

Dans les threads d’interopérabilité et dans les threads d’interopérabilité de fédération, l’utilisateur de Teams dispose désormais des contrôles (bouton) pour démarrer le partage de contenu. Lorsque l’utilisateur de Teams sélectionne le bouton, un menu supplémentaire l’informe que pour partager du contenu, il doit démarrer une réunion Teams.

Si les utilisateurs étaient en communication, le menu les avertit également que leur appel actuel entre Teams et Skype Entreprise sera résilié lorsqu’ils seront placés dans une réunion Teams. S’il le choisit, il peut avertir l’utilisateur de Skype Entreprise avant de l’accepter.

![Capture d’écran du message Teams pour partager une réunion avec un utilisateur Skype Entreprise](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Dès acceptation, ils sont placés dans la réunion Teams ; ils doivent commencer le partage à partir de la bac de partage dans la réunion.

En attendant, l’utilisateur de Skype Entreprise reçoit un message de conversation entrante avec le lien vers la réunion et est guidé pour y participer.

Cette escalade d’accès à une réunion Teams est disponible pour les appels et conversations fédérés dans un client interprofessé et inter client. Elle est mise en service par défaut et aucun paramètre n’est à mettre en service par l’administrateur. Elle est toutefois désactivée pour l’utilisateur si l’administrateur ``-AllowPrivateMeetNow`` définit ``CsTeamsMeetingPolicy`` sur ``$false`` .

Après avoir lu cet article, consultez Choisir votre voyage de mise à [niveau,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)les conseils de migration et [d’interopérabilité,](https://aka.ms/SkypeToTeams-Interop)la [coexistence](coexistence-chat-calls-presence.md)avec Skype Entreprise et la définition de vos paramètres de coexistence et de mise à niveau pour des [détails](https://aka.ms/SkypeToTeams-SetCoexistence) de mise en œuvre. Nous recommandons également la vidéo suivante : Vidéo : Gérer la coexistence et [l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Détails techniques de Teams et de la coexistence avec Skype Entreprise

Les sections suivantes résument le comportement qui peut être utilisé lors de l’exécution des clients Teams et Skype Entreprise dans la même organisation, quel que soit le mode et la méthode de mise à niveau utilisée :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Threads de conversation Teams - Interop et threads natifs](#teams-conversations---interop-versus-native-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)



### <a name="meetings"></a>Réunions

Quel que soit leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion à qui ils sont invités, qu’il s’agit de Skype Entreprise ou Teams.  Toutefois, les utilisateurs doivent participer à la réunion avec un client correspondant au type de réunion :

- S’il s’agit d’une réunion Teams, tous les participants (qu’il s’agit de TeamsOnly, d’îles ou de Skype Entreprise) utilisent le client Teams pour participer à la réunion. Si Teams n’est pas installé, l’utilisateur est dirigé vers le web lors de sa tentative de rejoindre une réunion.

- S’il s’agit d’une réunion Skype Entreprise, tous les participants (qu’il s’agit de TeamsOnly, d’îles ou de Skype Entreprise) utilisent le client Skype Entreprise pour participer à la réunion. Si le client Skype Entreprise n’est pas installé, l’utilisateur sera dirigé vers le Web pour y participer via l’application de réunion Skype.

Lors de l’organisation de réunions, le type de réunion qui est programmé est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode d’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Toutes les réunions prévues dans Teams. Le module logiciel skype entreprise n’est pas disponible dans Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Toutes les réunions prévues dans Skype Entreprise. Le add-in Teams n’est pas disponible dans Outlook. | 
| Île | Par défaut, les réunions peuvent être programmées dans Skype Entreprise ou Teams. Les deux modules sont disponibles dans Outlook. Toutefois, vous pouvez demander aux utilisateurs d’îles de toujours planifier des réunions dans Teams en leur attribuant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interopérabilité

Comme décrit ci-dessus [dans l’interopérabilité de Teams](#interoperability-of-teams-and-skype-for-business)et de Skype Entreprise, Teams prend en charge l’interopérabilité avec Skype Entreprise dans certains scénarios. La communication Interop fait référence à une conversation ou un appel entre un utilisateur Skype Entreprise et un utilisateur de Teams.  La communication Interop n’est possible que entre deux utilisateurs. Les discussions/appels à plusieurs ou l’ajout d’utilisateurs supplémentaires ne sont pas pris en charge.

Une conversation ou un appel interop est créé entre deux utilisateurs lorsque chacun des états suivants est vrai :

- Un utilisateur utilise Teams et l’autre utilise Skype Entreprise.

- Le mode du destinataire de la communication initiale n’est PAS (sinon, la communication se place dans le même client) si les deux utilisateurs font partie de la même organisation. Dans les scénarios fédérés, l’utilisateur d’envoi utilise Teams et le destinataire n’est pas en mode TeamsOnly. 

- L’utilisateur de Teams n’a PAS non plus de compte Skype Entreprise homed sur site.

Dans la communication interop, la conversation est uniquement en texte intégral. De plus, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la conversation interop elle-même.* Toutefois, les utilisateurs d’une conversation interop peuvent facilement obtenir un partage de fichier et/ou d’écran en créant une réunion à la demande, au sein de la conversation interop, comme décrit ci-dessous :

- Si l’utilisateur de Teams tente de partager son écran, une réunion Teams à la demande est créée automatiquement et un lien d’invitation vers cette réunion est envoyé au client de l’utilisateur Skype Entreprise. Lorsque vous cliquez sur le lien, l’utilisateur de Skype Entreprise ouvre Teams et rejoint la réunion. Les deux utilisateurs sont maintenant dans une réunion Teams et peuvent partager le cas nécessaire.

- Si l’utilisateur de Skype Entreprise utilise un client depuis 2018 ou une date ultérieure et tente de partager du contenu, une réunion Skype Entreprise à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur de Teams. En cliquant sur le lien, l’utilisateur de Teams tente de participer à la réunion Skype Entreprise. Si le client Skype Entreprise est installé sur l’utilisateur Teams, celui-ci s’ouvre et l’utilisateur est invité à se connecter (s’il n’est pas encore connecté).  Si le client Skype Entreprise n’est pas installé pour l’utilisateur Teams, il est invité à utiliser la version web. Une fois les deux utilisateurs inscrits, ils sont en réunion Skype Entreprise et peuvent les partager au besoin.

### <a name="teams-conversation-threads---interop-versus-native-threads"></a>Threads de conversation Teams - Interop et threads natifs

Étant donné que les communications interop n’offrent pas toutes les fonctionnalités des conversations Teams natives, le client Teams propose des threads de conversation distincts pour les communications Teams-to-Teams et teams-to-Skype Entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : Les threads Interop peuvent être différenciés d’un thread Teams natif normal par :

- Absence de contrôles pour le texte enrichi, le partage de fichiers/écran, l’impossibilité d’ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible affichant un « S » pour Skype Entreprise.

Ces différences sont affichées dans les captures d’écran suivantes :

Conversation Teams-to-Teams native avec le test User G3

![Diagramme montrant une conversation Teams-to-Teams native](media/teams-upgrade-native-thread.png)

Conversation interop avec le même test Utilisateur G3

![Diagramme montrant une conversation Interop Teams-to-Teams](media/teams-upgrade-interop-thread.png)

Une fois qu’un fil de conversation est créé, son type ne change jamais. Une fois créée, un thread interop dans Teams routera toujours vers le client Skype Entreprise de l’utilisateur cible. Un fil de discussion natif routera toujours vers le client Teams de l’utilisateur cible.  Si le mode d’un utilisateur du destinataire change, les threads Teams existants à cet utilisateur ne fonctionnent plus et une note s’affiche dans cette conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.

![Diagramme montrant une conversation avec l’utilisateur Skype Entreprise mis à niveau](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est ensuite publiée pour les autres utilisateurs.  Skype Entreprise et Teams sont des services distincts avec des clients distincts, de sorte que chaque service a son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans Teams et dans Skype Entreprise Online.  Cela permet à un service de publier éventuellement la présence de l’utilisateur à partir de l’autre service si nécessaire. 

Le comportement de publication de présence est basé sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence Teams pour cet utilisateur, quel que soit le client qu’ils utilisent.

- Si un utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient la présence de Skype Entreprise pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur est en mode Îles, la présence publiée dans Skype Entreprise et Teams est indépendante, de sorte que la présence affichée aux utilisateurs au sein de la même organisation dépend du client de l’autre utilisateur. Les utilisateurs d’organisations fédérées peuvent voir s’ils sont présents en fonction de leur activité Skype Entreprise, car le trafic fédéré vers un utilisateur du mode Îles arrive dans Skype Entreprise.

Par exemple, supposons que l’utilisateur A se trouve en mode Îles. Si l’utilisateur A est actif dans Teams, mais n’est pas connecté à Skype Entreprise, d’autres utilisateurs voient l’utilisateur A comme actif à partir de leur client Teams, mais dans leur client Skype Entreprise, ils voient l’utilisateur A comme hors connexion. Cela est tout à fait possible, car l’utilisateur A ne peut pas être joint s’il n’exécute pas le client. 


### <a name="federation"></a>Fédération

La fédération de Teams vers un autre utilisateur utilisant Skype Entreprise nécessite que l’utilisateur de Teams soit homed online dans Skype Entreprise. TeamsUpgradePolicy régit le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les scénarios au même client, sauf en mode Îles. Lorsque les destinataires sont en mode Îles :

- Les conversations et appels initiés à partir de Teams sont lancés dans Skype Entreprise si le destinataire se trouve dans un client fédéré.
- Les conversations et appels initiés à partir de Teams se placent dans Teams si le destinataire se trouve dans le même client.
- Les conversations et appels initiés par Skype Entreprise sont toujours lancés dans Skype Entreprise.

Une conversation fédérée peut être un thread natif ou un thread interop. Consultez [Conversations Teams ---interop-versus-native-threads.](#teams-conversations---interop-versus-native-threads)

- Si le récepteur et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native pour [les utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) 

- Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’échange avec les messages texte uniquement. L’interface utilisateur expose les conversations fédérées de la même manière que les threads interop de même client, sauf qu’une note indique que l’utilisateur est externe.

Pour plus d’informations, voir Gérer l’accès externe dans [Microsoft Teams](manage-external-access.md) et l’expérience de conversation native pour les utilisateurs [externes (fédérés) dans Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>Contacts

Teams et Skype Entreprise ont des listes de contacts distinctes. Cela signifie que les ajouts, la suppression et les modifications apportées aux contacts dans un système ne sont pas synchronisés avec l’autre système. Toutefois, les contacts de Skype Entreprise sont automatiquement copiés dans Teams lorsque l’un des deux événements spécifiques se produit : 

- Pour les utilisateurs Skype Entreprise Online, lors de leur première connexion à Teams, les contacts de Skype Entreprise sont copiés dans Teams.  Ce comportement n’est pas disponible pour les utilisateurs avec un compte local dans Skype Entreprise Server.  

- Après la mise à niveau d’un utilisateur vers TeamsOnly (via l’affectation de TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype Entreprise seront fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si le compte Skype Entreprise de l’utilisateur est homed local ou en ligne. 

Dans les deux cas, le transfert de contacts de Skype Entreprise vers Teams est asynchrone, de sorte que quelques minutes peuvent être avant que les contacts n’apparaissent dans Teams. Les deux événements ci-dessus déclenchent la copie.  

### <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
