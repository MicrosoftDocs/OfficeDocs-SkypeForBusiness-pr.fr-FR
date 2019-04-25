---
title: Les équipes Microsoft | Mise à niveau, Mode (îles), stratégie d’interopérabilité de base, uniquement
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Détails de Skype pour les professionnels et Microsoft Teams coexistence et l’interopérabilité entre les équipes et Skype pour les entreprises.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63ddff805d0898b40cddae8a0fb9072359507da8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227118"
---
![Étapes du voyage mise à niveau, en insistant sur la phase de définition de projet] (media/upgrade-banner-project-definition.png "Étapes du voyage mise à niveau, en insistant sur la phase de définition de projet")

Cet article fait partie de la phase de définition de projet de votre parcours de mise à niveau, une activité effectuer après avoir créé une équipe de projet et coalition soutien et que vous définissez l’étendue, les objectifs et mission pour votre projet. Avant de continuer, vérifiez que vous avez effectué les activités suivantes :

- [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprendre Microsoft Teams et Skype pour l’interopérabilité et coexistence d’entreprise

Si votre organisation utilise Skype pour les entreprises aujourd'hui et que vous souhaitez commencer à utiliser les équipes à côté de Skype pour les entreprises, ou vous envisagez de démarrer la mise à niveau vers les équipes, il est important de comprendre comment les deux applications coexistent, quand et comment ils interagissent et comment à gérer migration des utilisateurs vers leur éventuelle mise à niveau à partir de Skype pour les entreprises aux équipes.

> [!Tip]
> Regarder la session suivante pour en savoir plus sur [l’interopérabilité et Coexistence](https://aka.ms/teams-upgrade-coexistence-interop)

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistence entre équipes et Skype pour les entreprises

Outre les fonctionnalités de collaboration, les équipes offre conversation, appel et des fonctionnalités de réunion. Selon la façon dont vous choisissez de déployer des équipes, ces fonctionnalités va se superposer avec les fonctionnalités fournies par Skype pour les entreprises pour un utilisateur donné. Le mode par défaut doit s’exécuter équipes avec Skype pour les entreprises ; Toutefois, un utilisateur peut disposer de plusieurs modes de coexistence qui ont été conçus pour vous assurer que ces fonctionnalités ne se chevauchent pas pour cet utilisateur.

Nous vous recommandons de consulter les modes de coexistence décrits ci-dessous pour vous aider à déterminer le chemin d’accès est adapté à votre organisation.

> [!Important]
> Présentation de la nouvelle technologie ou apporter des modifications à votre Skype existant et familier pour un environnement d’entreprise, tout en fournissant une nouvelle avantages, peut être sans interruption de service pour les utilisateurs. Prendre le temps d’évaluer la préparation de l’utilisateur et implémenter un plan de formation et de communication avant d’implémenter les modifications décrites dans cet article. En outre, nous vous invitons à piloter votre plan avec un groupe d’utilisateurs avant l’implémentation de votre organisation.

### <a name="islands-mode"></a>Mode (îles)

Par défaut, les utilisateurs peuvent exécuter des équipes à côté de Skype pour les entreprises en tant que deux solutions distinctes qui offrent des fonctionnalités similaires et qui se chevauchent telles que la conversation, appel et des réunions. Les équipes utilisateurs également peuvent tirer parti des fonctionnalités de collaboration tels que des équipes et canaux, accès aux fichiers dans Office 365 et des applications.

Dans ce mode de coexistence, appelé **(îles)**, chacune des applications clientes fonctionne comme un îlot séparé. Skype pour parle d’entreprise à Skype pour professionnels et les équipes communique avec les équipes. Les utilisateurs exécutent les deux clients et peuvent communiquer en mode natif dans le client à partir de laquelle la communication a été lancée. Par conséquent, il n’est pas nécessaire pour l’interopérabilité en mode **(îles)** .

> [!Tip]
> Skype pour Business Online clients recommandée consiste à démarrer avec le mode par défaut **(îles)** , dans l’organisation du lecteur saturation d’adoption et déplacez **Équipes uniquement** en mode rapide. Sur site et hybride clients peuvent bénéficier de déployer le mode **Skype pour les entreprises avec la collaboration des équipes** à venir en tant que point de départ plutôt que (îles) et la progression à partir de là, **Équipes uniquement** en mode lors de l’organisation est prête à adopter Équipes.

### <a name="skype-for-business-only"></a>Skype pour les entreprises uniquement

Dans ce mode de coexistence, les utilisateurs restent dans Skype pour les entreprises — pas les équipes — pour la conversation, réunion et appel des fonctions et qu’ils n’utilisent pas les équipes pour les équipes et les canaux. Ce mode est disponible. Toutefois, dans l’implémentation actuelle modalités d’équipes ne sont pas désactivées pour l’utilisateur automatiquement. Cette fonctionnalité est à venir. En attendant, administrateurs peuvent supprimer la licence équipes pour tous les utilisateurs qui ont besoin de rester dans Skype pour les entreprises en tant que leur application communications uniquement.

### <a name="teams-only"></a>Équipes uniquement

Un utilisateur **uniquement les équipes** peut uniquement utiliser le Skype pour client d’entreprise pour joindre Skype existant pour les réunions professionnelles ou des réunions sur Skype pour les entreprises qui ont été organisées par non mis à niveau des utilisateurs ou des parties externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs dans l’organisation qui sont toujours à l’aide de Skype pour les entreprises en utilisant les fonctionnalités d’interopérabilité entre les équipes et Skype pour les entreprises ; Toutefois, un utilisateur mis à niveau ne peut pas démarrer un Skype pour conversation Business, appel ou une réunion.

Dès que votre organisation est prête pour certains ou tous les utilisateurs d’utiliser les équipes leur seul outil de communication et de collaboration, vous pouvez mettre à niveau ces utilisateurs **Équipes uniquement** en mode.

Pour des considérations supplémentaires sur le déplacement des équipes uniquement en mode, voir [Considérations relatives au mode équipes uniquement](teams-only-mode-considerations.md).

![Skype pour client d’entreprise en cours d’exécution en mode spécial une fois que l’utilisateur est mis à niveau en tant qu’un utilisateur équipes uniquement] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype pour client d’entreprise en cours d’exécution en mode spécial une fois que l’utilisateur est mis à niveau en tant qu’un utilisateur équipes uniquement")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype pour les entreprises avec la Collaboration des équipes (ce mode est à venir)

Utilisez ce mode pour présenter des équipes de votre environnement tout en continuant à tirer parti de vos investissements existants dans Skype pour les entreprises. Dans ce mode, vous laissez Skype pour les entreprises inchangée avec la conversation, appel et des fonctionnalités de réunion et ajouter des fonctionnalités de collaboration des équipes, les équipes et les canaux, l’accès aux fichiers dans Office 365 et d’applications. Organisations de démarrage de point de Skype pour Business server sur site ou hybride doivent utiliser ce mode au lieu de mode (îles).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype pour les entreprises avec la Collaboration des équipes et des réunions (ce mode est à venir)

Utilisez ce mode de coexistence pour accélérer la disponibilité des fonctionnalités dans votre organisation, en plus de ses fonctionnalités de collaboration de la réunion, permettant à vos utilisateurs les équipes pour tirer parti de la grande qualité, nouvelles fonctions, telles que de transcription et prise en charge pour les réunions dans les navigateurs et traduction.

Ainsi qu’à l’aide des équipes pour les équipes et basée sur les canaux de conversations dans ce mode, les utilisateurs démarrent à l’aide des équipes de planifier et organiser des réunions. Salles de conversation privées et voix et appel vidéo, restent sur Skype pour les entreprises. Ce mode de coexistence est particulièrement utile pour les utilisateurs dans Skype pour les déploiements sur site Business voix entreprise, qui sont susceptibles de prendre un certain temps à mettre à niveau pour les équipes, mais souhaitent bénéficier des réunions équipes supérieures.

> [!Note]
> Lors du déploiement dans les modes de coexistence spécifique, équipes et Skype pour les entreprises peuvent [interagir](#interoperability-of-teams-and-skype-for-business), permettant aux utilisateurs de converser avec et l’autre des appels et en vous assurant que communications figées dans votre organisation au cours de votre voyage aux équipes de mise à niveau. Modes de coexistence régissent l’interopérabilité. Le mode de la coexistence du destinataire détermine si l’interopérabilité sera disponible. Par exemple, si le destinataire est dans un mode dans lequel conversation n’est plus disponible dans un client (par exemple, équipes), l’interopérabilité conversation généralement sera disponible au cas où l’initiateur utilise l’autre client (dans ce cas, Skype pour les entreprises) pour démarrer la conversation. En revanche, si le destinataire est dans un mode dans lequel la conversation est disponible dans les deux clients, l’interopérabilité n’est pas disponible pour la salle de conversation, et le message est reçu par le destinataire dans le même client dans lequel l’initiateur démarré la conversation.

Pour plus d’informations sur la gestion, les conditions préalables et les modes de coexistence, consultez [Migration et conseils d’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://aka.ms/SkypeToTeams-Interop) et [définir votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" />|Point de décision|<ul><li>Les meilleures coexistence mode (s) adaptées aux besoins de votre organisation et des utilisateurs ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étape suivante|<ul><li>Choisir la meilleure approche pour votre parcours de mise à niveau.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interopérabilité des équipes et Skype pour les entreprises

L’interopérabilité est la capacité pour les équipes et Skype pour les utilisateurs professionnels dans la même organisation de communiquer entre équipes et Skype pour les entreprises.

### <a name="native-interop-and-interop-escalation"></a>Escalade interopérabilité et interopérabilité native

Il existe deux types d’interopérabilité de base expériences : escalade natif et d’interopérabilité de base.

- Une expérience _d’interopérabilité native_ se produit dans le client qui est utilisé par l’utilisateur. Un utilisateur sera dans le Skype pour client d’entreprise, l’autre dans les équipes. Une expérience d’interopérabilité native ne prendre les vers un autre client pour communiquer, les utilisateurs seront en mesure de gérer leur conversation dans le client qu’ils utilisent actuellement. Les expériences interopérabilités natives sont une conversation et l’appel.
- Une expérience _d’escalade interopérabilité_ signifie que dans le cadre d’aider les utilisateurs à effectuer une action avancée (telles que le partage de leur bureau), le service peut faciliter la création d’une réunion et continuer l’expérience de cette réunion. La conférence est créée sur la plateforme de l’initiateur de l’action. Les utilisateurs qui ne sont pas sur cette plateforme reçoivent la réunion joindre les coordonnées et participer à la réunion (après le passage de clients).

### <a name="native-interop-experiences"></a>Interopérabilité native expérience améliorée

Selon les modes de coexistence attribués à des utilisateurs (comme décrit ci-dessus), les expériences interopérabilité native suivantes sont disponibles :

- Skype pour les utilisateurs professionnels peut converser en tête-à-tête avec les utilisateurs des équipes et vice versa. Une conversation interopérabilitée doit passer par une passerelle d’interopérabilité de base qui fait partie des équipes cloud services (et par conséquent existe uniquement en ligne). Interopérabilité conversations sont en texte brut : texte enrichi et des émoticônes ne sont pas pris en charge. Les utilisateurs dans les équipes sont avertis que la conversation est une conversation d’interopérabilité de base ; une notification similaire pour Skype pour les utilisateurs professionnels est fournie rapidement.

![Interopérabilité conversation expérience des équipes] (media/Interop_chat_experience_from_Teams.png "Interopérabilité conversation expérience des équipes")

- Skype pour les utilisateurs professionnels peut-il en tête-à-tête appels vocaux et vidéo pour les utilisateurs d’équipes et vice versa.

![Interopérabilité appelant expérience des équipes] (media/Interop_calling_experience_from_Teams.png "Interopérabilité appelant expérience des équipes")

> [!Important]
> Expériences interopérabilités avec un déploiement local de Skype pour les entreprises exigent que l’environnement sur site est en mode hybride avec Office 365 Skype pour les entreprises. Pour plus d’informations, voir [conseils d’interopérabilité et de Migration](https://aka.ms/SkypeToTeams-Interop).

Les fonctionnalités d’interopérabilité de base sont disponibles pour et entre les utilisateurs qui ont l’un des modes de coexistence suivants affecté : **Skype pour les entreprises avec la Collaboration des équipes**, **Skype pour l’entreprise grâce à des réunions et la Collaboration des équipes**, **Skype pour Business uniquement**, ou les **équipes uniquement**. Il n’existe aucune interopérabilité pour les utilisateurs en mode (îles).

### <a name="native-interop-experience-limitations"></a>Limitations de l’expérience interopérabilité native

Certaines fonctionnalités ne sont pas disponibles pour la conversation interopérabilitée et expérience appelant interopérabilité entre les équipes et Skype pour les entreprises :

- Le jeu d’émoticônes complète, texte enrichi et promotions ne sont pas pris en charge à partir des équipes ou Skype pour les entreprises. Autres fonctionnalités natives de la boîte de message à des conversations équipes ne sont pas pris en charge.
- Écran de partage entre équipes et Skype pour les entreprises (bureau ou partage d’application) n’est pas pris en charge.
- Conversations de groupe (tiers plusieurs conversations) dans les équipes ne peuvent inclure que les participants qui utilisent des équipes.
- Conversations de messagerie instantanée plusieurs tiers (salles de conversation de groupe) dans Skype pour les entreprises ne peuvent inclure que les participants qui utilisent Skype pour les entreprises.
- Passage d’un appel vidéo à un appel plusieurs tiers impliquant des équipes et Skype pour les utilisateurs professionnels ou vocales d’égal à égal en cours n’est pas pris en charge.
- Transfert de deux conversations de fichier ou de pièce jointe à des conversations de groupe, des équipes à Skype pour les entreprises et inversement, ne sont pas pris en charge.
- Il n’existe aucune interopérabilité avec Skype pour la conversation permanente Business.

Pour toutes ces limites (à l’exception de conversation permanente), une solution de contournement possible est pour un utilisateur démarrer une réunion et inviter à rejoindre l’autre utilisateur. Cette solution de contournement est la base d’escalade d’interopérabilité de base.

> [!Important]
> Ce qui démarre une conversation simple (IM) peut-être rapidement transformer un appel ou une réunion ad hoc. Bien que ces scénarios sont essentielles pour la facilité d’utilisation et l’expérience utilisateur, et nous sommes en constante évolution des expériences interopérabilités entre Skype pour les utilisateurs professionnels et les équipes. Rechercher dans les informations les plus récentes.

Après avoir lu cet article, voir [Choisir votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Migration et des conseils d’interopérabilité](https://aka.ms/SkypeToTeams-Interop), [la Coexistence avec Skype pour les entreprises](coexistence-chat-calls-presence.md)et [définir votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) d’implémentation plus d’informations.

## <a name="related-links"></a>Liens connexes

[Vidéo : Gérer la Coexistence et l’interopérabilité entre les équipes et SfB](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)