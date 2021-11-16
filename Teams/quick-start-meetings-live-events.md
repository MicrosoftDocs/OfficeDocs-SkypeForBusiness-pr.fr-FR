---
title: 'Démarrage rapide : réunions, webinaires et événements en direct'
ms.reviewer: ''
description: Guide de démarrage rapide permettant aux administrateurs de déployer et de configurer des réunions, des webinaires et des événements en direct dans Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: caabea3e1310ad704953171836dcdfb35506609a
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960063"
---
# <a name="quick-start---meetings-webinars-and-live-events"></a>Démarrage rapide : réunions, webinaires et événements en direct 

Il existe plusieurs façons de se réunir dans Microsoft Teams : réunions, webinaires et événements en direct. 

Cet article, destiné aux administrateurs et aux professionnels de l’informatique, décrit brièvement les différences entre les réunions, les webinaires et les événements en direct. Il fournit ensuite des liens vers les informations dont vous avez besoin pour déployer rapidement cette fonctionnalité pour vos utilisateurs.

> [!Note]
> Pour plus d’informations sur la configuration rapide de réunions et d’événements Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings-webinars-and-live-events"></a>Réunions, webinaires et événements en direct

[Les réunions](#meetings), [webinaires](#webinars)et [événements en direct](#live-events) sont tous des types de réunions, mais les webinaires et les événements en direct offrent un contrôle supplémentaire à l’organisateur sur la conversation et les participants. Les webinaires fournissent une interaction bidirectionnelle tandis que les événements en direct offrent une expérience de questions et réponses gérée. 

Les différents types de réunions ont également des limites de participants et des fonctionnalités de participants différentes. 

Le tableau suivant récapitule brièvement les trois types de réunions, le nombre de participants recommandés et la façon dont les participants peuvent interagir dans la réunion.<br><br>

| Type de réunion | Nombre de participants | Interaction | Inscription prise en charge |
|----------|--------|--------|-----|
| Réunions  | Jusqu’à 20 000* <br> | - Jusqu’à 1 000, les participants disposent des mêmes fonctionnalités de réunion totalement interactives. <br> - Au delà de 1 000 et jusqu’ à 20 000, les participants ont des fonctionnalités en [lecture seule](view-only-meeting-experience.md).  | Non |
| Séminaires web | - Jusqu'à 1 000<br>- Des limites accrues avec des fonctionnalités en [lecture seule](view-only-meeting-experience.md) seront bientôt disponibles. |- Jusqu’à 1 000, les participants disposent de fonctionnalités totalement interactives. <br> -Interaction de l’audience configurable. <br> - Peut spécifier des présentateurs. | Oui |
| Événements en direct | Jusqu’à 20 000** |- Diffuser au grand public. <br>- Questions et réponses modérées pour l’interaction de l’audience. <br> - Peut spécifier des producteurs et des présentateurs, y compris des présentateurs externes.<br>- Prend en charge des fonctionnalités de production plus avancées. | Non |
||||

*Les 10 000 habituels sont augmentés à 20 000 jusqu’au 30 juin 2022.<br>

**Les 10 000 habituels sont augmentés à 20 000 jusqu’au 30 juin 2022. Vous pouvez planifier des nombres encore plus importants avec des événements en direct dans Yammer et/ou Microsoft Stream. Pour plus d’informations, consultez [Événements en direct sur Microsoft 365](/stream/live-event-m365). Notez que les événements de plus de 20 000 participants nécessitent le [Programme d’assistance aux événements en direct](/stream/live-events-assistance). 

**Considérations relatives aux grandes réunions, aux webinaires et aux événements en direct** : lors de l’hébergement de réunions de grande taille, tenez compte des points suivants :

- Pour une expérience optimale dans les grandes réunions, Microsoft recommande d’utiliser le client de bureau Teams ou les clients mobiles Teams. 

- Les présentateurs des grandes réunions doivent utiliser le client de bureau Teams. 

- Pour plus d’informations sur l’hébergement de grandes réunions, consultez [Meilleures pratiques pour une grande réunion Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

Pour plus d’informations sur l’expérience de réunion en lecture seule, consultez [Expérience de réunion en lecture seule Teams](view-only-meeting-experience.md).

Notez que NDI est entièrement pris en charge dans les réunions, les webinaires et les événements en direct, ce qui vous permet de produire la diffusion à l’aide d’outils tels que OBS et Wirecast. Pour plus d’informations, consultez [Utiliser la technologie NDI® dans Microsoft Teams](use-ndi-in-meetings.md).


### <a name="meetings"></a>Réunions

**Les réunions** dans Teams incluent le partage audio, vidéo et d’écran pour jusqu’à 1 000 personnes et des [fonctionnalités d’affichage uniquement](view-only-meeting-experience.md) pour les événements de plus de 1 000 participants. Les participants n’ont pas besoin d’être membres d’une organisation (ou d’avoir un compte Teams) pour participer à une réunion Teams. Ils peuvent participer directement à partir de l’invitation au calendrier via le lien Rejoindre la réunion ou appeler via audio, le cas échéant.  

En tant qu’administrateur, vous allez configurer les paramètres de réunion et contrôler les fonctionnalités de réunion activées pour votre organisation en spécifiant des stratégies de réunion.  

Outre les réunions planifiées régulièrement, vos utilisateurs peuvent créer des réunions de canal. Avec les réunions de canal, tous les membres d’une équipe peuvent voir qu’il y a une réunion, participer à la réunion et utiliser la conversation de réunion. Les réunions de canal permettent d’inviter rapidement tous les membres d’une équipe à une réunion. Pour plus d’informations sur la façon dont les utilisateurs finaux planifient des réunions, consultez [Planifier une réunion](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5).

#### <a name="articles-for-administrators"></a>Articles pour les administrateurs

Le tableau suivant met en évidence les articles clés que vous souhaitez examiner :

| Article | Description | 
|----------|--------|
| [Paramètres de réunion](meeting-settings-in-teams.md) |  Décrit comment configurer les paramètres des réunions pour les utilisateurs anonymes, les invitations aux réunions et le trafic multimédia.  |
| [Stratégies de réunion](meeting-policies-overview.md)  | Décrit comment créer et gérer les stratégies qui déterminent les fonctionnalités disponibles pour les participants à la réunion. | 
| [Gérer l’enregistrement des réunions cloud Teams](cloud-recording.md) | Décrit comment gérer les enregistrements de réunion. |
| [Gérer les appareils de votre organisation](device-management.md)| Décrit comment gérer les appareils de votre organisation, tels que les téléphones et les salles Teams. |
||

#### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Gérer les réunions](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Vidéo de formation rapide destinée aux utilisateurs qui débutent avec les réunions Teams. |
| [Planifier une réunion](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | Article qui décrit comment planifier différents types de réunions. |
| [Tenez des réunions efficaces avec Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | Classe gratuite dirigée par un instructeur sur la façon de rendre les réunions plus attrayantes, productives et significatives. |
| [Modifier les paramètres des participants pour une réunion Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | Article sur la gestion des options de réunion.
||


### <a name="webinars"></a>Séminaires web

**Les webinaires** sont des réunions structurées où les présentateurs et les participants ont des rôles clairs. Une différence clé entre les webinaires et les réunions Teams est que les webinaires prennent en charge l’inscription et fournissent des données d’engagement des participants. Pour activer les webinaires dans votre organisation, consultez [Configurer des webinaires dans Teams](set-up-webinars.md). 


#### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Démarrage avec les webinaires Teams](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Vidéo de formation rapide destinée aux utilisateurs qui débutent avec les webinaires Teams. |
| [Guide de démarrage rapide visuel](https://teamworktools.azurewebsites.net/assets/TeamsWebinarsGetStartedGuide.pdf) | Guide visuel téléchargeable qui décrit comment commencer à planifier des webinaires.  |
||


### <a name="live-events"></a>Événements en direct

**Les événements en direct** sont des réunions structurées qui permettent à votre organisation de planifier et de produire des événements qui sont diffusés en continu à de grands publics en ligne&mdash; jusqu’à 20 000 personnes. Avec les événements en direct, l’interaction de l’audience est une expérience de questions et réponses managée.

#### <a name="articles-for-administrators"></a>Articles pour les administrateurs

Le tableau suivant met en évidence les articles clés que vous souhaitez examiner :

| Article | Description | 
|----------|--------|
| [Que sont les événements en direct Teams ?](teams-live-events/what-are-teams-live-events.md)  | Présentation rapide des événements en direct. |
| [Offre pour les événements en direct Teams](teams-live-events/plan-for-teams-live-events.md) | Ce que vous devez savoir avant de configurer des événements en direct. |
| [Configurer les événements en direct Teams](teams-live-events/set-up-for-teams-live-events.md) | Décrit les prérequis, tels que la planification réseau. |
| [Configurer des événements en direct](teams-live-events/configure-teams-live-events.md) | Étapes de configuration des événements en direct.
||

#### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Démarrage avec les événements en direct](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | Présentation des événements en direct et de la prise en main. |
| [Formation vidéo sur les événements en direct Teams](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | Vidéo qui décrit comment organiser et planifier un événement en direct.  |
||

Pour produire des événements virtuels à plus grande échelle, consultez le [Guide Événement Virtuel](https://adoption.microsoft.com/virtual-event-guidance/), qui contient des conseils pour les organisateurs d’événements, les producteurs techniques, les professionnels de l’informatique et les créateurs de contenu. 

## <a name="apps-for-meetings"></a>Applications pour les réunions

Microsoft vous permet d’améliorer les expériences de réunion en intégrant et en utilisant des applications de réunion. Par exemple, l’intégration du tableau blanc dans les réunions Teams est optimisée par l’application web Tableau blanc, qui permet aux participants aux réunions Teams de dessiner, d’esquisser et d’écrire ensemble sur un canevas numérique partagé.

Vous pouvez ajouter des applications de réunion à votre déploiement Teams à l’aide des applications fournies avec Teams, à l’aide d’applications et de modèles tiers certifiés, et en créant vos propres applications personnalisées. 

Le tableau suivant répertorie les articles pour plus d’informations :

| Article | Description | 
|----------|--------|
| [Applications, bots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) | Présentation des applications et comment déployer des applications pour votre organisation. |
| [Applications pour Teams réunions] (/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings | Vue d’ensemble de l’extensibilité des applications de réunion, des références d’API et de la façon d’activer et de configurer des applications pour les réunions. |
| [Gérer le tableau blanc dans Teams](manage-whiteboard.md) | Décrit les fonctionnalités du Tableau blanc et comment l’activer et désactiver pour votre organisation. |
||

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>Licence requise pour les réunions, les webinaires et les événements en direct

Tout le monde peut participer à une réunion Teams, à un webinaire ou à un événement en direct gratuitement&mdash; aucune licence n’est requise. 

Pour les personnes qui organisent, planifient et hébergent des réunions, des webinaires ou des événements en direct, elles ont besoin de l’une des licences Microsoft 365 répertoriées dans la description du service [Microsoft Teams](/office365/servicedescriptions/teams-service-description). Si vous utilisez déjà Teams, vous disposez probablement de la licence dont vous avez besoin pour organiser et héberger des réunions, des webinaires et des événements en direct.

Pour permettre aux personnes de se connecter à une réunion par téléphone, vous devez configurer l’audioconférence. Pour plus d’informations sur l’audioconférence, consultez [Audioconférence dans Teams](deploy-audio-conferencing-teams-landing-page.md).


## <a name="related-topics"></a>Sujets associés

[Réunions et conférences dans Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)

[Configurer des webinaires dans Teams](set-up-webinars.md)

[Événements en direct dans Microsoft Teams](teams-live-events/what-are-teams-live-events.md)

[Expérience de réunion en lecture seule de Teams](view-only-meeting-experience.md)

[Spécifications et limites de Microsoft Teams](limits-specifications-teams.md)

[Communauté technique Microsoft : événements en direct dans Microsoft 365](https://resources.techcommunity.microsoft.com/live-events/)
