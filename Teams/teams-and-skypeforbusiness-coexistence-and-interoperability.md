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
ms.openlocfilehash: f91297a0b2fa5178195b10b61817cc11a30acfbc
ms.sourcegitcommit: 303579b3ecd4e0af43710d4b078610f63e9d0eca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "68853362"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité

![Diagramme du parcours de mise à niveau, en mettant l’accent sur l’étape Définition du projet.](media/upgrade-banner-project-definition.png "Étapes du parcours de mise à niveau, en mettant l’accent sur l’étape Définition du projet")

Cet article fait partie de la phase De définition de projet de votre parcours de mise à niveau. Terminez une fois que vous avez créé une coalition de parrainage et une équipe de projet, et que vous avez défini l’étendue, les objectifs et le plan de votre projet. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Enrôlé les parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)

Si votre organisation utilise Skype Entreprise aujourd’hui et que vous commencez à utiliser Teams avec Skype Entreprise, ou si vous commencez à effectuer une mise à niveau vers Teams, il est important de comprendre comment les deux applications coexistent, quand et comment elles interagissent, et comment gérer la migration de vos utilisateurs jusqu’à leur éventuelle mise à niveau à partir de Skype Entreprise  à Teams.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur [la coexistence et l’interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop).
>
> En outre, vous pouvez nous rejoindre pour des ateliers interactifs en direct dans lesquels nous partagerons des conseils, des meilleures pratiques et des ressources conçus pour lancer la planification et l’implémentation de la mise à niveau.
>
> Rejoignez d’abord [planifier votre session de mise à niveau](./upgrade-workshops-landing-page.yml) pour commencer.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Vue d’ensemble de la coexistence de Teams et Skype Entreprise

Depuis la mise hors service de Skype Entreprise Online, tous les utilisateurs d’une organisation en ligne pure (autrement dit, une organisation qui n’a pas de déploiement local de Skype Entreprise) ont un mode de coexistence TeamsOnly. Le mode TeamsOnly garantit que les utilisateurs disposent de toutes les fonctionnalités de Teams. Toutefois, les organisations avec un déploiement local de Skype Entreprise Server peuvent avoir des utilisateurs qui sont toujours hébergés localement ; ces utilisateurs ne peuvent pas être TeamsOnly. Les utilisateurs disposant d’un compte Skype Entreprise Server local peuvent avoir n’importe quel mode de coexistence *autre que TeamsOnly.* Les sections suivantes décrivent les modes de coexistence disponibles avant que vous ne décidiez de mettre à niveau des utilisateurs Skype Entreprise locaux vers TeamsOnly, ainsi que les fonctionnalités offertes par chaque mode. En outre, les sections décrivent l’interopérabilité (interopérabilité) qui se produit entre les utilisateurs sur Skype Entreprise clients et les utilisateurs sur les clients Teams, et comment l’interopérabilité est affectée par le mode de coexistence choisi.

Teams offre des fonctionnalités de collaboration, de conversation, d’appel et de réunion.  La fonctionnalité de conversation, d’appel et de réunion était également historiquement disponible dans Skype Entreprise. Selon la configuration que vous choisissez lors de la fourniture de Teams, ces fonctionnalités peuvent chevaucher les fonctionnalités fournies par Skype Entreprise pour un utilisateur donné. Le mode de coexistence par défaut pour les utilisateurs locaux est Islands. Le mode Îles permet à l’utilisateur d’exécuter Teams en même temps que Skype Entreprise avec des fonctionnalités similaires disponibles dans les deux clients, autrement dit, les fonctionnalités se chevauchent. Toutefois, un utilisateur peut se voir attribuer d’autres modes de coexistence pour éviter que cette fonctionnalité ne se chevauche pour l’utilisateur, auquel cas l’interopérabilité entre Teams et Skype Entreprise est disponible. Par exemple, si vous avez des ressources locales importantes Skype Entreprise Server avec un déploiement Téléphonie –  Grandes entreprises complexe, mais que vous souhaitez que vos utilisateurs profitent de réunions modernes le plus rapidement possible, vous pouvez évaluer à l’aide de la Skype Entreprise  avec le mode Collaboration teams et Réunions, également appelé [Réunions d’abord](meetings-first.md).

Nous vous recommandons de passer en revue les modes de coexistence suivants pour vous aider à déterminer le chemin qui convient le mieux à votre organisation.

> [!Important]
> Les modes de coexistence continuent d’exister après la mise hors service de Skype Entreprise Online, mais les utilisateurs hébergés en ligne ne peuvent avoir qu’un mode TeamsOnly. Il n’est plus possible d’attribuer un mode autre que TeamsOnly à un utilisateur hébergé en ligne.  Comme c’était le cas avant la mise hors service de Skype Entreprise Online, les utilisateurs hébergés localement peuvent se voir attribuer n’importe quel mode *autre que TeamsOnly*.


### <a name="teams-only"></a>Teams uniquement

**Teams Only** est le seul mode disponible pour les utilisateurs en ligne purs. Un utilisateur **Teams uniquement** (dans le passé, parfois appelé utilisateur *mis à niveau*) a accès à toutes les fonctionnalités de Teams et peut continuer à communiquer avec tous les autres utilisateurs (qu’ils soient dans la même organisation ou externe) qui utilisent encore Skype Entreprise (à condition que les Skype Entreprise utilisateurs ne soient pas en mode **Îles**). **Teams Seuls** les utilisateurs reçoivent des conversations et des appels entrants dans Teams, et planifient également des réunions dans Teams. Ils ne peuvent pas lancer de conversations ou d’appels ou planifier des réunions dans Skype Entreprise. 

**Teams Seuls** les utilisateurs peuvent conserver l’Skype Entreprise client pour participer aux réunions Skype Entreprise qu’ils ont déjà ou qu’ils peuvent recevoir à l’avenir (c’est-à-dire, de parties externes ou éventuellement d’utilisateurs locaux Skype Entreprise Server de leur propre organisation). *Toutefois, une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online pour un utilisateur Teams uniquement donné, les utilisateurs Teams uniquement peuvent uniquement participer à Skype Entreprise réunions de manière anonyme.* Après le 30 juin 2022, les nouveaux utilisateurs teamsOnly ne seront plus approvisionnés avec l’infrastructure Skype Entreprise Online. Si ces utilisateurs sont invités à une réunion Skype Entreprise, ils doivent participer anonymement. Après octobre 2022, les utilisateurs déplacés de l’environnement local vers le cloud (autrement dit, ils deviennent TeamsOnly) ne seront plus approvisionnés avec l’infrastructure Skype Entreprise Online.  Si ces utilisateurs sont invités à une réunion Skype Entreprise, ils doivent également participer anonymement.

Dès que votre organisation est prête pour certains ou tous les utilisateurs à utiliser Teams comme seul outil de communication et de collaboration, mettez à niveau ces utilisateurs vers le mode **Teams uniquement** . Si vous effectuez une mise à niveau à partir du mode **Îles** , nous vous conseillons de commencer par saturer l’adoption de Teams dans toute votre organisation avant de commencer le processus de mise à niveau. Cette adoption évite les scénarios de communication rompus en raison du mode **Îles** qui n’assure pas l’interopérabilité.

En mode **Teams uniquement** , Teams est l’application par défaut pour le protocole SIP/Tel. Les liens dans la carte de visite d’un utilisateur dans Outlook pour l’appel ou la conversation sont gérés par Teams.

Pour plus d’informations sur le passage en mode **Teams uniquement** , consultez [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md).

![Capture d’écran du message de confirmation Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype Entreprise client s’exécutant en mode spécial après la mise à niveau de l’utilisateur en tant qu’utilisateur Teams uniquement")


### <a name="islands-mode"></a>Mode Îles

En mode **Îles**, les utilisateurs peuvent exécuter Teams avec Skype Entreprise en tant que deux solutions distinctes qui offrent des fonctionnalités similaires et qui se chevauchent. Les fonctionnalités incluent la présence, la conversation, les appels et les réunions. Les utilisateurs de Teams peuvent également tirer parti des nouvelles fonctionnalités de collaboration telles que les équipes et les canaux, l’accès aux fichiers dans Microsoft 365 et les applications.

Dans ce mode de coexistence, chacune des applications clientes fonctionne comme un îlot distinct. Skype Entreprise parle à Skype Entreprise et Teams à Teams. Les utilisateurs sont censés exécuter les deux clients à tout moment et peuvent communiquer en mode natif dans le client à partir duquel la communication a été démarrée. Par conséquent, il n’est pas nécessaire d’utiliser l’interopérabilité en mode **Îles** .

Pour éviter une expérience de Skype Entreprise confuse ou régressée, le Skype Entreprise gère les intégrations suivantes qui ne sont pas gérées en mode Teams **Islands** :

- Communications externes (fédérées).
- Services vocaux RTC et applications vocales, intégration d’Office.
- Contrôles HID pour les périphériques USB.
- Plusieurs autres intégrations.

Téléphonie Microsoft Teams System n’est pas pris en charge dans Teams en mode **Îles**. 

> [!Important]
>  - En mode **Îles**, tous les messages et appels des utilisateurs fédérés (personnes extérieures à votre organisation) sont remis à Skype Entreprise. Après la mise à niveau vers le mode **Teams uniquement** , tous les messages et appels en provenance de l’extérieur de votre organisation sont remis à Teams.
>  - Vous pouvez exiger que les utilisateurs des îles planifient toujours des réunions dans Teams en leur affectant une instance de TeamsMeetingPolicy avec le PreferredMeetingProviderForIslandsMode=Teams. Cela garantit que tous les utilisateurs planifient des réunions à l’aide de Teams, ce qui prend en charge la connexion authentifiée et la participation aux réunions pour tous les utilisateurs de l’organisation, que l’utilisateur soit TeamsOnly ou utilise toujours Skype Entreprise Server. En revanche, après la mise hors service de l’infrastructure Skype Entreprise Online héritée pour les organisations hybrides à partir d’octobre 2022, les utilisateurs de TeamsOnly ne pourront participer qu’à Skype Entreprise réunions de manière anonyme.


### <a name="skype-for-business-only"></a>Skype Entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype Entreprise(et non Teams) pour les fonctionnalités de conversation, de réunion et d’appel, et ils n’utilisent pas Teams pour les équipes et les canaux. Ce mode est disponible dès aujourd’hui. Toutefois, dans l’implémentation actuelle, les équipes et les canaux ne sont pas automatiquement désactivés pour l’utilisateur. Pour ce faire, utilisez la stratégie d’installation de l’application pour masquer les équipes et les fichiers.

Ce mode peut être utilisé avant de démarrer un déploiement managé de Teams pour empêcher les utilisateurs de commencer à utiliser Teams avant d’avoir une préparation intégrée. Ce mode est également un moyen d’activer la participation authentifiée aux réunions Teams pour Skype Entreprise utilisateurs, à condition que les utilisateurs disposent d’une licence pour Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Entreprise avec Collaboration Teams

Utilisez ce mode pour introduire Teams dans votre environnement tout en continuant à utiliser votre investissement existant dans Skype Entreprise. Laissez Skype Entreprise inchangé pour les fonctionnalités de conversation, d’appel et de réunion. Ajouter des fonctionnalités de collaboration Teams :

- Équipes et canaux.
- Accès aux fichiers dans Microsoft 365 ou Office 365.
- Applications. Fonctionnalités de communication Teams : conversation privée, appel et planification de réunions.

Les conversations privées Teams, les appels et la planification de réunions sont désactivés par défaut dans ce mode.

Les organisations commençant par Skype Entreprise Server localement ont ce mode comme alternative au mode **Îles** si elles souhaitent offrir à leurs utilisateurs l’interopérabilité et la prévisibilité de leurs communications pendant la migration. Ce mode fournit également une chronologie prévisible pour leur mise à niveau vers Teams (par opposition à la saturation de l’adoption en mode **Îles** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Entreprise avec Teams Collaboration et Réunions, également appelées Réunions d’abord

Dans ce mode, la fonctionnalité de conversation privée et d’appel reste sur Skype Entreprise tandis que Teams est utilisé pour la planification et la conduite de réunions, ainsi que pour la collaboration à l’aide de conversations basées sur des canaux.  Ce mode de coexistence permet d’accélérer la disponibilité des fonctionnalités de réunion et de collaboration Teams dans votre organisation et permet à vos utilisateurs de tirer parti de l’expérience de réunion Teams supérieure :

- Grande qualité.
- Transcription et traduction.
- Flou en arrière-plan.
- Expérience utilisateur supérieure sur toutes les plateformes, y compris les appareils mobiles et les navigateurs.

Teams et Skype Entreprise bénéficier d’une gamme de fonctionnalités « mieux ensemble », telles que le rapprochement de présence, la conservation/non-conservation automatique et la prise en charge des appareils HID dans les deux applications. Il est possible de masquer les équipes et les canaux, si vous le souhaitez, à l’aide de la stratégie de configuration des applications Teams.

Ce mode de coexistence est particulièrement utile pour les organisations avec Skype Entreprise déploiements locaux avec Téléphonie –  Grandes entreprises. Ces organisations mettent probablement un certain temps à mettre à niveau vers Teams et souhaitent tirer parti des réunions Teams supérieures dès que possible.

> [!NOTE]
> À compter d’octobre 2022, ce mode est recommandé pour tous les utilisateurs locaux qui étaient précédemment affectés **Skype Entreprise uniquement** ou **Skype Entreprise avec les modes collaboration Teams**. Ce mode offre les mêmes fonctionnalités que les deux autres, à l’exception des nouvelles réunions planifiées par l’utilisateur seront des réunions Teams au lieu de Skype Entreprise réunions. Cela garantit que les utilisateurs planifient leurs réunions en tant que réunions Teams, ce qui prend en charge la connexion authentifiée et la participation aux réunions pour tous les utilisateurs de l’organisation, que l’utilisateur soit TeamsOnly ou utilise toujours Skype Entreprise Server.  En revanche, à mesure que Microsoft met hors service l’infrastructure héritée Skype Entreprise Online, les utilisateurs de TeamsOnly ne pourront plus s’authentifier lorsqu’ils rejoignent Skype Entreprise réunions, mais ils peuvent toujours participer de manière anonyme. Pour plus d’informations, consultez [Ce à quoi s’attendre après la mise hors service](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

> [!TIP]
> Pour identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous souhaitez activer dans Teams lorsque Skype Entreprise est toujours en cours d’utilisation, tirez parti de [l’Assistant Mise à niveau de Skype vers Teams](https://aka.ms/SkypeToTeamsWizard).

Pour plus d’informations sur les modes de coexistence, les prérequis et la gestion, consultez [Guide de migration et d’interopérabilité pour les organisations utilisant Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md) et [Définition de vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md).

|Icône de point de décision |Définition de l’icône |Description |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quel(s) mode(s) de coexistence correspond le mieux aux besoins de votre organisation et des utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour votre parcours de mise à niveau.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité de Teams et de Skype Entreprise

L’interopérabilité est la possibilité pour Teams et Skype Entreprise utilisateurs de la même organisation de communiquer entre Teams et Skype Entreprise.

L’interopérabilité est régie par le mode de coexistence (également appelé mode de mise à niveau) du récepteur. Il n’y a pas d’interopérabilité lorsque le récepteur est en mode **Îles** .

> [!Note]
> Lorsqu’ils sont déployés dans n’importe quel mode de coexistence à l’exception des **îles**, Teams et Skype Entreprise peuvent [interagir](#interoperability-of-teams-and-skype-for-business), ce qui permet aux utilisateurs de discuter et de s’appeler les uns avec les autres, et de garantir que les communications restent fluides au sein de votre organisation pendant votre parcours de mise à niveau vers Teams. Les modes de coexistence régissent l’interopérabilité. Le mode de coexistence du récepteur détermine si l’interopérabilité sera disponible. Par exemple, si le récepteur est dans un mode dans lequel la conversation n’est disponible que dans un seul client (par exemple, Teams), l’interopérabilité de conversation est généralement disponible si l’initiateur utilise l’autre client (dans ce cas, Skype Entreprise) pour démarrer la conversation. En revanche, si le récepteur est dans le mode dans lequel la conversation est disponible dans les deux clients (mode Îles), l’interopérabilité ne sera pas disponible pour la conversation. Le message est reçu par le destinataire dans le même client que celui dans lequel l’initiateur a démarré la conversation. Par conséquent, une communication correcte en mode **Îles** nécessite une saturation de l’adoption de Teams ; autrement dit, tous les utilisateurs utilisent et surveillent activement les deux clients.

> [!Note]
> **Pour disposer de la dernière expérience de coexistence, la version du client doit être le dernier client disponible dans le canal de déploiement Office de l’utilisateur.**

#### <a name="native-interop-and-interop-escalation"></a>Interopérabilité et escalade d’interopérabilité natives

Il existe deux types d’expériences d’interopérabilité : l’escalade native et l’escalade d’interopérabilité.

- Une expérience _d’interopérabilité native_ se produit dans le client que l’utilisateur utilise actuellement. Un utilisateur se trouve dans le client Skype Entreprise, l’autre dans Teams. Une expérience d’interopérabilité native ne les amène pas à un autre client pour communiquer. Les utilisateurs pourront mener leur conversation dans le client qu’ils utilisent actuellement. Les expériences d’interopérabilité natives sont une conversation et un appel.
- Une expérience _d’escalade_ d’interopérabilité signifie que dans le cadre de l’aide aux utilisateurs à effectuer une action avancée (comme le partage de leur bureau), le client facilite la création d’une réunion que les utilisateurs peuvent rejoindre pour poursuivre l’expérience de cette réunion. La réunion est créée sur la plateforme de l’initiateur de l’action. L’utilisateur ou les utilisateurs qui ne sont pas sur cette plateforme reçoivent un lien de participation à la réunion. Quand ils cliquent sur ce lien, ils sont joints à la réunion dans un client compatible (navigateur, application web ou client complet, selon la configuration). L’escalade d’interopérabilité à partir de Skype Entreprise nécessite un client récent. L’escalade d’interopérabilité à partir de Teams est désormais disponible. Les deux sont pris en charge dans les expériences d’interopérabilité dans le locataire et pour les communications fédérées entre locataires.

#### <a name="native-interop-experiences"></a>Expériences d’interopérabilité natives

En fonction des modes de coexistence attribués aux utilisateurs (comme décrit précédemment), les expériences d’interopérabilité native suivantes sont disponibles :

Skype Entreprise utilisateurs peuvent discuter en face à face avec les utilisateurs De Teams, et vice versa. Une conversation d’interopérabilité doit passer par une passerelle d’interopérabilité qui fait partie des services cloud Teams (et qui n’existe donc qu’en ligne). Les conversations d’interopérabilité sont en texte brut : le texte enrichi et les émoticônes ne sont pas pris en charge. Les utilisateurs dans Teams et dans Skype Entreprise sont avertis que la conversation est une conversation d’interopérabilité.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype Entreprise utilisateurs peuvent passer des appels vocaux et vidéo en tête-à-tête aux utilisateurs Teams, et les utilisateurs de Teams peuvent faire de même.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Les expériences d’interopérabilité avec des utilisateurs locaux dans une organisation avec un mélange d’utilisateurs locaux et Teams nécessitent que l’environnement local soit en mode hybride avec Teams. Pour plus d’informations, [consultez Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Ces expériences d’interopérabilité sont disponibles pour et entre les utilisateurs auxquels l’un des modes de coexistence suivants est attribué : **Skype Entreprise avec Teams Collaboration**, **Skype Entreprise avec Teams Collaboration et réunions**, **Skype Entreprise uniquement** ou **Teams uniquement**. Il n’existe aucune interopérabilité pour les utilisateurs en mode **Îles** .

#### <a name="native-interop-experience-limitations"></a>Limitations de l’expérience d’interopérabilité native

En raison de la différence entre les protocoles et la technologie, il n’est pas possible de prendre en charge toutes les fonctionnalités en mode natif. Plus précisément, les fonctionnalités suivantes ne sont pas disponibles :

- Markdown, le texte enrichi et le jeu d’émoticône complet ne sont pas pris en charge à partir de Teams ou Skype Entreprise. Les autres fonctionnalités natives de la zone de composition dans les conversations Teams ne sont pas prises en charge.
- Le partage d’écran (partage de bureau ou d’application) entre Teams et Skype Entreprise n’est pas pris en charge en mode natif. Toutefois, elle est prise en charge par le biais de l’escalade d’interopérabilité.
- Les conversations de groupe (conversations à plusieurs parties) dans Teams ne peuvent inclure que des participants qui utilisent Teams.
- Les conversations de messagerie instantanée à plusieurs parties (conversations de groupe) dans Skype Entreprise peuvent inclure uniquement des participants qui utilisent Skype Entreprise. Toutefois, l’escalade d’interopérabilité vers plusieurs parties est disponible à partir de Skype Entreprise.
- L’escalade d’un appel vocal ou vidéo pair à pair en cours vers un appel à plusieurs parties impliquant à la fois Teams et Skype Entreprise utilisateurs n’est pas pris en charge.
- Le transfert de fichiers pour les conversations bi-parties ou les pièces jointes dans les conversations de groupe, de Teams à Skype Entreprise ( et vice versa) ne sont pas pris en charge.
- Il n’existe aucune interopérabilité avec Skype Entreprise conversation permanente.

Pour toutes ces limitations (à l’exception de la conversation permanente), une solution de contournement possible consiste à démarrer une réunion et à inviter l’autre utilisateur à la rejoindre.

Cette solution de contournement est la base de l’escalade d’interopérabilité. En particulier, le partage d’écran et l’escalade vers plusieurs parties ne sont pas réalisables en mode natif, mais ils sont pris en charge via l’escalade d’interopérabilité.

#### <a name="interop-escalation-experiences"></a>Expériences d’escalade d’interopérabilité

L’escalade d’interopérabilité consiste à compléter les fonctionnalités d’interopérabilité natives par des escalades managées vers des réunions. Les réunions offrent des expériences enrichies accessibles à tous, quel que soit le client dont ils disposent.

Lorsque l’escalade d’interopérabilité est déclenchée par l’utilisateur Teams, une réunion Teams est créée. Lorsqu’elle est déclenchée par l’utilisateur Skype Entreprise, une réunion Skype Entreprise est créée. Dans les deux cas, la réunion créée est une réunion **Meet now** , qui n’est pas reflétée dans le calendrier de l’utilisateur.

L’autre partie reçoit le lien de participation à la réunion par le biais d’une conversation d’interopérabilité et rejoint en cliquant sur ce lien. Si l’utilisateur Skype Entreprise a un compte Teams et est invité par l’utilisateur Teams, il rejoint la réunion authentifiée. Sinon, ils participeront en tant que participant anonyme. Les utilisateurs Teams ont presque toujours un compte Skype Entreprise et un client Skype Entreprise qu’ils peuvent utiliser pour participer à une réunion Skype Entreprise en tant que participant authentifié, mais ils peuvent également participer en tant que participant anonyme, par exemple à l’aide de l’application Réunion Skype.

Une fois que les parties ont rejoint la réunion, elles peuvent effectuer toute activité prise en charge dans les réunions, comme le partage de contenu ou de bureau, le partage ou le transfert de fichiers, l’ajout d’autres participants, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalade d’interopérabilité à partir de Skype Entreprise

L’interopérabilité et l’escalade d’interopérabilité à partir de Skype Entreprise ont été mises à jour dans la version de juillet 2019 du C2R mensuel. Auparavant, Skype Entreprise ne savait pas à l’avance que la partie distante utilisait Teams. Il n’a supposé que de la signalisation reçue après une session a été établie.

Lorsque la signalisation indique que la réponse provient de (ou via) la passerelle d’interopérabilité, elle affiche la barre professionnelle jaune (bannière) indiquant que l’autre partie n’utilise pas Skype Entreprise. Avec l’évolution de notre service, cela a entraîné des faux positifs où Skype Entreprise utilisateurs voyaient la barre métier lorsqu’ils étaient connectés au service Messagerie vocale infonuagique ou à d’autres services vocaux cloud, plutôt qu’à un utilisateur **Teams uniquement** réel.

Pour éviter les faux positifs, le service de présence informe désormais le client Skype Entreprise lorsque l’autre partie est un utilisateur **teams uniquement** réel. Cela permet à Skype Entreprise de créer une conversation d’interopérabilité et à la fenêtre de conversation d’être spécifique à l’interopérabilité.

![Capture d’écran du message Teams pour créer une conversation d’interopérabilité avec un utilisateur Skype Entreprise.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si l’utilisateur Skype Entreprise souhaite partager son bureau, par exemple, il est informé que nous allons commencer une réunion et qu’il est guidé tout au long des étapes.

![Capture d’écran du message Teams pour commencer la réunion avec un utilisateur Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Pendant ce temps, l’utilisateur Teams reçoit un message de conversation entrant avec le lien vers la réunion et est guidé pour participer.

Cette escalade vers une réunion Skype Entreprise est disponible pour les appels et conversations fédérés interlocataires et interlocataires. Il est activé par défaut et il n’y a aucun paramètre que l’administrateur doit provisionner.

#### <a name="interop-escalation-from-teams"></a>Escalade d’interopérabilité à partir de Teams

L’escalade d’interopérabilité de Teams vers une réunion Teams est désormais disponible lorsque l’utilisateur Teams sélectionne le bouton de partage de bureau dans un thread d’interopérabilité dans le locataire avec un utilisateur Skype Entreprise ou dans un thread de fédération interlocataire. L’escalade d’interopérabilité est prise en charge à partir d’une conversation 1:1 ou d’un appel 1:1.

La fonctionnalité est prise en charge dans le client de bureau Teams pour Windows, dans le client de bureau Teams pour Mac et dans le client web Teams sur les navigateurs où le partage de contenu est pris en charge, tout en communication avec n’importe quelle version du client Skype Entreprise.

Dans les threads d’interopérabilité et dans les threads d’interopérabilité de fédération, l’utilisateur Teams dispose désormais des contrôles (bouton) pour démarrer le partage de contenu. Lorsque l’utilisateur Teams sélectionne le bouton, un menu supplémentaire l’informe que pour partager du contenu, il doit démarrer une réunion Teams.

Si les utilisateurs étaient dans un appel, le menu les avertit que leur appel actuel entre Teams et Skype Entreprise sera arrêté lorsqu’ils sont placés dans une réunion Teams. S’il le souhaite, il peut avertir l’utilisateur Skype Entreprise avant de l’accepter.

![Capture d’écran du message Teams pour partager une réunion avec un utilisateur Skype Entreprise.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Une fois acceptés, ils sont placés dans la réunion Teams ; ils doivent commencer à partager à partir de la barre de partage dans la réunion.

Pendant ce temps, l’utilisateur Skype Entreprise reçoit un message de conversation entrant avec le lien vers la réunion et est guidé pour participer.

Cette escalade vers une réunion Teams est disponible pour les appels et conversations fédérés interlocataires et interlocataires. Il est activé par défaut et il n’y a aucun paramètre que l’administrateur doit provisionner. Toutefois, elle est désactivée pour l’utilisateur si l’administrateur définit ``-AllowPrivateMeetNow`` dans sur ``$false````CsTeamsMeetingPolicy`` .

Après avoir passé en revue cet article, consultez [Choisir votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Guide de migration et d’interopérabilité](./migration-interop-guidance-for-teams-with-skype.md), [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md) et [Définition de vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md) pour plus d’informations sur l’implémentation. Nous vous recommandons également la vidéo suivante : [Vidéo : Gérer la coexistence et l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Détails techniques de la coexistence de Teams et de Skype Entreprise

Les sections suivantes récapitulent les comportements qui peuvent être rencontrés lors de l’exécution de Teams et Skype Entreprise clients dans la même organisation, quel que soit le mode et la méthode de mise à niveau utilisés :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Interopérabilité et threads de conversation natifs](#interop-versus-native-conversation-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)

### <a name="meetings"></a>Réunions

Quel que soit leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion auquel ils sont invités, qu’il s’agisse d’Skype Entreprise ou de Teams.  Toutefois, les utilisateurs doivent rejoindre la réunion avec un client correspondant qui correspond au type de réunion :

- Si la réunion est une réunion Teams, tous les participants (qu’il s’agisse d’utilisateurs TeamsOnly, Islands ou Skype Entreprise) utilisent le client Teams pour rejoindre la réunion. Si Teams n’est pas installé, l’utilisateur est dirigé vers le web lors de sa tentative de participation à une réunion.

- Si la réunion est une réunion Skype Entreprise, tous les participants (qu’il s’agisse d’utilisateurs TeamsOnly, Islands ou Skype Entreprise) utilisent le client Skype Entreprise pour rejoindre la réunion. Si le client Skype Entreprise n’est pas installé, l’utilisateur est dirigé vers le web pour y participer via l’application Réunion Skype. 

  Dans certains cas, les participants en mode TeamsOnly pourront uniquement rejoindre Skype Entreprise réunions à l’aide de Application Web Skype Entreprise ou de l’application Réunions Skype en tant qu’utilisateur anonyme. Finalement, ce cas sera vrai pour tous les utilisateurs en mode TeamsOnly. Pour plus d’informations, consultez [Skype Entreprise mise hors service en ligne](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Lors de l’organisation de réunions, le type de réunion qui est planifié est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode d’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Toutes les réunions planifiées dans Teams. Skype Entreprise complément n’est pas disponible dans Outlook. |
| SfbWithTeamsCollab, SfbOnly | Toutes les réunions planifiées dans Skype Entreprise. Le complément Teams n’est pas disponible dans Outlook. Envisagez d’utiliser SfbWithTeamsCollabAndMeetings à la place, ce qui permet à tous les utilisateurs, qu’ils soient locaux ou TeamsOnly, d’utiliser Teams pour les réunions.|
| Île | Par défaut, les réunions peuvent être planifiées dans Skype Entreprise ou Teams. Les deux compléments sont disponibles dans Outlook. Toutefois, vous pouvez éventuellement exiger que les utilisateurs des îles planifient toujours des réunions dans Teams en leur affectant une instance de TeamsMeetingPolicy avec le PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interopérabilité

Comme décrit ci-dessus dans [Interopérabilité de Teams et Skype Entreprise](#interoperability-of-teams-and-skype-for-business), Teams prend en charge l’interopérabilité avec Skype Entreprise dans certains scénarios. La communication d’interopérabilité fait référence à une conversation ou un appel entre un utilisateur Skype Entreprise et un utilisateur Teams. La communication d’interopérabilité n’est possible qu’entre deux utilisateurs; La conversation/l’appel ou l’ajout d’utilisateurs supplémentaires n’est pas pris en charge.

Une conversation ou un appel d’interopérabilité entre deux utilisateurs est créé lorsque chacune des conditions suivantes est vraie :

- Un utilisateur utilise Teams et l’autre Skype Entreprise.

- Le mode du destinataire de la communication initiale n’est pas Islands (sinon, la communication atterrirait dans le même client) si les deux utilisateurs se trouvent dans la même organisation. Dans les scénarios fédérés, l’utilisateur qui envoie utilise Teams et le destinataire n’est pas en mode TeamsOnly.

- L’utilisateur Teams n’a PAS non plus de compte Skype Entreprise hébergé localement.

Dans la communication d’interopérabilité, la conversation est en texte brut uniquement. En outre, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la conversation d’interopérabilité elle-même*. Toutefois, les utilisateurs d’une conversation d’interopérabilité peuvent facilement obtenir le partage de fichiers et/ou d’écran en créant une réunion à la demande, à partir de la conversation d’interopérabilité, comme décrit ci-dessous :

- Si l’utilisateur Teams tente de partager son écran, une réunion Teams à la demande est automatiquement créée et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Skype Entreprise. En cliquant sur le lien, l’utilisateur Skype Entreprise ouvre Teams et rejoint la réunion. Les deux utilisateurs sont maintenant dans une réunion Teams et peuvent partager en fonction des besoins.

- Si l’utilisateur Skype Entreprise utilise un client de la version 2018 ou ultérieure et tente de partager du contenu, une réunion Skype Entreprise à la demande est automatiquement créée et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Teams. En cliquant sur le lien, l’utilisateur Teams tente de rejoindre la réunion Skype Entreprise. Si l’utilisateur Teams a installé le client Skype Entreprise, il s’ouvre et l’utilisateur est invité à se connecter (s’il n’est pas déjà connecté).  Si l’utilisateur Teams n’a pas installé le client Skype Entreprise, il est invité à utiliser la version web. Une fois que les deux utilisateurs sont connectés, ils participent à une réunion Skype Entreprise et peuvent partager en fonction des besoins.

### <a name="interop-versus-native-conversation-threads"></a>Interopérabilité et threads de conversation natifs

Étant donné que les communications d’interopérabilité ne prennent pas en charge toutes les fonctionnalités de la conversation Teams native, le client Teams gère des threads de conversation distincts pour la communication Teams-to-Teams et Teams-to-Skype Entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : les threads d’interopérabilité peuvent être différenciés d’un thread Teams natif standard par :

- Manque de contrôles pour le texte enrichi, le partage de fichiers/d’écran, l’impossibilité d’ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible, affichant un « S » pour Skype Entreprise.

Ces différences sont illustrées dans les captures d’écran suivantes :

Une conversation Teams-to-Teams native avec l’utilisateur G3 Test

![Diagramme montrant une conversation Teams-to-Teams native.](media/teams-upgrade-native-thread.png)

Une conversation d’interopérabilité avec le même test utilisateur G3

![Diagramme montrant une conversation interopérabilité de Teams à Teams.](media/teams-upgrade-interop-thread.png)

Une fois qu’un thread de conversation est créé, son type ne change jamais. Une fois créé, un thread d’interopérabilité dans Teams est toujours acheminé vers le client Skype Entreprise de l’utilisateur cible. Un thread natif est toujours acheminé vers le client Teams de l’utilisateur cible.  Si le mode d’un utilisateur destinataire change, les threads Teams existants pour cet utilisateur ne fonctionnent plus et une note s’affiche sur cette conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.

![Diagramme montrant une conversation avec un utilisateur Skype Entreprise mis à niveau.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est ensuite publiée pour que d’autres utilisateurs puissent le voir.  Skype Entreprise et Teams étant des services distincts avec des clients distincts, chaque service a son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans Teams et dans Skype Entreprise Online.  Cela permet à un service de publier éventuellement la présence de l’utilisateur à partir de l’autre service si nécessaire.

Le comportement de publication de présence est basé sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence de Teams pour cet utilisateur, quel que soit le client qu’ils utilisent.

- Si un utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient Skype Entreprise présence de cet utilisateur, quel que soit le client qu’ils utilisent.

- Si un utilisateur est en mode Îles, la présence publiée dans Skype Entreprise et Teams sont indépendantes, de sorte que la présence affichée aux utilisateurs au sein de la même organisation dépend du client de l’autre utilisateur. Les utilisateurs des organisations fédérées verront la présence de cet utilisateur en fonction de leur activité Skype Entreprise, car le trafic fédéré vers un utilisateur en mode Îles arrive dans Skype Entreprise.

Par exemple, supposons que l’utilisateur A est en mode Îles. Si l’utilisateur A est actif dans Teams mais n’est pas connecté à Skype Entreprise, d’autres utilisateurs voient l’utilisateur A comme actif à partir de leur client Teams, mais dans leur Skype Entreprise client, ils verraient l’utilisateur A comme étant hors connexion. Cela est dû à la conception, car l’utilisateur A n’est pas accessible s’il n’exécute pas le client.


### <a name="federation"></a>Fédération

La fédération de Teams vers un autre utilisateur à l’aide de Skype Entreprise nécessite que l’utilisateur Teams soit hébergé en ligne dans Skype Entreprise. TeamsUpgradePolicy régit le routage pour les conversations et les appels fédérés entrants. Le comportement de routage fédéré est le même que pour les scénarios de même locataire, sauf en mode Îles. Lorsque les destinataires sont en mode Îles :

- Les conversations et les appels lancés à partir de Teams atterrissent dans Skype Entreprise si le destinataire se trouve dans un locataire fédéré.
- Les conversations et les appels lancés à partir de Teams arrivent dans Teams si le destinataire se trouve dans le même locataire.
- Les conversations et les appels lancés à partir de Skype Entreprise toujours atterrir dans Skype Entreprise.

Une conversation fédérée peut être un thread natif ou un thread d’interopérabilité. Consultez [Interopérabilité et threads de conversation natifs](#interop-versus-native-conversation-threads).

- Si le destinataire et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation est une expérience de conversation native, qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, consultez [Expérience de conversation native pour les utilisateurs externes (fédérés) dans Teams](native-chat-for-external-users.md).

- Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’interopérabilité avec des messages texte uniquement. L’interface utilisateur expose les conversations fédérées de la même manière que les threads d’interopérabilité du même locataire, sauf qu’une note indique que l’utilisateur est externe.

Pour plus d’informations, consultez [Gérer l’accès externe dans Microsoft Teams](manage-external-access.md) et [Expérience de conversation native pour les utilisateurs externes (fédérés) dans Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contacts

Teams et Skype Entreprise ont des listes de contacts distinctes. Cela signifie que les ajouts, suppressions et modifications de contact effectués dans un système ne sont pas synchronisés avec l’autre système. Toutefois, les contacts de Skype Entreprise sont automatiquement copiés vers Teams lorsque l’un des deux événements spécifiques se produit :

- Pour tout utilisateur Skype Entreprise Online, la première fois qu’il se connecte à Teams, les contacts de Skype Entreprise sont copiés dans Teams. Ce comportement n’est pas disponible pour les utilisateurs disposant d’un compte local dans Skype Entreprise Server.

- Une fois qu’un utilisateur est mis à niveau vers TeamsOnly (via l’attribution de TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype Entreprise sont fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si l’utilisateur a été déplacé vers TeamsOnly à partir d’un emplacement local ou en ligne.

Dans les deux cas, le transfert de contacts d’Skype Entreprise vers Teams est asynchrone, de sorte qu’il peut s’agir de quelques minutes avant que les contacts n’apparaissent dans Teams. Les deux événements ci-dessus sont ce qui déclenche la copie.

### <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Utilisation de Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
