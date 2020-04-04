---
title: Interopérabilité entre Skype entreprise et Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Détails des options de coexistence de Skype entreprise et Microsoft Teams, ainsi que de l’interopérabilité entre Skype entreprise et Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc2a4495d95d0c6458fef16ea2f3f336dd337db4
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140675"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft teams et la coexistence et l’interopérabilité de Skype entreprise

![Diagramme de parcours de mise à niveau, mettant l’accent sur l’étape de définition du projet](media/upgrade-banner-project-definition.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de définition du projet")

Cet article fait partie de la phase de définition du projet de votre parcours de mise à niveau, d’une activité complète après la création d’une coalition de parrainage et de l’objectif de votre projet. Avant de continuer, confirmez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)

Si votre organisation utilise Skype entreprise dès aujourd’hui et que vous commencez à utiliser teams avec Skype entreprise, ou que vous commencez à effectuer la mise à niveau vers Teams, il est important de comprendre la manière dont les deux applications coexistent, quand et comment elles interagissent, et comment gérer la migration des utilisateurs dans le cadre de la mise à niveau de Skype entreprise vers Teams.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur la [coexistence et l’interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop).
>
> De plus, vous pouvez participer à des ateliers en direct et interactifs pour partager des conseils, des meilleures pratiques et des ressources conçues pour démarrer la mise à niveau de la planification et l’implémentation.
>
> Participez d’abord à la planification de votre session de [mise à niveau](https://aka.ms/SkypeToTeamsPlanning) pour commencer.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistence des équipes et de Skype entreprise

Outre les fonctionnalités de collaboration, teams fournit les fonctionnalités de conversation, d’appel et de réunion. En fonction de la façon dont vous choisissez de déployer Teams, ces fonctionnalités risquent de se superposer aux fonctions fournies par Skype entreprise pour un utilisateur donné. Le mode par défaut consiste à exécuter teams en même temps que Skype entreprise grâce aux fonctionnalités qui se chevauchent. Toutefois, l’un des modes de coexistence (également appelé mode de mise à niveau) peut être attribué à un utilisateur pour garantir que ces fonctionnalités ne se chevauchent pas pour cet utilisateur (auquel cas l’interopérabilité entre les équipes et Skype entreprise est disponible). Par exemple, si vous avez des ressources locales de Skype entreprise Server avec un déploiement vocal d’entreprise et que vous voulez que vos utilisateurs puissent profiter des réunions modernes le plus rapidement possible, il est possible que vous souhaitiez évaluer les [réunions](meetings-first.md) en guise d’alternative.

Nous vous recommandons de passer en revue les modes de coexistence suivants pour déterminer le chemin approprié pour votre organisation.

> [!Important]
> L’introduction de nouvelles technologies ou la modification de votre environnement Skype entreprise actuel et familier, tout en offrant de nouveaux avantages économiques, peuvent être perturbés pour les utilisateurs. Prenez le temps d’évaluer la compatibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter les modifications décrites dans cet article. Par ailleurs, nous vous encourageons vivement à piloter votre plan avec un groupe d’utilisateurs sélectionné avant de l’implémenter au sein de votre organisation.

### <a name="islands-mode"></a>Mode insulaire

Par défaut, les utilisateurs peuvent exécuter des équipes en même temps que Skype entreprise, sous la forme de deux solutions distinctes qui offrent des fonctionnalités similaires et chevauchantes, telles que la présence, les discussions, les appels et les réunions. Les utilisateurs teams peuvent également tirer parti des nouvelles fonctionnalités de collaboration telles que les équipes et les canaux, l’accès aux fichiers dans Office 365 et les applications.

Dans ce mode de coexistence, appelé **îlot**, chacune des applications clientes fonctionne comme une île séparée. Skype entreprise parle de Skype entreprise et teams parle d’équipes. Les utilisateurs doivent exécuter les deux clients à tout moment et pouvoir communiquer en mode natif dans le client à partir duquel la communication a été lancée. Par exemple, il n’est pas nécessaire d’interopérabilité en mode **îlot** .

Pour éviter d’avoir une connaissance confuse ou régressé, les communications externes, les services vocaux RTC et les applications vocales, l’intégration d’Office, les contrôles HID pour les périphériques USB et plusieurs autres intégrations continuent d’être gérées par Skype entreprise et ne sont pas disponibles dans teams en mode **îlot** . Le système téléphonique n’est pas pris en charge dans teams en mode **îlot** ; dans ce mode, le seul client voix entreprise est Skype entreprise.

> [!Important]
> Dans le mode **îlot** , tous les messages et les appels des utilisateurs fédérés (personnes externes à votre organisation) sont remis à Skype entreprise. Après avoir effectué la mise à niveau vers le mode **équipes uniquement** , tous les messages et les appels en dehors de votre organisation sont remis à Teams.

> [!Tip]
> Le chemin d’accès recommandé pour les utilisateurs de Skype entreprise Online consiste à démarrer avec le mode par défaut des **îles** , de mettre la saturation des équipes au sein de l’organisation et de basculer rapidement vers le mode **équipes uniquement** . Les clients locaux et hybrides, particulièrement complexes, peuvent bénéficier du déploiement du mode de **collaboration Skype entreprise avec teams** comme point de départ plutôt que du mode d' **îlot** et de la progression de la réunion avec le mode de collaboration et des réunions dans **Skype entreprise avec teams** (c’est-à-dire, réunions d’abord), le cas échéant, et en mode **équipes uniquement** lorsque l’organisation est prête à adopter teams

### <a name="skype-for-business-only"></a>Skype Entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype entreprise (et non dans Teams) pour les fonctionnalités de conversation, de réunion et d’appel, et ils n’utilisent pas teams pour les équipes et les canaux. Ce mode est disponible aujourd’hui ; Toutefois, dans l’implémentation actuelle, les équipes et les canaux ne sont pas automatiquement désactivés pour l’utilisateur. Pour cela, vous pouvez utiliser la stratégie d’autorisations d’application pour masquer les équipes et les canaux.

Ce mode peut être utilisé avant le démarrage d’un déploiement géré d’équipes afin d’empêcher les utilisateurs de commencer à utiliser teams en avance ou à activer la participation authentifiée dans les réunions d’équipes pour les utilisateurs de Skype entreprise, à condition que les utilisateurs soient sous licence d’équipes.

### <a name="teams-only"></a>Équipes uniquement


> [!IMPORTANT]
> Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution de contournement :pour afficher la présence dans Outlook (et d'autres applications Office), Skype Entreprise doit être installé, même si vous exécutez Teams en mode **Teams uniquement**. Microsoft est sensibilisé à ce problème et travaille activement au développement d’un correctif.


Un utilisateur de **teams** (également appelé utilisateur *mis à niveau* ) a accès à toutes les fonctionnalités dans Teams. Ils peuvent conserver le client Skype entreprise pour pouvoir participer à des réunions dans Skype entreprise qui ont été organisées par des utilisateurs qui ne sont pas mis à niveau ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui utilisent encore Skype entreprise à l’aide des fonctionnalités d’interopérabilité entre teams et Skype entreprise (à condition que les utilisateurs de Skype entreprise ne sont pas en mode d' **îlot** ). Toutefois, un utilisateur mis à niveau ne peut pas lancer une conversation, un appel ou une réunion Skype entreprise.

Dès que votre organisation est prête à être utilisée par tout ou partie des équipes comme outil de communication et de collaboration uniquement, vous pouvez mettre à niveau ces utilisateurs vers le mode **équipes uniquement** . Si vous effectuez une mise à niveau à partir du mode **îlot** , nous vous conseillons de saturer d’abord les équipes au sein de votre organisation avant de commencer le processus de mise à niveau. Cela évite de violer les scénarios de communication en raison du fait que le mode **îlot** ne procure pas d’interopérabilité.

Pour plus d’informations sur le passage en mode **équipes uniquement** , voir [considérations relatives au mode équipes uniquement](teams-only-mode-considerations.md).

![Capture d’écran du message de confirmation teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Client Skype entreprise s’exécutant en mode spécial une fois que l’utilisateur a été mis à niveau en tant qu’utilisateur d’équipe uniquement")

### <a name="skype-for-business-with-teams-collaboration"></a>Collaboration avec teams dans Skype entreprise

Ce mode permet aux équipes dans votre environnement de profiter de votre investissement actuel dans Skype entreprise. Dans ce mode, vous laissez Skype entreprise inchangé pour les fonctionnalités de conversation, d’appel et de réunion, et vous ajoutez des fonctionnalités de collaboration aux équipes (équipes et canaux, accès à des fichiers dans Office 365 et applications). Les fonctionnalités de communication de Teams (discussions privées, appels et planification) sont désdésactivées dans ce mode par défaut.

Les organisations dont le point de départ est Skype entreprise Server sur site ou hybride doivent envisager ce mode en guise d’alternative au mode **insulaire** s’ils souhaitent offrir à leurs utilisateurs l’interopérabilité et la prédiction de leurs communications, ainsi qu’une chronologie prévisible pour leur mise à niveau vers Teams (plutôt que d’adopter la saturation du mode **insulaire** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype entreprise avec la collaboration et les réunions d’équipes, également appelées réunions en premier

Utilisez ce mode de coexistence pour accélérer la disponibilité des fonctionnalités de réunion teams au sein de votre organisation, en plus de ses fonctionnalités de collaboration, permettant à vos utilisateurs de profiter de l’utilisation de la fonction de réunion de qualité d’équipe supérieure (qualité de la transcription et de la traduction ou de l’arrière-plan) et d’une meilleure utilisation de toutes les plates-formes, y compris

Outre l’utilisation d’équipes pour les équipes et les canaux, les utilisateurs utilisent teams pour planifier et diriger leurs réunions. Les appels et les discussions privés restent sur Skype entreprise. Avantages de teams et de Skype entreprise d’une gamme de fonctions « combinées », telles que le rapprochement de présence, la conservation automatique de la conservation et l’affichage de périphériques HID sur les deux applications. Notez qu’il est possible de masquer les équipes et les canaux, si vous le souhaitez, à l’aide de la stratégie d’autorisations des applications.

Ce mode de coexistence est particulièrement utile pour les organisations qui utilisent des déploiements sur site de Skype entreprise et qui sont susceptibles de prendre le temps de mettre à jour les équipes et de profiter des réunions de plus en plus performantes dès que possible.

> [!Note]
> Lorsqu’il est déployé dans n’importe quel mode de coexistence, à l’exception des **îles**, teams et Skype entreprise [, permet aux](#interoperability-of-teams-and-skype-for-business)utilisateurs de communiquer avec eux et de s’appeler entre eux et de veiller à ce que les communications restent fluides au sein de votre organisation pendant la mise à niveau vers Teams. Modes de coexistence régissant l’interopérabilité. Le mode de coexistence du destinataire détermine si l’interopérabilité sera disponible. Par exemple, si le destinataire est dans un mode qui n’est disponible que dans un seul client (par exemple, Teams), l’interopérabilité des discussions sera généralement disponible en cas d’utilisation d’un autre client (dans ce cas, Skype entreprise) pour lancer la discussion. D’un autre côté, si le destinataire est en mode d’accès à la discussion dans les deux clients (mode de l’îlot), l’interopérabilité ne sera pas disponible pour la discussion. Le message est reçu par le destinataire dans le client dans lequel l’initiateur a lancé la discussion. Par conséquent, une bonne communication en mode **îlot** nécessite la saturation de teams ; ainsi, tous les utilisateurs utilisent activement et surveillant les deux clients.

> [!TIP]
> Pour vous aider à identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous voulez activer dans teams alors que Skype entreprise est toujours en cours d’utilisation, tirez parti de l' [Assistant Mise à niveau de Skype to teams](https://aka.ms/SkypeToTeamsWizard).

Pour plus d’informations sur les modes de coexistence, les conditions préalables et la gestion, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes avec Skype entreprise](https://aka.ms/SkypeToTeams-Interop) et [définissant vos paramètres de coexistence et de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quels sont les modes de coexistence qui conviennent le mieux aux besoins de votre organisation et de vos utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour le voyage de votre mise à niveau.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité entre teams et Skype entreprise

L’interopérabilité est une fonctionnalité qui permet aux équipes et aux utilisateurs Skype entreprise de la même organisation de communiquer entre eux et Skype entreprise.

L’interopérabilité est régie par le mode de coexistence (également appelé mode de mise à niveau) du destinataire. Il n’existe aucune interopérabilité lorsque le destinataire est en mode **îlot** .

### <a name="native-interop-and-interop-escalation"></a>Escalade d’interopérabilité native et d’interopérabilité

Il existe deux types d’expériences d’interopérabilité : la réaffectation native et interopérabilité.

- Une interface d' _interopérabilité native_ intervient dans le client que l’utilisateur utilise actuellement. Un utilisateur sera dans le client Skype entreprise, l’autre dans Teams. Dans le cadre d’une utilisation native de l’interopérabilité, les utilisateurs ne pourront pas communiquer eux-mêmes à un autre client. Les expériences d’interopérabilité natives sont des conversations et des appels à deux.
- Une expérience d' _escalade d’interopérabilité_ implique que dans le cadre de l’assistance des utilisateurs pour effectuer une action avancée (par exemple, le partage de leur bureau), le client facilite la création d’une réunion à laquelle les utilisateurs peuvent se joindre pour continuer l’expérience de cette réunion. La réunion est créée sur la plateforme de l’initiateur de l’action. Les utilisateurs qui ne se trouvent pas sur cette plateforme reçoivent un lien de participation à une réunion. Étant donné qu’ils cliquent sur ce lien, ils sont joints à la réunion dans un client compatible (navigateur, application Web ou client complet, en fonction de la configuration). La progression de l’interopérabilité de Skype entreprise nécessite un client récent. La réaffectation d’interopérabilité des équipes est désormais disponible. Les deux sont pris en charge dans les expériences d’interopérabilité dans le client et pour les clients de communications fédérées.

### <a name="native-interop-experiences"></a>Expériences d’interopérabilité native

En fonction des modes de coexistence attribués aux utilisateurs (comme décrit plus haut), les expériences d’interopérabilité natives suivantes sont disponibles :

Les utilisateurs de Skype entreprise peuvent discuter avec les utilisateurs Teams, et inversement. Une discussion d’interopérabilité doit traverser une passerelle d’interopérabilité incluse dans teams services Cloud (et donc uniquement en ligne). Les discussions d’interopérabilité sont en texte brut : le texte enrichi et les émoticônes ne sont pas pris en charge. Dans teams et dans Skype entreprise, les utilisateurs sont avertis du fait qu’il s’agit d’une conversation d’interopérabilité.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Les utilisateurs de Skype entreprise peuvent passer des appels vocaux et vidéo en tête à tête aux utilisateurs de teams, et inversement.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Les expériences d’interopérabilité d’un déploiement local de Skype entreprise requièrent que l’environnement local soit en mode hybride avec Office 365 Skype entreprise. Pour plus d’informations, consultez les [conseils de migration et d’interopérabilité](https://aka.ms/SkypeToTeams-Interop).

Ces expériences d’interopérabilité sont accessibles aux utilisateurs et aux utilisateurs qui disposent de l’un des modes de coexistence suivants attribués : **Skype entreprise avec collaboration en équipe**, **Skype entreprise avec collaboration et réunions en équipe**, **Skype entreprise uniquement**ou **équipes uniquement**. Il n’existe aucune interopérabilité entre les utilisateurs en mode **îlot** .

### <a name="native-interop-experience-limitations"></a>Limitations de l’interface d’interopérabilité native

En raison de la différence de protocoles et de technologie, il n’est pas possible de prendre en charge toutes les fonctionnalités en mode natif. Plus précisément, les fonctionnalités suivantes ne sont pas disponibles :

- La démarque, le texte enrichi et l’ensemble d’émoticônes complet ne sont pas pris en charge par teams ou Skype entreprise. D’autres fonctionnalités natives de la zone de rédaction des discussions en équipes ne sont pas prises en charge.
- Le partage d’écran (le partage de bureau ou d’application) entre les équipes et Skype entreprise n’est pas pris en charge en mode natif. Toutefois, elle est prise en charge par le biais de la réaffectation d’interopérabilité.
- Les discussions de groupe (conversations à plusieurs parties) dans teams peuvent inclure uniquement les participants qui utilisent Teams.
- Les conversations de messagerie instantanée à plusieurs (discussions de groupe) dans Skype entreprise ne peuvent inclure que les personnes qui utilisent Skype entreprise. En revanche, la réorganisation de l’interopérabilité entre les différentes parties est disponible dans Skype entreprise.
- Le fait de répartir un appel audio ou vidéo pair à pair vers un appel à plusieurs participants implique des équipes et des utilisateurs Skype entreprise n’est pas pris en charge.
- Le transfert de fichiers pour les conversations à deux ou les pièces jointes dans des discussions de groupe, de teams à Skype entreprise, et inversement, n’est pas pris en charge.
- Il n’y a pas d’interopérabilité avec les discussions permanentes Skype entreprise.

Pour toutes ces limitations (sauf dans le cas d’une conversation permanente), il existe une solution de contournement possible pour permettre à un utilisateur de démarrer une réunion et d’inviter l’utilisateur à rejoindre la réunion.

Il s’agit de la solution de contournement pour la réaffectation d’interopérabilité. En particulier, le partage d’écran et la réaffectation à plusieurs parties ne sont pas réalisables en natif, mais ils sont pris en charge par le biais de la réaffectation d’interopérabilité.

### <a name="interop-escalation-experiences"></a>Expériences de réaffectation d’interopérabilité

La réorganisation de l’interopérabilité se compose en complétant les fonctionnalités d’interopérabilité natives par une remontée gérée des réunions. Les réunions offrent des expériences riches accessibles à tout le monde, quel que soit le client qu’ils possèdent.

Lorsque la réaffectation d’interopérabilité est déclenchée par l’utilisateur Teams, une réunion teams est créée. Lorsque l’utilisateur Skype entreprise le déclenche, une réunion Skype entreprise est créée. Dans les deux cas, la réunion créée est une réunion **Conférence maintenant** qui n’apparaît pas dans le calendrier de l’utilisateur.
 
L’autre personne reçoit le lien de participation à la réunion par le biais de conversations et de jointures Interop en cliquant sur ce lien. Si l’utilisateur de Skype entreprise dispose d’un compte d’équipe et est invité par l’utilisateur de teams, il rejoint la réunion qui est authentifiée. Dans le cas contraire, il sera joint en tant que participant anonyme. À l’inverse, les utilisateurs de teams disposent presque toujours d’un compte Skype entreprise et d’un client Skype entreprise qu’ils peuvent utiliser pour participer à une réunion Skype entreprise en tant que participant authentifié, mais ils peuvent également se joindre en tant que participant anonyme, par exemple l’application réunion Skype.

Une fois que les parties ont rejoint la réunion, elles peuvent diriger toutes les activités prises en charge dans les réunions, telles que le partage de bureau ou de contenu, le partage de fichiers ou le transfert, l’ajout d’autres participants, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalade d’interopérabilité depuis Skype entreprise

La réaffectation de l’interopérabilité et de l’interopérabilité de Skype entreprise a été mise à jour dans la build 2019 de juillet C2R. Auparavant, Skype entreprise ne proposait pas à l’avance que la partie distante utilisait Teams. Seule surmised à partir du signal reçu après l’établissement d’une session.

Lorsque les signaux indiquent que la réponse provient de la passerelle d’interopérabilité (ou par le biais de celle-ci), elle affichait la barre d’affaires jaune (bannière) indiquant que l’autre personne n’utilise pas Skype entreprise. En raison de l’évolution de notre service, il s’est produit des faux positifs lorsque les utilisateurs de Skype entreprise pouvaient voir la barre d’entreprise lorsqu’ils étaient connectés au service de messagerie vocale Cloud ou à d’autres services vocaux Cloud, plutôt qu’à un utilisateur d' **équipe uniquement** .
 
Pour éviter ces faux positifs, le service de présence est désormais en train d’informer le client Skype entreprise quand il s’agit d’une **équipe uniquement** en tant qu’utilisateur réel. Cela permet à Skype entreprise de savoir qu’il est nécessaire de créer une conversation d’interopérabilité au-delà de sa création et de la fenêtre de conversation pour être spécifique à l’interopérabilité.

![Capture d’écran du message d’équipe permettant de créer une conversation d’interopérabilité avec un utilisateur Skype entreprise](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si l’utilisateur Skype entreprise veut partager son bureau, par exemple, il est informé que nous allons lancer une réunion et suivre les étapes décrites dans cette procédure.

![Capture d’écran du message d’équipe permettant de démarrer une réunion avec un utilisateur de teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Entre-temps, l’utilisateur de teams reçoit un message de discussion entrant contenant le lien vers la réunion et est guidé pour s’inscrire.

Ce renvoi à une réunion Skype entreprise est disponible pour l’interopérabilité dans le client et pour les appels et les discussions fédérées entre clients. Elle est activée par défaut et il n’y a aucun paramètre que l’administrateur doit mettre en service.

#### <a name="interop-escalation-from-teams"></a>Escalade d’interopérabilité à partir de teams

La réorganisation de l’interopérabilité entre teams et une réunion teams est désormais disponible lorsque l’utilisateur de teams sélectionne le bouton de partage de bureau dans un thread d’interopérabilité in-client avec un utilisateur de Skype entreprise ou dans un thread de Fédération d’interclient. La réaffectation d’interopérabilité est prise en charge dans une conversation de messagerie 1:1 ou depuis un appel 1:1.

Cette fonctionnalité est prise en charge dans le client de bureau teams pour Windows, dans le client de bureau teams pour Mac et dans le client Web teams dans les navigateurs où le partage de contenu est pris en charge, tandis qu’il est pris en charge avec une version de client Skype entreprise.

Dans les threads d’interopérabilité et dans les threads d’interopérabilité de Fédération, l’utilisateur teams dispose désormais du bouton contrôles pour démarrer le partage de contenu. Lorsque l’utilisateur de teams sélectionne le bouton, un menu supplémentaire lui indique qu’il doit partager du contenu, il doit commencer une réunion Teams.

Si les utilisateurs ont participé à un appel, le menu les prévient pour leur permettre de mettre fin à l’appel en cours entre teams et Skype entreprise. Si tel est le cas, l’utilisateur peut m’avertir avant d’accepter.

![Capture d’écran du message d’équipe permettant de partager la réunion avec un utilisateur de Skype entreprise](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Lors de la validation, il est placé dans la réunion Teams. ils doivent commencer le partage à partir du bac de partage de la réunion.
 
Pendant ce temps, l’utilisateur Skype entreprise reçoit un message de discussion entrant contenant le lien vers la réunion et est guidé pour s’inscrire.

Ce remontée à une réunion teams est disponible pour les appels et les discussions et les appels fédérés entre clients. Elle est activée par défaut et il n’y a aucun paramètre que l’administrateur doit mettre en service. Toutefois, elle est désactivée pour l’utilisateur si celui- ``-AllowPrivateMeetNow`` ci ``CsTeamsMeetingPolicy`` est ``$false``défini comme.

Après avoir consulté cet article, vous pouvez consulter [la rubrique choix de votre guide de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), de la [migration et de l’interopérabilité](https://aka.ms/SkypeToTeams-Interop), de la [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md)et de [la configuration de votre coexistence et de vos paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) pour plus d’informations.

## <a name="related-links"></a>Liens connexes

[Vidéo : gérer la coexistence et l’interopérabilité entre marketing et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
