---
title: Guide d’accessibilité pour les administrateurs Microsoft Teams
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Améliorez l’accessibilité dans Microsoft Teams en activant les légendes et la transcription, en donnant accès aux interpréteurs de langue des signes et aux sous-titreurs CART, en réduisant les distractions, en améliorant la participation et en partageant des ressources.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614708"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Guide d’accessibilité pour les administrateurs Microsoft Teams

En tant qu’administrateur Microsoft Teams pour votre organisation, vous pouvez contribuer à rendre votre environnement Teams aussi inclusif et accessible que possible pour tous vos utilisateurs. Suivez les guides et ressources ci-dessous pour configurer Microsoft Teams pour une accessibilité optimale.

> [!NOTE]
> La plupart des options d’accessibilité sont activées par défaut, mais vous pouvez vérifier qu’elles n’ont pas été désactivées en suivant les étapes décrites dans ce guide.

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>Activer les légendes et la transcription pour les réunions et les appels

Créez des réunions inclusives et des appels pour les utilisateurs handicapés afin que tout le monde puisse participer et contribuer.

### <a name="turn-on-live-captions-for-meetings"></a>Activer les sous-titres en direct pour les réunions

Les sous-titres en direct sont du texte généré automatiquement en temps réel de ce qui est dit dans une réunion. Elles apparaissent quelques lignes à la fois pour un utilisateur qui les a activées et qui ne sont pas enregistrées.

Pour activer les sous-titres en direct pour les utilisateurs :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Réunions**, puis sélectionnez les **stratégies de réunion** de liste déroulante.

2. Sélectionnez la stratégie à modifier.

3. Accédez à la section **Participants & invités** .

4. Basculez **les sous-titres en direct** sur **Non activé, mais l’utilisateur peut le remplacer**.

5. Sélectionnez **Enregistrer**.

> [!TIP]
> Partagez le lien suivant pour permettre aux utilisateurs d’apprendre à [activer des sous-titres en direct pendant les réunions](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop).

> [!NOTE]
> Des sous-titres en direct sont disponibles pour les réunions organisées dans les organisations commerciales et dans le cloud de la communauté du gouvernement des États-Unis (GCC).

### <a name="turn-on-transcription-for-calls"></a>Activer la transcription pour les appels

La transcription est générée automatiquement, le texte enregistré de ce qui a été dit dans un appel. Lorsqu’elle est activée, la transcription peut être examinée par les utilisateurs après la fin d’un appel.

Pour activer la transcription pour les utilisateurs :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Voix**, puis sélectionnez les **stratégies d’appel de liste déroulante**.

2. Sélectionnez la stratégie à modifier.

3. Activez **la transcription****, puis** **sélectionnez Enregistrer**.

### <a name="why-captions-and-transcripts-are-important"></a>Pourquoi les sous-titres et les transcriptions sont importants

Les sous-titres et les transcriptions sont des versions textuelles des mots que quelqu’un parle. Ils donnent aux gens la possibilité de voir du texte en plus ou au lieu de l’audio seul. Les légendes bénéficient également aux personnes sourdes ou malentendantes en fournissant des informations supplémentaires sur ce que certains utilisateurs reçoivent de l’interpréteur de langue des signes ou du sous-titreur CART avec lequel ils peuvent travailler.

Les légendes et la transcription sont utiles dans un large éventail de situations, mais peuvent être particulièrement utiles pour :

- Personnes sourds ou malentendants

- Personnes avec des difficultés d’apprentissage

- Personnes qui se trouvent dans un environnement bruyant ou distrait et qui doivent passer en revue les informations partagées après la fin d’une réunion

Pour plus d’informations, consultez les liens suivants :

- [Paramètres de stratégie de réunion pour l’enregistrement et la transcription](/Microsoftteams/meetings-policies-recording-and-transcription)

- [Web Content Accessibility Guidelines (WCAG) 1.2.4.: Captions (Live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>Accorder l’accès aux réunions aux interpréteurs de langue des signes et aux sous-titreurs CART (Communication Access Real-time Translation)

Donnez aux interpréteurs de langue des signes et aux sous-titreurs CART (communication access real-time translation) l’accès aux réunions Microsoft Teams afin qu’ils puissent travailler plus efficacement avec les utilisateurs sourds ou malentendants.

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>Admettre des interpréteurs de langue des signes et des sous-titreurs CART aux réunions

Les interpréteurs de langue des signes et les sous-titreurs CART ne fonctionnent probablement pas pour votre organisation, mais vous pouvez les inviter à des réunions Microsoft Teams [en leur donnant un accès invité](/MicrosoftTeams/guest-access).

Une fois l’accès invité accordé, pour admettre des interpréteurs de langue des signes et des sous-titreurs CART aux réunions :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Réunions**, puis sélectionnez les **stratégies de réunion** de liste déroulante.

2. Sélectionnez la stratégie à modifier.

3. Accédez à la section **Participants & invités** .

4. Choisissez l’option sous **Admettre automatiquement les personnes** qui répondent le mieux aux exigences de conformité et de sécurité de votre organisation. Vous pouvez sélectionner l’une des options suivantes :

   - Tout le monde (non recommandé)

   - Personnes dans mon organisation et les invités (recommandé)

   - Membres de mon organisation, organisations de confiance et invités

   - Membres de mon organisation

   - Organisateur uniquement

   - Utilisateurs invités uniquement

5. Sélectionnez **Enregistrer**.

> [!NOTE]
> Le paramètre **Admettre automatiquement les personnes** ne s’applique pas aux utilisateurs entrants.

### <a name="turn-on-ip-video-feed-for-your-users"></a>Activer le flux vidéo IP pour vos utilisateurs

Donnez aux interpréteurs de langage des signes la possibilité de partager des flux vidéo IP pendant les réunions Microsoft Teams afin qu’ils puissent communiquer avec les utilisateurs sourds ou malentendants.

Pour vérifier si le flux vidéo IP est activé :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Réunions**, puis sélectionnez les **stratégies de réunion** de liste déroulante.

2. Sélectionnez la stratégie à modifier.

3. Accédez à la section **audio & vidéo** .

4. Vérifiez que **la vidéo IP** **est activée,** puis **sélectionnez Enregistrer**.

> [!TIP]
> Partagez les liens suivants avec les utilisateurs afin qu’ils puissent ajuster la façon dont ils utilisent Teams pour optimiser leur capacité à participer, à se concentrer et à collaborer dans des réunions :
> - [Personnaliser votre vue de réunion](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [Utiliser des légendes CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>Pourquoi il est important d’inclure des interpréteurs de langue des signes et des sous-titreurs CART

Certains utilisateurs peuvent préférer utiliser des sous-titreurs CART, car ils peuvent être plus précis pour un jargon spécifique, des accents et bien plus encore, que des sous-titres générés automatiquement.

Les utilisateurs dont la méthode de communication principale est la langue des signes, nécessitent une interprétation de la langue des signes, ce qui nécessite la présence d’un interpréteur humain.

Pour plus d’informations, consultez le [Guide d’accessibilité du contenu web (WCAG) 1.2.6. : Interprétation de la langue des signes](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded).

## <a name="reduce-distractions-in-meetings"></a>Réduire les distractions dans les réunions

Encouragez la participation des utilisateurs en activant les filtres vidéo pour réduire les distractions dans les réunions Teams.

### <a name="turn-on-video-filters"></a>Activer les filtres vidéo

Les filtres vidéo permettent de réduire les distractions pendant les réunions.

Pour activer les filtres vidéo :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Réunions**, puis sélectionnez les **stratégies de réunion** de liste déroulante.

2. Sélectionnez la stratégie à modifier.

3. Accédez à la section **Partage de contenu** .

4. Choisissez l’option sous **Sélectionner des filtres vidéo** qui répondent le mieux aux exigences de conformité et de sécurité de votre organisation. Sélectionnez l’une des options suivantes :

   - Flou d’arrière-plan uniquement

   - Flou d’arrière-plan et images par défaut

   - Tous les filtres

5. Sélectionnez **Enregistrer**.

> [!TIP]
> Partagez les liens suivants afin que les utilisateurs puissent ajuster leurs préférences de réunion Teams pour réduire les distractions :
> - [Modifier les effets d’arrière-plan dans les réunions Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [Réduire le bruit de fond dans les réunions Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>Pourquoi il est utile de réduire les distractions

Certaines personnes de votre organisation peuvent avoir de la difficulté à se concentrer pendant les réunions vidéo et les appels en raison du mouvement, de la lumière et d’autres distractions dans les antécédents des participants. L’utilisation de filtres vidéo permet aux utilisateurs de contrôler les distractions et de participer pleinement.

*Les effets d’arrière-plan* peuvent aider les gens à se concentrer sur l’orateur plutôt que sur son arrière-plan. Microsoft Teams dispose d’une bibliothèque d’arrière-plans, et les utilisateurs peuvent également charger leurs propres arrière-plans.

*Le flou d’arrière-plan* permet d’améliorer la visibilité et le focus lors de réunions ou d’appels, car il réduit les distractions en arrière-plan, mais maintient le focus des utilisateurs.

Les filtres vidéo sont utiles dans un large éventail de situations, mais peuvent être particulièrement utiles pour :

- Personnes neurodiverse

- Personnes sourds ou malentendants

Pour plus d’informations, consultez [la directive WCAG (Web Content Accessibility Guideline) 1.4.8.: Visual Presentation](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html).

## <a name="improve-participation-in-microsoft-teams-meetings"></a>Améliorer la participation aux réunions Microsoft Teams

Encouragez la participation des utilisateurs avec plus d’options de contrôle et de flexibilité en activant la **conversation dans les réunions**, et en activant des stratégies de messagerie telles que la modification de conversation, **Lecteur immersif** et les emojis.

### <a name="turn-on-chat-in-meetings"></a>Activer la conversation dans les réunions

La conversation permet à de nombreux utilisateurs de poser des questions ou d’ajouter des informations dans les réunions Teams.

Pour vérifier si la conversation en réunion est activée :

1. Dans le Centre d’administration Microsoft Teams, accédez à **Réunions**, puis sélectionnez les **stratégies de réunion** de liste déroulante.

2. Sélectionnez la stratégie à modifier.

3. Accédez à la section **Participants & invités** .

4. Choisissez l’option sous **Conversation dans les réunions** qui correspond le mieux aux exigences de conformité et de sécurité de votre organisation. Vous pouvez sélectionner l’une des options suivantes :

   - L’activer pour tout le monde (recommandé)

   - Désactivez-le pour tout le monde (non recommandé)

   - Activez-le pour tout le monde, sauf les utilisateurs anonymes

5. Sélectionnez **Enregistrer**.

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>Utiliser des stratégies de messagerie pour une flexibilité et un contrôle accrus

Les options de conversation flexibles permettent à de nombreux utilisateurs de comprendre plus facilement les messages d’autres utilisateurs, de réviser leurs propres messages et de s’exprimer.

Pour vérifier si ces options de conversation flexibles sont activées :

Dans le **Centre d’administration Microsoft Teams** :

1. Dans le Centre d’administration Microsoft Teams, accédez aux **stratégies de messagerie**.

2. Sélectionnez la stratégie à modifier.

3. Vérifiez que les éléments suivants **sont activés** :

   - **Supprimer des messages envoyés**

   - **Modifier des messages envoyés**

   - **Conversation**

   - **Giphys dans les conversations**

   - **Mèmes dans les conversations**

   - **Autocollants dans les conversations**

   - **Aperçus d’URL**

   - **Traduire des messages**

   - **Lecteur immersif pour les messages**

4. Sélectionnez **Enregistrer**.

> [!TIP]
> Partagez le lien [pour écrire du texte de remplacement efficace](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) avec votre organisation afin d’aider les utilisateurs à comprendre les messages non textuels partagés dans la conversation.

### <a name="why-alternate-participation-options-matter"></a>Pourquoi les options de participation alternatives sont importantes

Les options de conversation flexibles offrent aux utilisateurs une plus grande flexibilité dans la façon dont ils utilisent le contenu de conversation en réunion et un contrôle accru sur la façon dont ils participent à une réunion avec une conversation.

*La conversation en réunion* offre aux personnes un autre moyen de participer à la discussion de la réunion. Pour certaines personnes handicapées, la conversation peut être préférable à la voix ou à la langue des signes comme moyen de contribuer aux discussions de réunion.

*Lecteur immersif*, un outil conçu pour les personnes souffrant de dyslexie et de dysgraphie, facilite la compréhension du texte. Il inclut également la traduction en ligne pour les personnes qui préfèrent communiquer dans une autre langue. Voici quelques-unes des principales fonctionnalités de Lecteur immersif :

- Ajout de l’option permettant de lire le contenu à voix haute

- Modification de la taille du texte et de la couleur d’arrière-plan

- Mots cassants en syllabes

- Augmentation de l’espace entre les lettres

- Mise en surbrillance d’une ou de plusieurs lignes de texte

- Mettre en surbrillance des parties de la parole

Les options de conversation flexibles sont utiles dans un large éventail de situations, mais peuvent être particulièrement utiles pour :

- Personnes aveugles ou malvoyants

- Personnes qui sont neurodiverse (c’est-à-dire ayant une dyslexie ou une dysgraphie)

Pour plus d’informations, consultez [web Content Accessibility Guidelines (WCAG) 1.1.1.: Text Alternatives](https://www.w3.org/TR/WCAG21/#text-alternatives).

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>Partager des ressources avec les utilisateurs pour mieux connaître l’accessibilité

Il existe des étapes supplémentaires que les utilisateurs peuvent suivre pour améliorer leur expérience en matière d’accessibilité. Partagez les liens ci-dessous avec votre organisation et les utilisateurs invités.

### <a name="reference-links"></a>Liens de référence

Le support technique des personnes handicapées de Microsoft propose des guides pour les utilisateurs finaux afin de personnaliser leur expérience afin de répondre à leurs besoins d’accessibilité :

- [Activer les sous-titres en direct pendant les réunions](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [Personnaliser votre vue de réunion](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [Utiliser des légendes CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [Modifier les effets d’arrière-plan dans les réunions Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [Réduire le bruit de fond dans les réunions Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [Écrire du texte de remplacement effectif](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Outils d’accessibilité pour Microsoft Teams](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>Référencer les instructions d’accessibilité du contenu web (WCAG)

WCAG est une série de normes internationales conçues pour améliorer l’accessibilité web. Les critères de réussite référencés dans ce guide sont les suivants :

- [WCAG 1.2.4.: Captions (Live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.: Interprétation de la langue des signes](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.: Visual Presentation](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.: Text Alternatives](https://www.w3.org/TR/WCAG21/#text-alternatives)
