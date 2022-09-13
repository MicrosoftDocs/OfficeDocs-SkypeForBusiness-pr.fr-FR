---
title: Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Détails des options de coexistence Skype Entreprise et Microsoft Teams, ainsi que l’interopérabilité qui en résulte entre Skype Entreprise et Teams.
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
ms.openlocfilehash: 6d1b5604d5b76d0f642fe26a4ec9777060b9d5ef
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657334"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité

![Diagramme de parcours de mise à niveau, mettant l’accent sur l’étape Définition de projet.](media/upgrade-banner-project-definition.png "Étapes du parcours de mise à niveau, en mettant l’accent sur l’étape Définition de projet")

Cet article fait partie de l’étape Définition de projet de votre parcours de mise à niveau. Terminé après avoir créé une coalition de parrainage et une équipe de projet et défini l’étendue, les objectifs et le plan de votre projet. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)

Si votre organisation utilise Skype Entreprise aujourd’hui et que vous commencez à utiliser Teams en même temps que Skype Entreprise (ou si vous commencez à effectuer une mise à niveau vers Teams), il est important de comprendre comment les deux applications coexistent, quand et comment elles interagissent, et comment gérer la migration de vos utilisateurs jusqu’à leur mise à niveau à partir de Skype Entreprise  vers Teams.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur [la coexistence et l’interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop).
>
> En outre, vous pouvez vous joindre à nous pour des ateliers interactifs en direct dans lesquels nous partagerons des conseils, des meilleures pratiques et des ressources conçues pour lancer la planification et la mise en œuvre de la mise à niveau.
>
> Rejoignez d’abord la session [De planification de votre mise à niveau](./upgrade-workshops-landing-page.yml) pour commencer.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Vue d’ensemble de la coexistence de Teams et de Skype Entreprise

Les sections suivantes décrivent les modes de coexistence qui sont disponibles lorsque vous décidez de mettre à niveau vers Teams, ainsi que les fonctionnalités offertes par chaque mode. En outre, nous décrivons l’interopérabilité (interopérabilité) qui se produit entre les utilisateurs sur les clients Skype Entreprise et les utilisateurs sur les clients Teams, et comment l’interopérabilité est affectée par le mode de coexistence choisi.

Teams offre des fonctionnalités de collaboration, de conversation, d’appel et de réunion. Selon la façon dont vous choisissez de déployer Teams, ces fonctionnalités peuvent chevaucher les fonctionnalités fournies par Skype Entreprise pour un utilisateur donné. Le mode par défaut consiste à exécuter Teams en même temps que Skype Entreprise avec les fonctionnalités qui se chevauchent. Toutefois, un utilisateur peut se voir attribuer l’un des différents modes de coexistence (également appelés modes de mise à niveau) qui ont été conçus pour garantir que ces fonctionnalités ne se chevauchent pas pour cet utilisateur (auquel cas l’interopérabilité entre Teams et Skype Entreprise est disponible). Par exemple, si vous disposez de ressources locales Skype Entreprise Server importantes avec un déploiement Téléphonie –  Grandes entreprises complexe, mais que vous souhaitez que vos utilisateurs puissent profiter des réunions modernes aussi rapidement que possible, vous souhaiterez peut-être évaluer [Meetings First](meetings-first.md) comme un autre chemin d’accès.

Nous vous recommandons de passer en revue les modes de coexistence suivants pour déterminer le chemin d’accès adapté à votre organisation.

> [!Important]
> Les modes de coexistence continuent d’exister après la mise hors service de Skype Entreprise Online, mais les utilisateurs hébergés en ligne ne peuvent avoir qu’un mode TeamsOnly. Il n’est plus possible d’affecter un mode autre que TeamsOnly à un utilisateur hébergé en ligne.  Comme c’était le cas avant la mise hors service de Skype Entreprise Online, les utilisateurs hébergés localement peuvent se voir attribuer n’importe quel mode *autre que TeamsOnly*.

### <a name="islands-mode"></a>Mode Îles

Par défaut, les utilisateurs peuvent exécuter Teams en même temps que Skype Entreprise en tant que deux solutions distinctes qui offrent des fonctionnalités similaires et qui se chevauchent. Les fonctionnalités incluent la présence, la conversation, l’appel et les réunions. Les utilisateurs teams peuvent également tirer parti de nouvelles fonctionnalités de collaboration telles que les équipes et les canaux, l’accès aux fichiers dans Microsoft 365 et aux applications.

Dans ce mode de coexistence, appelé **Îles**, chacune des applications clientes fonctionne comme une île distincte. Skype Entreprise communique avec Skype Entreprise et Teams communique avec Teams. Les utilisateurs sont censés exécuter les deux clients en tout temps et peuvent communiquer en mode natif dans le client à partir duquel la communication a été démarrée. Par conséquent, il n’est pas nécessaire d’interopérabilité en mode **Îles** .

Pour éviter une expérience Skype Entreprise déroutante ou régressée, le Skype Entreprise gère les intégrations suivantes qui ne sont pas gérées en mode **Îles** Teams :

- Communications externes (fédérées).
- Services vocaux RTC et applications vocales, intégration d’Office.
- Contrôles HID pour les périphériques USB.
- Plusieurs autres intégrations.

Le système téléphonique n’est pas pris en charge dans Teams en mode **Îles** . **Le mode Islands** ne prend pas en charge Téléphonie –  Grandes entreprises client est Skype Entreprise.

> [!Important]
> En mode **Îles**, tous les messages et appels des utilisateurs fédérés (personnes extérieures à votre organisation) sont remis à Skype Entreprise. Après la mise à niveau vers le mode **Teams uniquement** , tous les messages et appels provenant de l’extérieur de votre organisation sont remis à Teams.

### <a name="teams-only"></a>Teams uniquement

Un utilisateur **Teams uniquement** (également appelé utilisateur *mis à niveau* ) a accès à toutes les fonctionnalités de Teams. Ils peuvent conserver le client Skype Entreprise pour participer à des réunions sur Skype Entreprise qui ont été organisées par des utilisateurs non mis à niveau ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui utilisent toujours Skype Entreprise en utilisant les fonctionnalités d’interopérabilité entre Teams et Skype Entreprise (à condition que les utilisateurs Skype Entreprise ne soient pas en mode **Îles**). Toutefois, un utilisateur mis à niveau ne peut pas lancer de conversation, d’appel ou de réunion Skype Entreprise.

Dès que votre organisation est prête pour que certains utilisateurs ou tous les utilisateurs utilisent Teams comme seul outil de communication et de collaboration, mettez à niveau ces utilisateurs vers le mode **Teams uniquement** . Si vous effectuez une mise à niveau à partir du mode **Îles** , nous vous conseillons de d’abord saturer l’adoption de Teams dans toute votre organisation avant de commencer le processus de mise à niveau. Cette adoption évite les scénarios de communication rompus en raison du mode **Îles** qui ne fournit pas d’interopérabilité.

En mode **Teams uniquement** , Teams est l’application par défaut pour le protocole SIP/Tel. Les liens dans la carte de visite d’un utilisateur dans Outlook pour l’appel ou la conversation sont gérés par Teams.

Pour plus d’informations sur le passage au mode **Teams uniquement** , consultez [les considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md).

![Capture d’écran du message de confirmation Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype Entreprise client s’exécutant en mode spécial après la mise à niveau de l’utilisateur en tant qu’utilisateur Teams uniquement")

### <a name="skype-for-business-only"></a>Skype Entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype Entreprise (et non Teams) pour les fonctionnalités de conversation, de réunion et d’appel, et ils n’utilisent pas Teams pour les équipes et les canaux. Ce mode est disponible aujourd’hui; toutefois, dans l’implémentation actuelle, les équipes et les canaux ne sont pas automatiquement désactivés pour l’utilisateur. Pour ce faire, utilisez la stratégie d’installation d’application pour masquer les équipes et les fichiers.

Ce mode peut être utilisé avant le démarrage d’un déploiement managé de Teams pour empêcher les utilisateurs de commencer à utiliser Teams avant d’avoir une préparation intégrée. Ce mode permet également d’activer la participation authentifiée aux réunions Teams pour Skype Entreprise utilisateurs, à condition que les utilisateurs disposent d’une licence Pour Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Entreprise avec Teams Collaboration

Utilisez ce mode pour introduire Teams dans votre environnement tout en continuant à utiliser votre investissement existant dans Skype Entreprise. Laissez Skype Entreprise inchangé pour les fonctionnalités de conversation, d’appel et de réunion. Ajoutez des fonctionnalités de collaboration Teams :

- Équipes et canaux.
- Accès aux fichiers dans Microsoft 365 ou Office 365.
- Applications. Fonctionnalités de communication Teams : conversation privée, appel et planification de réunions.

Les réunions de conversation, d’appel et de planification privées Teams sont désactivées par défaut dans ce mode.

Les organisations avec un point de départ de Skype Entreprise Server localement ou hybride doivent considérer ce mode comme une alternative au mode **Îles** si elles souhaitent offrir à leurs utilisateurs une interopérabilité et une prévisibilité pour leurs communications, ainsi qu’une chronologie prévisible pour leur mise à niveau vers Teams (au lieu de s’appuyer sur la saturation de l’adoption en mode **Îles**).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Entreprise avec collaboration et réunions Teams, également appelées Réunions d’abord

Utilisez ce mode de coexistence pour accélérer la disponibilité des fonctionnalités de réunion et de collaboration Teams dans votre organisation. Le mode de coexistence permet à vos utilisateurs de tirer parti de l’expérience supérieure des réunions Teams :

- Grande qualité.
- Transcription et traduction.
- Flou d’arrière-plan.
- Expérience utilisateur supérieure sur toutes les plateformes, y compris les appareils mobiles et les navigateurs.

Outre l’utilisation de Teams pour les équipes et les conversations basées sur les canaux dans ce mode, les utilisateurs utilisent Teams pour planifier et mener leurs réunions. Les conversations privées et les appels restent sur Skype Entreprise. Teams et Skype Entreprise bénéficient d’une gamme de fonctionnalités « mieux regroupées », telles que le rapprochement des présences, la conservation/la non-conservation automatique et la prise en charge des appareils HID dans les deux applications. Il est possible de masquer les équipes et les canaux, si vous le souhaitez, à l’aide de la stratégie d’installation de l’application.

Ce mode de coexistence est particulièrement utile pour les organisations avec Skype Entreprise déploiements locaux avec Téléphonie –  Grandes entreprises. Ces organisations sont susceptibles de prendre un certain temps pour effectuer une mise à niveau vers Teams et souhaitent tirer parti des réunions Teams supérieures dès que possible.

> [!TIP]
> Pour identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous souhaitez activer dans Teams alors que Skype Entreprise est toujours en cours d’utilisation, tirez parti de [l’Assistant Mise à niveau de Skype vers Teams](https://aka.ms/SkypeToTeamsWizard).

Pour plus d’informations sur les modes de coexistence, les prérequis et la gestion, consultez [les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md) et [définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md).

|Icône de point de décision |Définition d’icône |Description |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quel est le ou les modes de coexistence les mieux adaptés aux besoins de votre organisation et des utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour votre parcours de mise à niveau.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité de Teams et de Skype Entreprise

L’interopérabilité est la possibilité pour Teams et Skype Entreprise utilisateurs de la même organisation de communiquer entre Teams et Skype Entreprise.

L’interopérabilité est régie par le mode de coexistence (également appelé mode de mise à niveau) du récepteur. Il n’existe aucune interopérabilité lorsque le récepteur est en mode **Îles** .

> [!Note]
> En cas de déploiement dans n’importe quel mode de coexistence à l’exception **des îles**, Teams et Skype Entreprise peuvent [interagir](#interoperability-of-teams-and-skype-for-business), ce qui permet aux utilisateurs de discuter et de s’appeler les uns les autres, et de s’assurer que les communications restent fluides au sein de votre organisation pendant votre parcours de mise à niveau vers Teams. Les modes de coexistence régissent l’interopérabilité. Le mode de coexistence du récepteur détermine si l’interopérabilité sera disponible. Par exemple, si le récepteur est dans un mode dans lequel la conversation n’est disponible que dans un client (par exemple, Teams), l’interopérabilité de conversation est généralement disponible si l’initiateur utilise l’autre client (dans ce cas, Skype Entreprise) pour démarrer la conversation. En revanche, si le récepteur est dans le mode dans lequel la conversation est disponible dans les deux clients (mode Îles), l’interopérabilité ne sera pas disponible pour la conversation. Le message sera reçu par le destinataire dans le même client que celui dans lequel l’initiateur a démarré la conversation. Par conséquent, une communication appropriée en mode **Îles** nécessite une saturation de l’adoption de Teams ; autrement dit, tous les utilisateurs utilisent et surveillent activement les deux clients.

> [!Note]
> **Pour avoir la dernière expérience de coexistence, la version du client doit être le client le plus récent disponible dans le canal de déploiement Office de l’utilisateur.**

#### <a name="native-interop-and-interop-escalation"></a>Escalade d’interopérabilité et d’interopérabilité natives

Il existe deux types d’expériences d’interopérabilité : l’escalade native et l’escalade d’interopérabilité.

- Une expérience _d’interopérabilité native_ se produit dans le client que l’utilisateur utilise actuellement. Un utilisateur se trouvera dans le client Skype Entreprise, l’autre dans Teams. Une expérience d’interopérabilité native ne les amène pas à un autre client pour communiquer. Les utilisateurs pourront mener leur conversation dans le client qu’ils utilisent actuellement. Les expériences d’interopérabilité natives sont des conversations et des appels un-à-un.
- Une expérience _d’escalade d’interopérabilité_ signifie que, dans le cadre de l’aide aux utilisateurs à effectuer une action avancée (par exemple, le partage de leur bureau), le client facilite la création d’une réunion à laquelle les utilisateurs peuvent participer pour poursuivre l’expérience dans cette réunion. La réunion est créée sur la plateforme de l’initiateur de l’action. L’utilisateur ou les utilisateurs qui ne sont pas sur cette plateforme reçoivent un lien de participation à une réunion. Quand ils cliquent sur ce lien, ils sont joints à la réunion dans un client compatible (navigateur, application web ou client complet, selon la configuration). L’escalade d’interopérabilité à partir de Skype Entreprise nécessite un client récent. L’escalade d’interopérabilité à partir de Teams est désormais disponible. Les deux sont pris en charge dans les expériences d’interopérabilité in-tenant et pour les communications fédérées entre locataires.

#### <a name="native-interop-experiences"></a>Expériences d’interopérabilité natives

Selon les modes de coexistence affectés aux utilisateurs (comme décrit précédemment), les expériences d’interopérabilité native suivantes sont disponibles :

Skype Entreprise les utilisateurs peuvent discuter en un-à-un avec des utilisateurs Teams, et vice versa. Une conversation d’interopérabilité doit passer par une passerelle d’interopérabilité qui fait partie des services cloud Teams (et n’existe donc qu’en ligne). Les conversations d’interopérabilité sont du texte brut : le texte enrichi et les émoticônes ne sont pas pris en charge. Les utilisateurs dans Teams et dans Skype Entreprise sont avertis que la conversation est une conversation d’interopérabilité.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype Entreprise les utilisateurs peuvent passer des appels vocaux et vidéo en tête-à-tête aux utilisateurs Teams, et les utilisateurs Teams peuvent faire de même.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Les expériences d’interopérabilité avec un déploiement local de Skype Entreprise nécessitent que l’environnement local soit en mode hybride avec Teams. Pour plus d’informations, [configurez la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Ces expériences d’interopérabilité sont disponibles pour et entre les utilisateurs qui ont l’un des modes de coexistence suivants : **Skype Entreprise avec Collaboration Teams**, **Skype Entreprise avec Collaboration Teams et réunions**, **Skype Entreprise uniquement** ou **Teams uniquement**. Il n’existe aucune interopérabilité pour les utilisateurs en mode **Îles** .

#### <a name="native-interop-experience-limitations"></a>Limitations de l’expérience d’interopérabilité native

En raison de la différence entre les protocoles et la technologie, il n’est pas possible de prendre en charge toutes les fonctionnalités en mode natif. Plus précisément, les fonctionnalités suivantes ne sont pas disponibles :

- Markdown, le texte enrichi et l’ensemble complet d’émoticônes ne sont pas pris en charge à partir de Teams ou de Skype Entreprise. Les autres fonctionnalités natives de la zone de composition dans les conversations Teams ne sont pas prises en charge.
- Le partage d’écran (partage de bureau ou d’application) entre Teams et Skype Entreprise n’est pas pris en charge en mode natif. Toutefois, elle est prise en charge par le biais de l’escalade d’interopérabilité.
- Les conversations de groupe (conversations à plusieurs parties) dans Teams peuvent uniquement inclure les participants qui utilisent Teams.
- Les conversations par messagerie instantanée à plusieurs parties (conversations de groupe) dans Skype Entreprise ne peuvent inclure que les participants qui utilisent Skype Entreprise. Toutefois, l’escalade d’interopérabilité vers plusieurs parties est disponible à partir de Skype Entreprise.
- L’escalade d’un appel vocal ou vidéo d’égal à égal continu à un appel à plusieurs parties impliquant à la fois Teams et Skype Entreprise utilisateurs n’est pas prise en charge.
- Le transfert de fichiers pour les conversations à deux parties, ou la pièce jointe dans les conversations de groupe, de Teams à Skype Entreprise, et inversement, ne sont pas pris en charge.
- Il n’existe aucune interopérabilité avec Skype Entreprise conversation permanente.

Pour toutes ces limitations (à l’exception de la conversation permanente), une solution de contournement possible consiste à permettre à un utilisateur de démarrer une réunion et d’inviter l’autre utilisateur à la rejoindre.

Cette solution de contournement est la base de l’escalade d’interopérabilité. En particulier, le partage d’écran et l’escalade en plusieurs parties ne sont pas réalisables en mode natif, mais ils sont pris en charge par le biais de l’escalade d’interopérabilité.

#### <a name="interop-escalation-experiences"></a>Expériences d’escalade d’interopérabilité

L’escalade d’interopérabilité consiste à compléter les fonctionnalités d’interopérabilité natives par des escalades managées vers des réunions. Les réunions offrent des expériences riches à la disposition de quiconque, quel que soit le client qu’ils ont.

Lorsque l’escalade d’interopérabilité est déclenchée par l’utilisateur Teams, une réunion Teams est créée. Lorsqu’elle est déclenchée par l’utilisateur Skype Entreprise, une réunion Skype Entreprise est créée. Dans les deux cas, la réunion créée est une réunion **Meet now** , qui n’est pas répercutée dans le calendrier de l’utilisateur.

L’autre partie reçoit le lien de participation à la réunion via la conversation d’interopérabilité et les jointures en cliquant sur ce lien. Si l’utilisateur Skype Entreprise dispose d’un compte Teams et qu’il est invité par l’utilisateur Teams, il rejoint la réunion authentifiée. Dans le cas contraire, ils se joindront en tant que participant anonyme. À l’inverse, les utilisateurs Teams ont presque toujours un compte Skype Entreprise et un client Skype Entreprise qu’ils peuvent utiliser pour participer à une réunion Skype Entreprise en tant que participant authentifié, mais ils peuvent également participer en tant que participant anonyme, par exemple à l’aide de l’application Réunion Skype.

Une fois que les parties ont rejoint la réunion, elles peuvent effectuer toutes les activités prises en charge dans les réunions, telles que le partage de bureau ou de contenu, le partage ou le transfert de fichiers, l’ajout d’autres participants, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalade d’interopérabilité à partir de Skype Entreprise

L’escalade d’interopérabilité et d’interopérabilité à partir de Skype Entreprise a été mise à jour dans la build de juillet 2019 de la R2R mensuelle. Auparavant, Skype Entreprise n’étaient pas au fait que la partie distante utilisait Teams. Elle a seulement supposé qu’à partir de la signalisation reçue après l’établissement d’une session.

Lorsque la signalisation indique que la réponse provient (ou par le biais) de la passerelle d’interopérabilité, elle affiche la barre d’affaires jaune (bannière) indiquant que l’autre partie n’utilise pas Skype Entreprise. Avec l’évolution de notre service, cela a entraîné des faux positifs où Skype Entreprise utilisateurs voyaient la barre métier lorsqu’ils étaient connectés au service Messagerie vocale infonuagique ou à d’autres services vocaux cloud, plutôt qu’à un utilisateur **Teams Uniquement** réel.

Pour éviter ces faux positifs, le service de présence informe maintenant le client Skype Entreprise lorsque l’autre partie est un utilisateur réel **Teams Uniquement**. Cela permet à Skype Entreprise de savoir qu’il doit créer une conversation d’interopérabilité avant sa création et que la fenêtre de conversation doit être spécifique à l’interopérabilité.

![Capture d’écran du message Teams pour créer une conversation d’interopérabilité avec un utilisateur Skype Entreprise.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si l’utilisateur Skype Entreprise souhaite partager son bureau, par exemple, il est informé que nous allons démarrer une réunion et qu’il est guidé tout au long des étapes.

![Capture d’écran du message Teams pour démarrer la réunion avec un utilisateur Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Pendant ce temps, l’utilisateur Teams reçoit un message de conversation entrant avec le lien vers la réunion et est guidé pour participer.

Cette escalade vers une réunion Skype Entreprise est disponible pour les appels et conversations fédérés in-tenant et interlocataires. Il est activé par défaut et il n’existe aucun paramètre que l’administrateur doit provisionner.

#### <a name="interop-escalation-from-teams"></a>Escalade d’interopérabilité à partir de Teams

L’escalade d’interopérabilité entre Teams et une réunion Teams est désormais disponible lorsque l’utilisateur Teams sélectionne le bouton de partage de bureau dans un thread d’interopérabilité dans le locataire avec un utilisateur Skype Entreprise ou dans un thread de fédération d’interopérabilité entre locataires. L’escalade d’interopérabilité est prise en charge à partir d’une conversation de conversation 1:1 ou d’un appel 1:1.

La fonctionnalité est prise en charge dans le client de bureau Teams pour Windows, dans le client de bureau Teams pour Mac et dans le client web Teams sur les navigateurs où le partage de contenu est pris en charge, tout en communiquant avec n’importe quelle version du client Skype Entreprise.

Dans les threads d’interopérabilité et dans les threads d’interopérabilité de fédération, l’utilisateur Teams dispose désormais des contrôles (bouton) pour démarrer le partage de contenu. Lorsque l’utilisateur Teams sélectionne le bouton, un menu supplémentaire lui est présenté pour l’informer que pour partager du contenu, il doit démarrer une réunion Teams.

Si les utilisateurs étaient dans un appel, le menu les avertit également que leur appel actuel entre Teams et Skype Entreprise sera arrêté lorsqu’ils seront placés dans une réunion Teams. S’il choisit, il peut avertir l’utilisateur Skype Entreprise avant d’accepter.

![Capture d’écran du message Teams pour partager une réunion avec un utilisateur Skype Entreprise.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Une fois acceptés, ils sont placés dans la réunion Teams ; ils doivent commencer à partager à partir du plateau de partage dans la réunion.

Pendant ce temps, l’utilisateur Skype Entreprise reçoit un message de conversation entrant avec le lien vers la réunion et est guidé pour participer.

Cette escalade vers une réunion Teams est disponible pour les appels et conversations fédérés in-tenant et interlocataires. Il est activé par défaut et il n’existe aucun paramètre que l’administrateur doit provisionner. Toutefois, elle est désactivée pour l’utilisateur si l’administrateur se définit ``-AllowPrivateMeetNow`` sur ``CsTeamsMeetingPolicy`` ``$false``.

Après avoir examiné cet article, consultez [Choisir votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [conseils sur la migration et l’interopérabilité](./migration-interop-guidance-for-teams-with-skype.md), [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md) et [Définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md) pour plus d’informations sur l’implémentation. Nous vous recommandons également la vidéo suivante : [Vidéo : Gérer la coexistence et l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Détails techniques de Teams et de la coexistence Skype Entreprise

Les sections suivantes récapitulent le comportement qui peut être rencontré lors de l’exécution de Teams et Skype Entreprise clients dans la même organisation, quel que soit le mode et la méthode de mise à niveau utilisés :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Interopérabilité par rapport aux threads de conversation natifs](#interop-versus-native-conversation-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)

### <a name="meetings"></a>Réunions

Quel que soit leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion auquel ils sont invités, qu’il s’agisse de Skype Entreprise ou teams.  Toutefois, les utilisateurs doivent rejoindre la réunion avec un client correspondant qui correspond au type de réunion :

- Si la réunion est une réunion Teams, tous les participants (qu’il s’agisse d’utilisateurs TeamsOnly, Islands ou Skype Entreprise) utilisent le client Teams pour participer à la réunion. Si Teams n’est pas installé, l’utilisateur est dirigé vers le web lors d’une tentative de participation à une réunion.

- Si la réunion est une réunion Skype Entreprise, tous les participants (qu’il s’agisse d’utilisateurs TeamsOnly, Islands ou Skype Entreprise) utilisent le client Skype Entreprise pour participer à la réunion. Si le client Skype Entreprise n’est pas installé, l’utilisateur est dirigé vers le web pour le rejoindre via l’application Réunion Skype. 

  Dans certains cas, les participants en mode TeamsOnly ne peuvent participer qu’à Skype Entreprise réunions à l’aide de Application Web Skype Entreprise ou de l’application Réunions Skype en tant qu’utilisateur anonyme. Finalement, ce cas sera vrai pour tous les utilisateurs en mode TeamsOnly. Pour plus d’informations, consultez [Skype Entreprise mise hors service en ligne](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Lors de l’organisation de réunions, le type de réunion qui est planifié est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode d’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Toutes les réunions planifiées dans Teams. Skype Entreprise complément n’est pas disponible dans Outlook. |
| SfbWithTeamsCollab, SfbOnly | Toutes les réunions planifiées dans Skype Entreprise. Le complément Teams n’est pas disponible dans Outlook. |
| Île | Par défaut, les réunions peuvent être planifiées dans Skype Entreprise ou Teams. Les deux compléments sont disponibles dans Outlook. Toutefois, vous pouvez éventuellement exiger que les utilisateurs des îles planifient toujours des réunions dans Teams en leur affectant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interopérabilité

Comme décrit ci-dessus dans [l’interopérabilité de Teams et de Skype Entreprise](#interoperability-of-teams-and-skype-for-business), Teams prend en charge l’interopérabilité avec Skype Entreprise dans certains scénarios. La communication d’interopérabilité fait référence à une conversation ou un appel entre un utilisateur Skype Entreprise et un utilisateur Teams.  La communication d’interopérabilité n’est possible qu’entre deux utilisateurs ; La conversation/appel multiparte ou l’ajout d’utilisateurs supplémentaires n’est pas pris en charge.

Une conversation ou un appel d’interopérabilité entre deux utilisateurs est créé lorsque chacun des éléments suivants est vrai :

- Un utilisateur utilise Teams et l’autre utilise Skype Entreprise.

- Le mode du destinataire de la communication initiale est NOT Islands (sinon, la communication atterrit dans le même client) si les deux utilisateurs sont dans la même organisation. Dans les scénarios fédérés, l’utilisateur expéditeur utilise Teams et le destinataire n’est pas en mode TeamsOnly.

- L’utilisateur Teams n’a PAS non plus de compte Skype Entreprise hébergé localement.

Dans la communication d’interopérabilité, la conversation est en texte brut uniquement. En outre, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la conversation d’interopérabilité elle-même*. Toutefois, les utilisateurs d’une conversation d’interopérabilité peuvent facilement obtenir un partage de fichiers et/ou d’écran en créant une réunion à la demande, à partir de la conversation d’interopérabilité, comme décrit ci-dessous :

- Si l’utilisateur Teams tente de partager son écran, une réunion Teams à la demande est automatiquement créée et un lien d’invitation vers cette réunion est envoyé au client de l’utilisateur Skype Entreprise. En cliquant sur le lien, l’utilisateur Skype Entreprise ouvre Teams et rejoint la réunion. Les deux utilisateurs sont maintenant dans une réunion Teams et peuvent partager en fonction des besoins.

- Si l’utilisateur Skype Entreprise utilise un client à partir de 2018 ou une version ultérieure et tente de partager du contenu, une réunion Skype Entreprise à la demande est automatiquement créée et un lien d’invitation vers cette réunion est envoyé au client de l’utilisateur Teams. En cliquant sur le lien, l’utilisateur Teams tente de rejoindre la réunion Skype Entreprise. Si l’utilisateur Teams a installé le client Skype Entreprise, il s’ouvre et l’utilisateur est invité à se connecter (s’il n’est pas déjà connecté).  Si l’utilisateur Teams n’a pas installé le client Skype Entreprise, il est invité à utiliser la version web. Une fois que les deux utilisateurs sont connectés, ils participent à une réunion Skype Entreprise et peuvent partager en fonction des besoins.

### <a name="interop-versus-native-conversation-threads"></a>Interopérabilité par rapport aux threads de conversation natifs

Étant donné que les communications d’interopérabilité ne prennent pas en charge toutes les fonctionnalités de la conversation Teams native, le client Teams gère des threads de conversation distincts pour la communication Teams-à-Teams et Teams-à-Skype Entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : les threads d’interopérabilité peuvent être différenciés d’un thread Teams natif normal en :

- Absence de contrôles pour le texte enrichi, le partage de fichiers/écran, l’impossibilité d’ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible, montrant un « S » pour Skype Entreprise.

Ces différences sont illustrées dans les captures d’écran suivantes :

Conversation teams-à-teams native avec le test G3 de l’utilisateur

![Diagramme montrant une conversation Teams-à-Teams native.](media/teams-upgrade-native-thread.png)

Conversation d’interopérabilité avec le même test utilisateur G3

![Diagramme montrant une conversation Teams-à-Teams d’interopérabilité.](media/teams-upgrade-interop-thread.png)

Une fois qu’un thread de conversation est créé, son type ne change jamais. Une fois créé, un thread d’interopérabilité dans Teams est toujours acheminé vers le client Skype Entreprise de l’utilisateur cible. Un thread natif est toujours acheminé vers le client Teams de l’utilisateur cible.  Si le mode utilisateur d’un destinataire change, les threads Teams existants pour cet utilisateur ne fonctionnent plus et une note s’affiche sur cette conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.

![Diagramme montrant une conversation avec un utilisateur Skype Entreprise mis à niveau.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est ensuite publiée pour que d’autres utilisateurs voient.  Skype Entreprise et Teams étant des services distincts avec des clients distincts, chaque service a son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans Teams et dans Skype Entreprise Online.  Cela permet à un service de publier potentiellement la présence de l’utilisateur à partir de l’autre service si nécessaire.

Le comportement de publication de présence est basé sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence Teams pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur se trouve dans l’un des modes de Skype Entreprise, tous les autres utilisateurs voient Skype Entreprise présence pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur est en mode Îles, la présence publiée dans Skype Entreprise et Teams étant indépendante, la présence affichée aux utilisateurs au sein de la même organisation dépend du client de l’autre utilisateur. Les utilisateurs des organisations fédérées verront la présence de cet utilisateur en fonction de leur activité Skype Entreprise, car le trafic fédéré vers un utilisateur en mode Îles arrive dans Skype Entreprise.

Par exemple, supposons que l’utilisateur A est en mode Îles. Si l’utilisateur A est actif dans Teams mais qu’il n’est pas connecté à Skype Entreprise, d’autres utilisateurs voient l’utilisateur A comme étant actif à partir de son client Teams, mais dans leur client Skype Entreprise ils voient l’utilisateur A comme étant hors connexion. Il s’agit d’une opération de conception, car l’utilisateur A ne peut pas être atteint s’il n’exécute pas le client.


### <a name="federation"></a>Fédération

La fédération de Teams vers un autre utilisateur à l’aide de Skype Entreprise exige que l’utilisateur Teams soit hébergé en ligne dans Skype Entreprise. TeamsUpgradePolicy régit le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les scénarios du même locataire, sauf en mode Îles. Lorsque les destinataires sont en mode Îles :

- Les conversations et les appels lancés à partir de Teams arrivent dans Skype Entreprise si le destinataire se trouve dans un locataire fédéré.
- Les conversations et les appels lancés à partir de Teams arrivent dans Teams si le destinataire se trouve dans le même locataire.
- Les conversations et les appels lancés à partir de Skype Entreprise arrivent toujours dans Skype Entreprise.

Une conversation fédérée peut être un thread natif ou un thread d’interopérabilité. Consultez [Interop par rapport aux threads de conversation natifs](#interop-versus-native-conversation-threads).

- Si le récepteur et l’expéditeur sont tous les deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez [l’expérience de conversation native pour les utilisateurs externes (fédérés) dans Teams](native-chat-for-external-users.md).

- Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’interopérabilité avec des messages texte uniquement. L’interface utilisateur expose les conversations fédérées de la même manière que les threads d’interopérabilité du même locataire, sauf qu’il existe une note indiquant que l’utilisateur est externe.

Pour plus d’informations, consultez [Gérer l’accès externe dans Microsoft Teams](manage-external-access.md) et l’expérience de [conversation native pour les utilisateurs externes (fédérés) dans Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contacts

Teams et Skype Entreprise ont des listes de contacts distinctes. Cela signifie que les ajouts de contacts, la suppression et les modifications apportées dans un système ne sont pas synchronisés avec l’autre système. Toutefois, les contacts de Skype Entreprise sont automatiquement copiés vers Teams lorsque l’un des deux événements spécifiques se produit :

- Pour n’importe quel utilisateur Skype Entreprise Online, la première fois qu’il se connecte à Teams, les contacts de Skype Entreprise sont copiés vers Teams.  Ce comportement n’est pas disponible pour les utilisateurs disposant d’un compte local dans Skype Entreprise Server.

- Une fois qu’un utilisateur est mis à niveau vers TeamsOnly (via l’affectation de TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype Entreprise sont fusionnés avec des contacts existants déjà dans Teams. Ce comportement se produit si l’utilisateur a été déplacé vers TeamsOnly à partir d’un emplacement local ou en ligne.

Dans les deux cas, le transfert de contacts d’Skype Entreprise vers Teams est asynchrone, ce qui peut prendre quelques minutes avant que les contacts apparaissent dans Teams. Les deux événements ci-dessus déclenchent la copie.

### <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Utilisation du service de migration de réunion (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
