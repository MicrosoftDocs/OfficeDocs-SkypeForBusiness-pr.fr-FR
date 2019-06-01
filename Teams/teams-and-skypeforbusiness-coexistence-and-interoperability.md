---
title: Microsoft teams | Mise à niveau, mode insulaire, stratégie d’interopérabilité, uniquement
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Détails des options de coexistence de Skype entreprise et Microsoft Teams, ainsi que de l’interopérabilité entre Skype entreprise et Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f32fd9fbbf43d5390422f1f6e47e0714bb5ab578
ms.sourcegitcommit: ff777b61573b9d90e2d49c49b41fad654eeb3af7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652840"
---
![Diagramme de parcours de mise à niveau, mettant l’accent sur l’étape de définition du projet] (media/upgrade-banner-project-definition.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de définition du projet")

Cet article fait partie de la phase de définition du projet de votre parcours de mise à niveau, d’une activité complète après la création d’une coalition de parrainage et de l’objectif de votre projet. Avant de continuer, confirmez que vous avez terminé les activités suivantes:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft teams et la coexistence et l’interopérabilité de Skype entreprise

Si votre organisation utilise Skype entreprise dès aujourd’hui et que vous envisagez de commencer à utiliser teams en même temps que Skype entreprise, ou si vous envisagez de commencer la mise à niveau vers Teams, il est important de comprendre la manière dont les deux applications coexistent, quand et comment elles interagissent, et comment gestion de la migration des utilisateurs jusqu’à la mise à niveau éventuelle de Skype entreprise vers équipes.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur la [coexistence et l’interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop)

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistence des équipes et de Skype entreprise

Outre les fonctionnalités de collaboration, teams fournit les fonctionnalités de conversation, d’appel et de réunion. En fonction de la façon dont vous choisissez de déployer Teams, ces fonctionnalités seront communes aux fonctions fournies par Skype entreprise pour un utilisateur donné. Le mode par défaut consiste à exécuter teams en même temps que Skype entreprise. Toutefois, l’un des modes de coexistence suivants peut être attribué à un utilisateur pour garantir que ces fonctionnalités ne se chevauchent pas pour cet utilisateur.

Nous vous recommandons de passer en revue les modes de coexistence décrits ci-dessous pour vous aider à déterminer le chemin approprié pour votre organisation.

> [!Important]
> L’introduction de nouvelles technologies ou la modification de votre environnement Skype entreprise actuel et familier, tout en offrant de nouveaux avantages économiques, peuvent être perturbés pour les utilisateurs. Prenez le temps d’évaluer la compatibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter les modifications décrites dans cet article. Par ailleurs, nous vous encourageons vivement à piloter votre plan avec un groupe d’utilisateurs sélectionné avant de l’implémenter au sein de votre organisation.

### <a name="islands-mode"></a>Mode insulaire

Par défaut, les utilisateurs peuvent exécuter des équipes en même temps que Skype entreprise, sous la forme de deux solutions distinctes qui offrent des fonctionnalités similaires et communes, telles que les discussions, les appels et les réunions. Les utilisateurs teams peuvent également tirer parti de fonctionnalités de collaboration telles que les équipes et les canaux, l’accès aux fichiers dans Office 365 et les applications.

Dans ce mode de coexistence, appelé **îlot**, chacune des applications clientes fonctionne comme une île séparée. Skype entreprise parle de Skype entreprise et teams parle d’équipes. Les utilisateurs exécutent les deux clients et peuvent communiquer en mode natif dans le client à partir duquel la communication a été lancée. Par exemple, il n’est pas nécessaire d’interopérabilité en mode **îlot** .

> [!Tip]
> Le chemin d’accès recommandé pour les utilisateurs de Skype entreprise Online consiste à commencer avec le mode par défaut de l' **îlot** , à la saturation de la saturation du lecteur au sein de l’organisation, puis passer en mode d' **équipe uniquement** . Les clients locaux et hybrides peuvent bénéficier du déploiement du mode de **collaboration Skype entreprise avec teams** comme point de départ plutôt que des îlots et de la progression du mode **équipe uniquement** lorsque l’organisation est prête à être adoptée. Associations.

### <a name="skype-for-business-only"></a>Skype entreprise uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype entreprise (et non dans Teams) pour les fonctionnalités de conversation, de réunion et d’appel, et ils n’utilisent pas teams pour les équipes et les canaux. Ce mode est disponible aujourd’hui; Toutefois, dans les modalités de l’implémentation actuelle, l’utilisateur n’est pas désactivé automatiquement. Cette fonctionnalité est à venir. Dans le cadre de l’attente, les administrateurs peuvent supprimer la licence teams pour tous les utilisateurs qui ont besoin de rester dans Skype entreprise en tant qu’application de communications uniquement.

### <a name="teams-only"></a>Équipes uniquement

Un utilisateur de **teams uniquement** peut utiliser le client Skype entreprise pour participer à des réunions Skype entreprise existantes ou des réunions sur Skype entreprise qui ont été organisées par des utilisateurs non mis à niveau ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui utilisent encore Skype entreprise à l’aide des fonctionnalités d’interopérabilité entre teams et Skype entreprise. Toutefois, un utilisateur mis à niveau ne peut pas lancer une conversation, un appel ou une réunion Skype entreprise.

Dès que votre organisation est prête à être utilisée par tout ou partie des équipes comme outil de communication et de collaboration uniquement, vous pouvez mettre à niveau ces utilisateurs vers le mode **équipes uniquement** .

Pour plus d’informations sur le passage en mode équipes uniquement, voir [considérations relatives au mode équipes uniquement](teams-only-mode-considerations.md).

![Capture d’écran du message de confirmation teams] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Client Skype entreprise s’exécutant en mode spécial une fois que l’utilisateur a été mis à niveau en tant qu’utilisateur d’équipe uniquement")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype entreprise avec collaboration en équipes (ce mode est à venir)

Ce mode permet aux équipes dans votre environnement de profiter de votre investissement actuel dans Skype entreprise. Dans ce mode, vous ne modifiez pas Skype entreprise avec les fonctionnalités de conversation, d’appel et de réunion, et vous ajoutez des fonctionnalités de collaboration aux équipes (équipes et canaux, accès à des fichiers dans Office 365 et applications). Les organisations avec le point de départ de Skype entreprise Server en local ou en hybride doivent utiliser ce mode au lieu du mode îlot.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype entreprise avec collaboration et réunions en équipe (ce mode est à venir)

Utilisez ce mode de coexistence pour accélérer la disponibilité des fonctionnalités de réunion teams au sein de votre organisation, en plus de ses fonctionnalités de collaboration, qui permettent à vos utilisateurs de profiter de la qualité exceptionnelle de nouvelles fonctionnalités telles que la transcription et traduction et prise en charge des réunions dans les navigateurs.

Outre l’utilisation d’équipes pour les équipes et les canaux, les utilisateurs commencent à utiliser teams pour planifier et organiser leurs réunions. Les discussions privées et les appels audio et vidéo sont conservés sur Skype entreprise. Ce mode de coexistence est particulièrement utile pour les utilisateurs de déploiements sur site de Skype entreprise, qui sont susceptibles de prendre du temps pour être mis à niveau vers Teams, mais peuvent tirer parti des réunions d’équipes supérieures.

> [!Note]
> Lorsqu’elle est déployée dans des modes de coexistence spécifiques, les équipes et Skype entreprise peuvent [interagir](#interoperability-of-teams-and-skype-for-business), ce qui permet aux utilisateurs de discuter avec eux et de s’appeler l’un de l’autre et de veiller à ce que les communications restent fluides au sein de votre organisation pendant la mise à niveau vers Teams. Modes de coexistence régissant l’interopérabilité. Le mode de coexistence du destinataire détermine si l’interopérabilité sera disponible. Par exemple, si le destinataire est dans un mode qui n’est disponible que dans un seul client (par exemple, Teams), l’interopérabilité des discussions sera généralement disponible en cas d’utilisation d’un autre client (dans ce cas, Skype entreprise) pour lancer la discussion. D’un autre côté, si le destinataire est dans un mode dans lequel la conversation est disponible dans les deux clients, l’interopérabilité ne sera pas disponible pour la discussion, et le message sera reçu par le destinataire dans le client sur lequel l’initiateur a lancé la discussion.

Pour plus d’informations sur les modes de coexistence, les conditions préalables et la gestion, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes avec Skype entreprise](https://aka.ms/SkypeToTeams-Interop) et [définissant vos paramètres de coexistence et de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision|<ul><li>Quels sont les modes de coexistence qui conviennent le mieux aux besoins de votre organisation et de vos utilisateurs?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Étape suivante|<ul><li>Choisissez la meilleure approche pour le voyage de votre mise à niveau.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité entre teams et Skype entreprise

L’interopérabilité est une fonctionnalité qui permet aux équipes et aux utilisateurs Skype entreprise de la même organisation de communiquer entre eux et Skype entreprise.

### <a name="native-interop-and-interop-escalation"></a>Escalade d’interopérabilité native et d’interopérabilité

Il existe deux types d’expériences d’interopérabilité: la réaffectation native et interopérabilité.

- Une interface d' _interopérabilité native_ intervient dans le client que l’utilisateur utilise actuellement. Un utilisateur sera dans le client Skype entreprise, l’autre dans Teams. Dans le cadre d’une utilisation native de l’interopérabilité, les utilisateurs ne pourront pas communiquer eux-mêmes à un autre client. Les expériences d’interopérabilité natives sont des conversations et des appels à deux.
- Une expérience d' _escalade_ d’interopérabilité signifie que dans le cadre de l’assistance des utilisateurs pour effectuer une action avancée (comme le partage de leur bureau), le service peut faciliter la création d’une réunion et poursuivre l’expérience dans cette réunion. La réunion est créée sur la plateforme de l’initiateur de l’action. L’utilisateur ou les utilisateurs qui ne sont pas sur cette plateforme reçoivent des coordonnées de participation à la réunion et rejoignent la réunion (après le changement de clients).

### <a name="native-interop-experiences"></a>Expériences d’interopérabilité native

En fonction des modes de coexistence attribués aux utilisateurs (comme décrit ci-dessus), les expériences d’interopérabilité natives suivantes sont disponibles:

- Les utilisateurs de Skype entreprise peuvent discuter avec les utilisateurs Teams, et inversement. Une discussion d’interopérabilité doit traverser une passerelle d’interopérabilité incluse dans teams services Cloud (et donc uniquement en ligne). Les discussions d’interopérabilité sont en texte brut: le texte enrichi et les émoticônes ne sont pas pris en charge. Les utilisateurs dans teams sont avertis que la conversation est une conversation d’interopérabilité. une notification similaire pour les utilisateurs Skype entreprise sera bientôt fournie.

![Capture d’écran de l’interface de conversation d’interopérabilité de teams] (media/Interop_chat_experience_from_Teams.png "Découvrir l’interface utilisateur de teams")

- Les utilisateurs de Skype entreprise peuvent passer des appels vocaux et vidéo en tête à tête aux utilisateurs de teams, et inversement.

![Capture d’écran de l’interface d’appel d’interopérabilité de teams] (media/Interop_calling_experience_from_Teams.png "Découverte de l’appel d’interopérabilité d’équipes")

> [!Important]
> Les expériences d’interopérabilité d’un déploiement local de Skype entreprise requièrent que l’environnement local soit en mode hybride avec Office 365 Skype entreprise. Pour plus d’informations, consultez les [conseils de migration et](https://aka.ms/SkypeToTeams-Interop)d’interopérabilité.

Ces expériences d’interopérabilité sont accessibles aux utilisateurs et aux utilisateurs qui disposent de l’un des modes de coexistence suivants attribués: **Skype entreprise avec collaboration en équipe**, **Skype entreprise avec collaboration et réunions en équipe**, **Skype pour Professionnelle uniquement**ou **équipes uniquement**. Il n’existe aucune interopérabilité entre les utilisateurs en mode îlot.

### <a name="native-interop-experience-limitations"></a>Limitations de l’interface d’interopérabilité native

Certaines fonctionnalités ne sont pas disponibles pour les appels de chat et d’interopérabilité entre teams et Skype entreprise:

- La démarque, le texte enrichi et l’ensemble d’émoticônes complet ne sont pas pris en charge par teams ou Skype entreprise. D’autres fonctionnalités natives de la zone de rédaction des discussions en équipes ne sont pas prises en charge.
- Le partage d’écran (le partage de bureau ou d’application) entre les équipes et Skype entreprise n’est pas pris en charge.
- Les discussions de groupe (conversations à plusieurs parties) dans teams peuvent inclure uniquement les participants qui utilisent Teams.
- Les conversations de messagerie instantanée à plusieurs (discussions de groupe) dans Skype entreprise ne peuvent inclure que les personnes qui utilisent Skype entreprise.
- Le fait de répartir un appel audio ou vidéo pair à pair vers un appel à plusieurs participants implique des équipes et des utilisateurs Skype entreprise n’est pas pris en charge.
- Le transfert de fichiers pour les conversations à deux ou les pièces jointes dans des discussions de groupe, de teams à Skype entreprise, et inversement, n’est pas pris en charge.
- Il n’y a pas d’interopérabilité avec les discussions permanentes Skype entreprise.

Pour toutes ces limitations (sauf dans le cas d’une conversation permanente), il existe une solution de contournement possible pour permettre à un utilisateur de démarrer une réunion et d’inviter l’utilisateur à rejoindre la réunion. Il s’agit de la solution de contournement pour la réaffectation d’interopérabilité.

> [!Important]
> Ce qui se passe par une simple discussion (messagerie instantanée) peut rapidement être retardée pour un appel ou une réunion ad hoc. Nous sommes conscients du bon fonctionnement de ces scénarios et de l’expérience utilisateur, et l’évolution des expériences d’interopérabilité entre les utilisateurs de Skype entreprise et de teams. Consultez de nouveau les informations les plus récentes.

Après avoir consulté cet article, vous pouvez consulter [la rubrique choix de votre guide de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), de la [migration et](https://aka.ms/SkypeToTeams-Interop)de l’interopérabilité, de la [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md)et de [la configuration de votre coexistence et de vos paramètres de mise à niveau pour l'](https://aka.ms/SkypeToTeams-SetCoexistence) implémentation taille.

## <a name="related-links"></a>Liens connexes

[Vidéo: gérer la coexistence et l’interopérabilité entre marketing et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
